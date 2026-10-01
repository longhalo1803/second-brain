---
title: Bộ Lọc Bloom (Bloom Filter - Cấu Trúc Xác Suất)
aliases:
  - Bloom Filter
  - Bộ lọc Bloom
  - Probabilistic Data Structure
tags:
  - dsa
  - data-structure
  - specialized
  - system-design
stage: 6
type: architecture
difficulty: intermediate
status: completed
created: 2026-08-27
updated: 2026-10-01
sources:
  - "[[CLRS - Introduction to Algorithms]]"
cross_domain:
  - "[[Database-knowledge/01 - Core Concepts/Block (Page)]]"
---

# 🌸 Bộ Lọc Bloom (Bloom Filter - Cấu Trúc Xác Suất)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Đồ Khái Niệm (Mermaid DAG)

```mermaid
graph TD
    Elem["Phần Tử Cần Nạp (String/Key)"] --> Hashes["k Hàm Băm Độc Lập: h1(x), h2(x) ... hk(x)"]
    Hashes --> Bits["Mảng BitArray Kích Thước m (Toàn Số 0 và 1)"]
    Bits --> Write["Thao Tác add(): Bật Toàn Bộ k Vị Trí Bit Thành 1"]
    Bits --> Query["Thao Tác contains(): Kiểm Tra k Vị Trí Bit"]
    Query --> Q1{"Có Bất Kỳ Bit Nào Bằng 0?"}
    Q1 -->|Có (Dù Chỉ 1 Bit)| Neg["CHẮC CHẮN 100% PHẦN TỬ CHƯA TỒN TẠI (No False Negatives)"]
    Q1 -->|Toàn Bộ Bit Đều Bằng 1| Pos["CÓ THỂ ĐÃ TỒN TẠI (Có Tỷ Lệ Nhỏ Dương Tính Giả - False Positive)"]
```

---

## 2. Chân Lý Vô Điều Kiện (First Principles)

> [!NOTE] Tiên Đề Không Bao Giờ Âm Tính Giả (Zero False Negatives)
> **Bộ lọc Bloom là cấu trúc dữ liệu xác suất (Probabilistic Data Structure) với định lý thép:**
> 1. Nếu Bloom Filter trả về **`false`**: Phần tử **CHẮC CHẮN 100% KHÔNG TỒN TẠI** trong tập hợp.
> 2. Nếu Bloom Filter trả về **`true`**: Phần tử **CÓ THỂ TỒN TẠI** (tồn tại xác suất dương tính giả do các phần tử khác vô tình bật trùng các bit đó).
>
> **Công thức xác suất dương tính giả ($p$):**
> $$ p \approx \left(1 - e^{-kn/m}\right)^k $$
> Với $m$ là số lượng bits, $n$ là số phần tử đã chèn, và $k$ là số hàm băm.
> Số hàm băm tối ưu để triệt tiêu xác suất lỗi là: $k = \frac{m}{n} \ln 2 \approx 0.7 \times \frac{m}{n}$.

---

## 3. Trực Giác Motivated Discovery

> [!TIP] Động Lực 3Blue1Brown: Kiểm Tra URL Độc Hại & Tránh Đọc Ổ Đĩa Vô Ích
> Google Chrome có danh sách 100 triệu trang web độc hại (Malicious URLs).
>
> - **Nếu dùng Hash Table:** Bạn cần lưu 100 triệu chuỗi URL trong RAM máy người dùng $\to$ Ngốn sạch vài Gigabytes RAM, máy tính đơ giật!
> - **Giải pháp của Bloom Filter:** Nén toàn bộ 100 triệu URL vào một mảng bit chỉ vỏn vẹn ** vài Megabytes RAM**:
>   - Khi người dùng vào web `example.com`: Chrome hỏi Bloom Filter. Nếu bộ lọc bảo "KHÔNG", bạn được duyệt web tức thì trong $O(1)$ mà không cần tải bất kỳ dữ liệu nào từ máy chủ.
>   - Nếu bộ lọc bảo "CÓ THỂ", Chrome mới gửi request lên Server Google để kiểm tra chắc chắn lần cuối!
>
> Bạn đã bảo vệ an toàn cho người dùng mà tiết kiệm đến **$99\%$ băng thông và dung lượng RAM**!

---

## 4. Phân Tích Kỹ Thuật & Đa Miền Hệ Thống

### Bảng Độ Phức Tạp (Complexity Sheet)

| Thao Tác | Thời Gian (Time) | Không Gian Bộ Nhớ (Space) | Rủi Ro Kỹ Thuật |
| :--- | :--- | :--- | :--- |
| **Thêm phần tử (`add`)** | [[O(1) - Constant Time|$O(k)$]] ($k$ hàm băm) | Cực nhỏ ($10$ bits / phần tử cho sai số $1\%$) | Không thể xóa (Standard Bloom Filter) |
| **Kiểm tra tồn tại (`contains`)** | [[O(1) - Constant Time|$O(k)$]] ($k$ hàm băm) | Không tốn thêm bộ nhớ phụ | Chấp nhận $1\%$ Dương tính giả |

### 🌐 Ứng Dụng Trong Cơ Sở Dữ Liệu (Cassandra, RocksDB, BigTable)
- **Cứu Tinh Của Cấu Trúc LSM-Tree:** Trong các hệ quản trị NoSQL hiện đại (Cassandra / ScyllaDB), dữ liệu được ghi tuần tự vào đĩa thành các file SSTable bất biến. Khi người dùng truy vấn `SELECT * WHERE key = 'user_999'`, thay vì phải chui xuống ổ đĩa đọc từng file SSTable ($O(\text{Disk I/O})$ cực chậm), hệ thống hỏi Bloom Filter của từng file: File nào trả lời "KHÔNG" $\to$ Bỏ qua ngay lập tức, **triệt tiêu 99% các lần đọc đĩa vô ích**!

---

## 5. Cài Đặt Chuẩn Mực (TypeScript - BloomFilter)

```typescript
export class BloomFilter {
  private size: number;
  private bitArray: Uint8Array;
  private hashCount: number;

  constructor(sizeInBits = 1024, hashCount = 3) {
    this.size = sizeInBits;
    this.hashCount = hashCount;
    // Mỗi byte chứa 8 bits
    this.bitArray = new Uint8Array(Math.ceil(this.size / 8));
  }

  // Tạo k giá trị băm độc lập bằng kỹ thuật Double Hashing
  private getHashValues(item: string): number[] {
    let hash1 = 0;
    let hash2 = 0;
    for (let i = 0; i < item.length; i++) {
      const char = item.charCodeAt(i);
      hash1 = (hash1 * 31 + char) % this.size;
      hash2 = (hash2 * 37 + char) % this.size;
    }
    const hashes: number[] = [];
    for (let i = 0; i < this.hashCount; i++) {
      hashes.push(Math.abs((hash1 + i * hash2) % this.size));
    }
    return hashes;
  }

  // Thêm phần tử: Bật các bit lên 1 trong O(k)
  add(item: string): void {
    const hashes = this.getHashValues(item);
    for (const bitIndex of hashes) {
      const byteIdx = Math.floor(bitIndex / 8);
      const bitOffset = bitIndex % 8;
      this.bitArray[byteIdx] |= (1 << bitOffset);
    }
  }

  // Kiểm tra: Nếu có bất kỳ bit nào bằng 0 -> Chắc chắn 100% chưa có
  contains(item: string): boolean {
    const hashes = this.getHashValues(item);
    for (const bitIndex of hashes) {
      const byteIdx = Math.floor(bitIndex / 8);
      const bitOffset = bitIndex % 8;
      if ((this.bitArray[byteIdx] & (1 << bitOffset)) === 0) {
        return false; // Chắc chắn KHÔNG tồn tại
      }
    }
    return true; // CÓ THỂ tồn tại
  }
}
```

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)

Nguyên lý Không bao giờ âm tính giả (No False Negatives) của Bloom Filter là gì? #card
?
Nếu Bloom Filter trả lời phần tử không có mặt trong tập hợp (`contains() === false`), thì chắc chắn 100% phần tử đó chưa từng được thêm vào. Không bao giờ có trường hợp một phần tử đã được thêm mà Bloom Filter lại nói không có.

Tại sao không thể xóa một phần tử khỏi Bloom Filter tiêu chuẩn? #card
?
Vì nhiều phần tử khác nhau có thể chia sẻ chung một số vị trí bit 1. Nếu bạn tắt một bit về 0 để xóa phần tử A, bạn sẽ vô tình làm hỏng kết quả kiểm tra của phần tử B và C vốn cũng dùng chung bit đó. Muốn xóa, người ta phải dùng biến thể Counting Bloom Filter.
