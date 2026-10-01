---
title: Bộ Nhớ Đệm LRU (LRU Cache - Least Recently Used)
aliases:
  - LRU Cache
  - Least Recently Used
  - Bộ nhớ đệm LRU
tags:
  - dsa
  - data-structure
  - system-design
  - cache
stage: 6
type: practical
difficulty: intermediate
status: completed
created: 2026-08-27
updated: 2026-10-01
sources:
  - "[[CLRS - Introduction to Algorithms]]"
  - "[[NeetCode - Algorithmic Patterns]]"
cross_domain:
  - "[[Database-knowledge/01 - Core Concepts/Buffer Cache]]"
  - "[[Database-knowledge/02 - Core Principles/3 Yếu tố cốt lõi làm Database nhanh]]"
---

# 🔄 Bộ Nhớ Đệm LRU (LRU Cache - Least Recently Used)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Đồ Khái Niệm (Mermaid DAG)

```mermaid
graph TD
    Client["Client / User Request: get(key) hoặc put(key, val)"] --> MapCheck{"Hash Table có Key?"}
    
    MapCheck -->|Có (Cache Hit)| GetHit["1. Lấy con trỏ Node tức thời: O(1)"]
    GetHit --> Promote["2. Ngắt Node khỏi vị trí hiện tại & Đưa lên ngay sau Dummy Head"]
    Promote --> ReturnVal["3. Trả về giá trị Node / Cập nhật giá trị mới"]

    MapCheck -->|Không (Cache Miss)| MissCheck{"Cache Đã Đầy? (size === capacity)"}
    MissCheck -->|Đầy| Evict["Loại bỏ Node ít dùng nhất: Node sát trước Dummy Tail (O(1))"]
    Evict --> DeleteMap["Xóa Key tương ứng khỏi Hash Table"]
    DeleteMap --> InsertNew["Tạo Node Mới"]
    MissCheck -->|Chưa đầy| InsertNew
    InsertNew --> AddHead["Chèn Node Mới vào ngay sau Dummy Head"]
    AddHead --> SaveMap["Lưu (Key -> Node) vào Hash Table: O(1)"]
```

---

## 2. Chân Lý Vô Điều Kiện (First Principles)

> [!NOTE] Tiên Đề Định Xứ Thời Gian (Temporal Locality) & Đẳng Thức $O(1)$
> **Dữ liệu vừa được truy cập trong quá khứ gần có xác suất cực cao sẽ được truy cập lại trong tương lai gần.**
>
> 1. **Mâu thuẫn kỹ thuật giữa Tìm Kiếm và Thứ Tự:**
>    - Mảng / Danh sách liên kết giữ thứ tự thời gian tuyệt vời nhưng tìm kiếm mất $O(n)$.
>    - Hash Table tìm kiếm $O(1)$ nhưng hoàn toàn vô cảm với thứ tự thời gian sử dụng.
> 2. **Giải pháp lai ghép tối ưu:** Kết hợp **[[Hash Table & HashSet|Hash Table]]** (lưu `Key -> Node*`) với **[[Linked List|Doubly Linked List]]** (nối các Node theo thứ tự thời gian) là kiến trúc duy nhất thỏa mãn cả `get(k)` và `put(k, v)` đạt đúng **$\Theta(1)$** mà không tốn công dịch chuyển phần tử.

---

## 3. Trực Giác Motivated Discovery

> [!TIP] Động Lực 3Blue1Brown: Bàn Làm Việc 3 Cuốn Sách Của Kỹ Sư
> Bạn làm việc tại một chiếc bàn hẹp chỉ để vừa đúng 3 cuốn sách:
>
> 1. Bạn lấy cuốn *Hệ Điều Hành* ra đọc $\to$ đặt nó ngay trước mặt (Vị trí đầu - Most Recently Used).
> 2. Bạn lấy cuốn *Mạng Máy Tính* $\to$ đẩy cuốn *Hệ Điều Hành* sang bên cạnh, đặt cuốn Mạng lên trước mặt.
> 3. Bạn lấy cuốn *Cơ Sở Dữ Liệu* $\to$ chiếc bàn vừa vặn 3 cuốn.
> 4. Bây giờ bạn muốn đọc cuốn *Trí Tuệ Nhân Tạo*: Bàn đã đầy! Cuốn nào phải bị cất vào tủ sách?
>    - Cuốn nằm xa tay bạn nhất ở góc bàn (cuốn *Hệ Điều Hành*) chính là cuốn **lâu nhất chưa được bạn đụng tới (LRU)**. Bạn cất nó đi và đặt cuốn mới lên đầu bàn!

---

## 4. Phân Tích Kỹ Thuật & Đa Miền Hệ Thống

### Bảng Độ Phức Tạp Tuyệt Đối

| Thao Tác | Thời Gian (Time) | Không Gian (Space) | Cơ Chế Triển Khai |
| :--- | :--- | :--- | :--- |
| **`get(key)`** | [[O(1) - Constant Time\|$O(1)$]] | [[O(1) - Constant Time\|$O(1)$]] | Hash Table trỏ tới Node $\to$ Nhấc node đưa lên đầu |
| **`put(key, val)`** | [[O(1) - Constant Time\|$O(1)$]] | [[O(1) - Constant Time\|$O(1)$]] | Cập nhật / Thêm mới vào đầu $\to$ Xóa đuôi nếu đầy |
| **Dung lượng tổng** | — | [[O(capacity) - Linear Time\|$O(C)$]] | Lưu tối đa đúng $C$ nodes trên RAM |

### 🌐 Ứng Dụng Trong Cơ Sở Dữ Liệu & DevOps
- **Database Buffer Cache:** PostgreSQL và MySQL InnoDB sử dụng biến thể của LRU (Clock Sweep Algorithm / 2Q Buffer Pool) để giữ lại các Disk Page 8KB/16KB thường xuyên truy vấn trên RAM, tránh nghẽn Disk I/O (Xem: [[Database-knowledge/01 - Core Concepts/Buffer Cache|Buffer Cache]]).
- **Redis Eviction Policy:** Khi Redis chạm ngưỡng `maxmemory`, cấu hình `allkeys-lru` hoặc `volatile-lru` sử dụng thuật toán xấp xỉ LRU để dọn dẹp RAM phục vụ các write request mới.

---

## 5. Cài Đặt Chuẩn Mực (TypeScript)

Sử dụng kỹ thuật **Dummy Head** và **Dummy Tail** để triệt tiêu toàn bộ lỗi xử lý con trỏ `null` ở ranh giới danh sách:

```typescript
class DNode {
  key: number;
  val: number;
  prev: DNode | null = null;
  next: DNode | null = null;

  constructor(key: number = 0, val: number = 0) {
    this.key = key;
    this.val = val;
  }
}

export class LRUCache {
  private capacity: number;
  private map: Map<number, DNode>;
  private head: DNode;
  private tail: DNode;

  constructor(capacity: number) {
    this.capacity = capacity;
    this.map = new Map();

    // Khởi tạo dummy ranh giới
    this.head = new DNode();
    this.tail = new DNode();
    this.head.next = this.tail;
    this.tail.prev = this.head;
  }

  // 1. Đọc giá trị và đôn lên đầu
  get(key: number): number {
    const node = this.map.get(key);
    if (!node) return -1;

    // Đôn node vừa dùng lên đầu (sát sau dummy head)
    this.moveToHead(node);
    return node.val;
  }

  // 2. Thêm hoặc cập nhật giá trị
  put(key: number, value: number): void {
    const node = this.map.get(key);

    if (node) {
      node.val = value;
      this.moveToHead(node);
    } else {
      const newNode = new DNode(key, value);
      this.map.set(key, newNode);
      this.addNode(newNode);

      // Nếu vượt quá capacity -> loại bỏ node ít dùng nhất (sát dummy tail)
      if (this.map.size > this.capacity) {
        const evicted = this.popTail();
        this.map.delete(evicted.key);
      }
    }
  }

  // Chèn node vào ngay sau head
  private addNode(node: DNode): void {
    node.prev = this.head;
    node.next = this.head.next;

    this.head.next!.prev = node;
    this.head.next = node;
  }

  // Ngắt liên kết của node khỏi vị trí hiện tại
  private removeNode(node: DNode): void {
    const prevNode = node.prev!;
    const nextNode = node.next!;

    prevNode.next = nextNode;
    nextNode.prev = prevNode;
  }

  // Đôn node lên đầu
  private moveToHead(node: DNode): void {
    this.removeNode(node);
    this.addNode(node);
  }

  // Xóa và trả về node ở sát trước tail (Least Recently Used)
  private popTail(): DNode {
    const res = this.tail.prev!;
    this.removeNode(res);
    return res;
  }
}
```

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)

Tại sao LRU Cache bắt buộc phải dùng Doubly Linked List mà không thể dùng Singly Linked List? #card
?
Vì khi muốn ngắt một node bất kỳ ở giữa danh sách để đôn lên đầu, Doubly Linked List cho phép truy cập node liền trước trong $O(1)$ (`node.prev.next = node.next`). Nếu dùng Singly Linked List, ta buộc phải duyệt tuần tự từ đầu mất $O(n)$ để tìm node trước nó, phá vỡ tiêu chuẩn $O(1)$.

Kỹ thuật Dummy Head và Dummy Tail mang lại lợi thế gì khi cài đặt LRU Cache? #card
?
Nó đóng vai trò nút chặn ranh giới vĩnh viễn, giúp triệt tiêu hoàn toàn các câu lệnh kiểm tra điều kiện biên (`if (head === null)`, `if (node === tail)`), làm code ngắn gọn, không có ngoại lệ null pointer và ngăn chặn rò rỉ ranh giới con trỏ.
