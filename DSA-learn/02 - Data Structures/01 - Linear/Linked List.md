---
tags:
  - dsa
  - data-structure
  - linear
stage: 2
type: data-structure
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Linked List
  - Singly Linked List
  - Doubly Linked List
  - Danh sách liên kết
  - Linked Lists
---

# 🔗 Danh Sách Liên Kết (Linked List)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)

- **Định nghĩa:** Là tập hợp các nút (Node) nằm rải rác bất kỳ đâu trong bộ nhớ RAM, được kết nối với nhau thông qua các **con trỏ tham chiếu (Pointers)**. Mỗi Node gồm 2 phần: `Value` (Dữ liệu) và `Next` (Địa chỉ node tiếp theo).
- **Phân loại:**
  - _Singly Linked List:_ Con trỏ 1 chiều (`Node -> Next`).
  - _Doubly Linked List:_ Con trỏ 2 chiều (`Node -> Prev` và `Node -> Next`).
- **Hình dung:** Giống như một đoàn tàu lửa nối toa bằng các móc xích, hoặc trò chơi săn kho báu: mỗi manh mối chỉ chứa dữ liệu và một tấm bản đồ chỉ đường tới vị trí của manh mối tiếp theo.

---

![[Pasted image 20260907115804.png]]

![[Pasted image 20260907115642.png]]

## 2. Bảng Độ Phức Tạp (Complexity Sheet)

| Thao Tác                         | Linked List                      | So Với [[Array & Dynamic Array\|Array]] | Ghi Chú                            |
| :------------------------------- | :------------------------------- | :-------------------------------------- | :--------------------------------- |
| **Truy cập qua Index ($k$)**     | [[O(n) - Linear Time\|$O(n)$]]   | 🟢 Array ($O(1)$)                       | Phải duyệt tuần tự từ đầu (`head`) |
| **Tìm kiếm giá trị**             | [[O(n) - Linear Time\|$O(n)$]]   | 🟡 Bằng nhau                            | Duyệt từng node                    |
| **Chèn/Xóa ở đầu (`head`)**      | [[O(1) - Constant Time\|$O(1)$]] | 🔴 Array ($O(n)$)                       | Chỉ cần đổi con trỏ `head`         |
| **Chèn/Xóa tại con trỏ đã biết** | [[O(1) - Constant Time\|$O(1)$]] | 🔴 Array ($O(n)$)                       | Không cần dịch chuyển ô nhớ        |

---

## 3. Sự Đánh Đổi (Trade-offs) & Đối Trọng

- 🟢 **Điểm mạnh (Superpower):**
  - Chèn và xóa cực nhanh trong $O(1)$ khi đã cầm con trỏ tại vị trí đó.
  - Cấp phát bộ nhớ linh hoạt, không yêu cầu vùng nhớ liên tục khổng lồ như Array.
- 🔴 **Điểm yếu (Weakness):**
  - Không hỗ trợ truy cập ngẫu nhiên (Random Access $O(1)$).
  - Tốn thêm bộ nhớ RAM phụ trợ để lưu trữ con trỏ `next` / `prev` cho từng node.
  - Kém thân thiện với CPU Cache (Cache Misses) do các node nằm rải rác trong RAM.
- ⚖️ **Ứng dụng hệ thống:** Doubly Linked List là thành phần cốt lõi tạo nên cấu trúc [[LRU Cache]] siêu tốc khi kết hợp với [[Hash Table & HashSet]].

---

## 4. Đối Chiếu Toàn Diện: Singly (SLL) vs Doubly Linked List (DLL)

### 📊 4.1. Bảng Ma Trận So Sánh Kiến Trúc & Độ Phức Tạp

| Tiêu chí                         | 🟢 Singly Linked List (SLL)                               | 🔵 Doubly Linked List (DLL)                               |
| :------------------------------- | :-------------------------------------------------------- | :-------------------------------------------------------- |
| **Cấu trúc con trỏ**             | 1 con trỏ `next` trỏ tới node sau                         | 2 con trỏ `next` (sau) và `prev` (trước)                  |
| **Chi phí RAM / Node**           | Thấp hơn: `Value + 1 Pointer` (8 bytes)                   | Tốn thêm $100\%$ bộ nhớ: `Value + 2 Pointers` (16 bytes)  |
| **Thêm ở đầu (`prepend`)**       | 🟢 **$O(1)$**                                             | 🟢 **$O(1)$**                                             |
| **Thêm ở cuối (`append`)**       | 🟢 **$O(1)$** (khi có con trỏ `tail`)                     | 🟢 **$O(1)$** (khi có con trỏ `tail`)                     |
| **Xóa ở đầu (`shift`)**          | 🟢 **$O(1)$**                                             | 🟢 **$O(1)$**                                             |
| **Xóa ở cuối (`pop`)**           | 🔴 **$O(n)$** _(Bắt buộc duyệt từ head tìm node kế cuối)_ | 🟢 **$O(1)$** _(Lấy ngay tức thì qua `tail.prev`)_        |
| **Xóa node khi đã có con trỏ**   | 🔴 **$O(n)$** _(Vẫn phải tìm node trước nó)_              | 🟢 **$O(1)$** _(`node.prev.next = node.next`)_            |
| **Tìm kiếm theo vị trí (`get`)** | 🔴 **$O(n)$** _(Chỉ duyệt 1 chiều từ Head)_               | 🟢 **$O(n/2)$** _(Tối ưu duyệt từ đầu hoặc cuối gần hơn)_ |
| **Chiều duyệt danh sách**        | 1 chiều xuôi (`head` $\to$ `tail`)                        | 2 chiều linh hoạt (`head` $\rightleftarrows$ `tail`)      |
| **Ứng dụng hệ thống**            | Stack, Undo 1 chiều đơn giản                              | [[LRU Cache]], Tab duyệt web, Leaf nodes của B+Tree       |

---

### 🔄 4.2. Bảng Tóm Tắt Cơ Chế Thao Tác Con Trỏ

| Thao Tác                      | 🟢 Bản Chất Con Trỏ Singly (SLL)                 | 🔵 Bản Chất Con Trỏ Doubly (DLL)                                     |
| :---------------------------- | :----------------------------------------------- | :------------------------------------------------------------------- |
| **Khai báo Node**             | `this.next = null;`                              | `this.next = null; this.prev = null;`                                |
| **Thêm vào đầu (`prepend`)**  | `newNode.next = head; head = newNode;`           | `newNode.next = head; head.prev = newNode; head = newNode;`          |
| **Thêm vào cuối (`append`)**  | `tail.next = newNode; tail = newNode;`           | `tail.next = newNode; newNode.prev = tail; tail = newNode;`          |
| **Xóa ở đầu (`shift`)**       | `head = head.next;`                              | `head = head.next; head.prev = null;`                                |
| **Xóa ở cuối (`pop`)**        | Duyệt tìm áp chót: `while(curr.next)` $\to O(n)$ | Trỏ ngược tức thời: `tail = tail.prev; tail.next = null;` $\to O(1)$ |
| **Nối cầu khi xóa node giữa** | `beforeNode.next = targetNode.next;`             | `before.next = after; after.prev = before;`                          |

---

### 💻 4.3. So Sánh Mã Nguồn Trọng Tâm (Syntax Highlighted)

#### 1. Cấu Trúc Nút (Node Structure)

> [!NOTE] 🟢 Singly Linked List: Node 1 Chiều
>
> ```javascript
> export class Node {
>   constructor(value) {
>     this.value = value;
>     this.next = null; // 1 con trỏ trỏ về phía trước
>   }
> }
> ```

> [!TIP] 🔵 Doubly Linked List: Node 2 Chiều
>
> ```javascript
> export class Node {
>   constructor(value) {
>     this.value = value;
>     this.next = null; // Con trỏ trỏ tới nút tiếp theo
>     this.prev = null; // Con trỏ trỏ ngược về nút phía trước
>   }
> }
> ```

---

#### 2. Xóa Phần Tử Ở Cuối (`pop`) — Điểm Khác Biệt Chí Mạng ($O(n)$ vs $O(1)$)

> [!NOTE] 🟢 Singly Linked List: $O(n)$ do Bắt Buộc Duyệt Tìm Node Áp Chót
>
> ```javascript
> pop() {
>   if (!this.head) return null;
>   let current = this.head;
>   let newTail = current;
>
>   // Bắt buộc duyệt tuần tự từ đầu để tìm node đứng trước tail
>   while (current.next) {
>     newTail = current;
>     current = current.next;
>   }
>
>   this.tail = newTail;
>   this.tail.next = null;
>   this.length--;
>   if (this.length === 0) {
>     this.head = null;
>     this.tail = null;
>   }
>   return current;
> }
> ```

> [!TIP] 🔵 Doubly Linked List: $O(1)$ Tức Thời Nhờ Con Trỏ `prev`
>
> ```javascript
> pop() {
>   if (!this.tail) return null;
>   const removedNode = this.tail;
>
>   if (this.length === 1) {
>     this.head = null;
>     this.tail = null;
>   } else {
>     // Nhảy lùi 1 bước trong O(1) mà không cần duyệt lại từ đầu
>     this.tail = removedNode.prev;
>     this.tail.next = null;
>     removedNode.prev = null;
>   }
>   this.length--;
>   return removedNode;
> }
> ```

---

#### 3. Truy Cập Theo Vị Trí (`get(index)`) — Tối Ưu Duyệt 2 Đầu

> [!NOTE] 🟢 Singly Linked List: $O(n)$ Duyệt Xuôi 1 Chiều Từ Head
>
> ```javascript
> get(index) {
>   if (index < 0 || index >= this.length) return null;
>   let current = this.head;
>   let count = 0;
>   while (count !== index) {
>     current = current.next;
>     count++;
>   }
>   return current;
> }
> ```

> [!TIP] 🔵 Doubly Linked List: $O(n/2)$ Phân Nhánh Đi Từ Đầu Gần Hơn
>
> ```javascript
> get(index) {
>   if (index < 0 || index >= this.length) return null;
>   let current, count;
>
>   // Nếu index nằm ở nửa đầu: đi từ Head xuôi xuống
>   if (index <= this.length / 2) {
>     count = 0;
>     current = this.head;
>     while (count !== index) {
>       current = current.next;
>       count++;
>     }
>   } else {
>     // Nếu index nằm ở nửa sau: lùi từ Tail ngược lên
>     count = this.length - 1;
>     current = this.tail;
>     while (count !== index) {
>       current = current.prev;
>       count--;
>     }
>   }
>   return current;
> }
> ```

---

#### 4. Đảo Ngược Danh Sách (`reverse()`)

> [!NOTE] 🟢 Singly Linked List: Thuật Toán 3 Con Trỏ (`prev`, `current`, `next`)
>
> ```javascript
> reverse() {
>   let current = this.head;
>   this.head = this.tail;
>   this.tail = current;
>
>   let prev = null;
>   let next = null;
>   while (current !== null) {
>     next = current.next; // 1. Giữ liên kết tới node sau
>     current.next = prev; // 2. Bẻ cong con trỏ quay về trước
>     prev = current;      // 3. Tịnh tiến prev
>     current = next;      // 4. Tịnh tiến current
>   }
>   return this;
> }
> ```

> [!TIP] 🔵 Doubly Linked List: Hoán Đổi Hai Con Trỏ `next` $\rightleftarrows$ `prev`
>
> ```javascript
> reverse() {
>   if (!this.head) return this;
>   let current = this.head;
>   this.head = this.tail;
>   this.tail = current;
>
>   let next = null;
>   while (current !== null) {
>     next = current.next;
>     current.next = current.prev; // Hoán đổi next thành prev
>     current.prev = next;         // Hoán đổi prev thành next
>     current = next;
>   }
>   return this;
> }
> ```

---

## 📂 5. Cấu Trúc Dự Án & Mã Nguồn Đầy Đủ (Full Implementation)

### 🗂️ 5.1. Tổ Chức Thư Mục Mã Nguồn (Modular Architecture)

Để dễ bảo trì và tái sử dụng, mã nguồn được chia tách thành các module chuyên biệt:

```text
📦 linked-list-project/
├── 📄 Node.js               # Định nghĩa cấu trúc Nút (Node 1 chiều & 2 chiều)
├── 📄 SinglyLinkedList.js   # Class quản trị Danh sách liên kết đơn
├── 📄 DoublyLinkedList.js   # Class quản trị Danh sách liên kết đôi (Tối ưu duyệt 2 đầu)
└── 🚀 index.js              # Kịch bản kiểm thử, in kết quả & so sánh hiệu năng
```

---

### 🟢 5.2. Singly Linked List (`SinglyLinkedList.js`)

> [!abstract] 📋 Bảng Tra Cứu Nhanh Các Phương Thức (API Reference)
>
> | Phương thức        | Tham số      | Giá trị trả về | Độ phức tạp | Mô tả bản chất                                  |
> | :----------------- | :----------- | :------------- | :---------: | :---------------------------------------------- |
> | `prepend(val)`     | `value`      | `this`         |   $O(1)$    | Nối vào trước `head`, cập nhật `head` mới       |
> | `append(val)`      | `value`      | `this`         |   $O(1)$    | Nối vào sau `tail`, cập nhật `tail` mới         |
> | `insertAt(k, val)` | `index, val` | `boolean`      |   $O(n)$    | Tìm node thứ $k-1$, bẻ nhánh trỏ qua node mới   |
> | `shift()`          | _không_      | `Node \| null` |   $O(1)$    | Nhấc bỏ node `head`, dịch `head` sang node sau  |
> | `pop()`            | _không_      | `Node \| null` |  🔴 $O(n)$  | Bắt buộc lặp tìm node kế cuối để ngắt đuôi      |
> | `removeAt(k)`      | `index`      | `Node \| null` |   $O(n)$    | Nối tắt node $k-1$ sang node $k+1$              |
> | `get(k)`           | `index`      | `Node \| null` |   $O(n)$    | Duyệt tuần tự 1 chiều từ `head`                 |
> | `set(k, val)`      | `index, val` | `boolean`      |   $O(n)$    | Lấy node qua `get(k)` và gán lại giá trị        |
> | `reverse()`        | _không_      | `this`         |   $O(n)$    | Thuật toán 3 con trỏ đảo ngược toàn bộ liên kết |
> | `print()`          | _không_      | `void`         |   $O(n)$    | In trực quan chuỗi: `A -> B -> C`               |

> [!example]- 💻 Bấm để xem mã nguồn chi tiết: `SinglyLinkedList.js`
>
> ```javascript
> // SinglyLinkedList.js
>
> export class Node {
>   constructor(value) {
>     this.value = value;
>     this.next = null;
>   }
> }
>
> export class SinglyLinkedList {
>   constructor() {
>     this.head = null;
>     this.tail = null;
>     this.length = 0;
>   }
>
>   // 1. Thêm vào cuối - O(1)
>   append(value) {
>     const newNode = new Node(value);
>     if (!this.head) {
>       this.head = newNode;
>       this.tail = newNode;
>     } else {
>       this.tail.next = newNode;
>       this.tail = newNode;
>     }
>     this.length++;
>     return this;
>   }
>
>   // 2. Thêm vào đầu - O(1)
>   prepend(value) {
>     const newNode = new Node(value);
>     if (!this.head) {
>       this.head = newNode;
>       this.tail = newNode;
>     } else {
>       newNode.next = this.head;
>       this.head = newNode;
>     }
>     this.length++;
>     return this;
>   }
>
>   // 3. Chèn vào vị trí bất kỳ - O(n)
>   insertAt(index, value) {
>     if (index < 0 || index > this.length) return false;
>     if (index === 0) return !!this.prepend(value);
>     if (index === this.length) return !!this.append(value);
>
>     const newNode = new Node(value);
>     const prevNode = this.get(index - 1);
>     newNode.next = prevNode.next;
>     prevNode.next = newNode;
>     this.length++;
>     return true;
>   }
>
>   // 4. Xóa ở đầu - O(1)
>   shift() {
>     if (!this.head) return null;
>     const removedNode = this.head;
>     this.head = this.head.next;
>     removedNode.next = null;
>     this.length--;
>     if (this.length === 0) this.tail = null;
>     return removedNode;
>   }
>
>   // 5. Xóa ở cuối - O(n) do phải tìm node kế cuối
>   pop() {
>     if (!this.head) return null;
>     let current = this.head;
>     let newTail = current;
>
>     while (current.next) {
>       newTail = current;
>       current = current.next;
>     }
>
>     this.tail = newTail;
>     this.tail.next = null;
>     this.length--;
>
>     if (this.length === 0) {
>       this.head = null;
>       this.tail = null;
>     }
>     return current;
>   }
>
>   // 6. Xóa tại vị trí bất kỳ - O(n)
>   removeAt(index) {
>     if (index < 0 || index >= this.length) return null;
>     if (index === 0) return this.shift();
>     if (index === this.length - 1) return this.pop();
>
>     const prevNode = this.get(index - 1);
>     const removedNode = prevNode.next;
>     prevNode.next = removedNode.next;
>     removedNode.next = null;
>     this.length--;
>     return removedNode;
>   }
>
>   // 7. Lấy node tại vị trí index - O(n)
>   get(index) {
>     if (index < 0 || index >= this.length) return null;
>     let current = this.head;
>     let count = 0;
>     while (count !== index) {
>       current = current.next;
>       count++;
>     }
>     return current;
>   }
>
>   // 8. Cập nhật giá trị node - O(n)
>   set(index, value) {
>     const foundNode = this.get(index);
>     if (foundNode) {
>       foundNode.value = value;
>       return true;
>     }
>     return false;
>   }
>
>   // 9. Đảo ngược danh sách (3 con trỏ) - O(n) time, O(1) space
>   reverse() {
>     let current = this.head;
>     this.head = this.tail;
>     this.tail = current;
>
>     let prev = null;
>     let next = null;
>     while (current !== null) {
>       next = current.next;
>       current.next = prev;
>       prev = current;
>       current = next;
>     }
>     return this;
>   }
>
>   // 10. In danh sách ra console
>   print() {
>     const arr = [];
>     let current = this.head;
>     while (current) {
>       arr.push(current.value);
>       current = current.next;
>     }
>     console.log(arr.join(" -> "));
>   }
> }
> ```

---

### 🔵 5.3. Doubly Linked List (`DoublyLinkedList.js`)

> [!abstract] 📋 Bảng Tra Cứu Nhanh Các Phương Thức (API Reference)
>
> | Phương thức        | Tham số      | Giá trị trả về |   Độ phức tạp   | Mô tả bản chất                                           |
> | :----------------- | :----------- | :------------- | :-------------: | :------------------------------------------------------- |
> | `prepend(val)`     | `value`      | `this`         |     $O(1)$      | Nối 2 chiều vào trước `head`                             |
> | `append(val)`      | `value`      | `this`         |     $O(1)$      | Nối 2 chiều vào sau `tail`                               |
> | `insertAt(k, val)` | `index, val` | `boolean`      |   🟢 $O(n/2)$   | Tận dụng `get(k)` thông minh để chèn 4 mối nối           |
> | `shift()`          | _không_      | `Node \| null` |     $O(1)$      | Xóa `head`, ngắt liên kết `prev` của `head` mới          |
> | `pop()`            | _không_      | `Node \| null` |  🟢 **$O(1)$**  | Lùi `tail = tail.prev` tức thời nhờ con trỏ `prev`       |
> | `removeAt(k)`      | `index`      | `Node \| null` |   🟢 $O(n/2)$   | Bỏ qua node mục tiêu: nối `before.next` và `after.prev`  |
> | `get(k)`           | `index`      | `Node \| null` | 🟢 **$O(n/2)$** | Phân nhánh: đi từ `head` hoặc lùi từ `tail`              |
> | `set(k, val)`      | `index, val` | `boolean`      |   🟢 $O(n/2)$   | Cập nhật giá trị node với tốc độ gấp đôi SLL             |
> | `reverse()`        | _không_      | `this`         |     $O(n)$      | Hoán đổi vị trí con trỏ `next` $\rightleftarrows$ `prev` |
> | `printForward()`   | _không_      | `void`         |     $O(n)$      | In xuôi từ `head`: `A <-> B <-> C`                       |
> | `printBackward()`  | _không_      | `void`         |     $O(n)$      | In ngược từ `tail`: `C <-> B <-> A`                      |

> [!tip]- 💻 Bấm để xem mã nguồn chi tiết: `DoublyLinkedList.js`
>
> ```javascript
> // DoublyLinkedList.js
>
> export class Node {
>   constructor(value) {
>     this.value = value;
>     this.next = null;
>     this.prev = null;
>   }
> }
>
> export class DoublyLinkedList {
>   constructor() {
>     this.head = null;
>     this.tail = null;
>     this.length = 0;
>   }
>
>   // 1. Thêm vào cuối - O(1)
>   append(value) {
>     const newNode = new Node(value);
>     if (this.length === 0) {
>       this.head = newNode;
>       this.tail = newNode;
>     } else {
>       this.tail.next = newNode;
>       newNode.prev = this.tail;
>       this.tail = newNode;
>     }
>     this.length++;
>     return this;
>   }
>
>   // 2. Thêm vào đầu - O(1)
>   prepend(value) {
>     const newNode = new Node(value);
>     if (this.length === 0) {
>       this.head = newNode;
>       this.tail = newNode;
>     } else {
>       this.head.prev = newNode;
>       newNode.next = this.head;
>       this.head = newNode;
>     }
>     this.length++;
>     return this;
>   }
>
>   // 3. Chèn vào vị trí bất kỳ - O(n/2)
>   insertAt(index, value) {
>     if (index < 0 || index > this.length) return false;
>     if (index === 0) return !!this.prepend(value);
>     if (index === this.length) return !!this.append(value);
>
>     const newNode = new Node(value);
>     const beforeNode = this.get(index - 1);
>     const afterNode = beforeNode.next;
>
>     beforeNode.next = newNode;
>     newNode.prev = beforeNode;
>     newNode.next = afterNode;
>     afterNode.prev = newNode;
>
>     this.length++;
>     return true;
>   }
>
>   // 4. Xóa ở cuối - O(1) siêu tốc
>   pop() {
>     if (!this.tail) return null;
>     const removedNode = this.tail;
>
>     if (this.length === 1) {
>       this.head = null;
>       this.tail = null;
>     } else {
>       this.tail = removedNode.prev;
>       this.tail.next = null;
>       removedNode.prev = null;
>     }
>     this.length--;
>     return removedNode;
>   }
>
>   // 5. Xóa ở đầu - O(1)
>   shift() {
>     if (!this.head) return null;
>     const removedNode = this.head;
>
>     if (this.length === 1) {
>       this.head = null;
>       this.tail = null;
>     } else {
>       this.head = removedNode.next;
>       this.head.prev = null;
>       removedNode.next = null;
>     }
>     this.length--;
>     return removedNode;
>   }
>
>   // 6. Xóa tại vị trí bất kỳ - O(n/2)
>   removeAt(index) {
>     if (index < 0 || index >= this.length) return null;
>     if (index === 0) return this.shift();
>     if (index === this.length - 1) return this.pop();
>
>     const removedNode = this.get(index);
>     const beforeNode = removedNode.prev;
>     const afterNode = removedNode.next;
>
>     beforeNode.next = afterNode;
>     afterNode.prev = beforeNode;
>     removedNode.next = null;
>     removedNode.prev = null;
>     this.length--;
>     return removedNode;
>   }
>
>   // 7. Tìm kiếm 2 đầu tối ưu - O(n/2)
>   get(index) {
>     if (index < 0 || index >= this.length) return null;
>     let current, count;
>
>     // Nếu index thuộc nửa đầu: đi từ head xuôi xuống
>     if (index <= this.length / 2) {
>       count = 0;
>       current = this.head;
>       while (count !== index) {
>         current = current.next;
>         count++;
>       }
>     } else {
>       // Nếu index thuộc nửa sau: lùi từ tail ngược lên
>       count = this.length - 1;
>       current = this.tail;
>       while (count !== index) {
>         current = current.prev;
>         count--;
>       }
>     }
>     return current;
>   }
>
>   // 8. Cập nhật giá trị node - O(n/2)
>   set(index, value) {
>     const foundNode = this.get(index);
>     if (foundNode) {
>       foundNode.value = value;
>       return true;
>     }
>     return false;
>   }
>
>   // 9. Đảo ngược danh sách - O(n)
>   reverse() {
>     if (!this.head) return this;
>     let current = this.head;
>     this.head = this.tail;
>     this.tail = current;
>
>     let next = null;
>     while (current !== null) {
>       next = current.next;
>       current.next = current.prev;
>       current.prev = next;
>       current = next;
>     }
>     return this;
>   }
>
>   // 10. In xuôi
>   printForward() {
>     const arr = [];
>     let current = this.head;
>     while (current) {
>       arr.push(current.value);
>       current = current.next;
>     }
>     console.log("Xuôi  :", arr.join(" <-> "));
>   }
>
>   // 11. In ngược
>   printBackward() {
>     const arr = [];
>     let current = this.tail;
>     while (current) {
>       arr.push(current.value);
>       current = current.prev;
>     }
>     console.log("Ngược :", arr.join(" <-> "));
>   }
> }
> ```

---

### 🚀 5.4. Kịch Bản Chạy Thử Nghiệm (`index.js`)

> [!note]- 🧪 Bấm để xem code chạy thử và output console: `index.js`
>
> ```javascript
> // index.js
> import { SinglyLinkedList } from "./SinglyLinkedList.js";
> import { DoublyLinkedList } from "./DoublyLinkedList.js";
>
> console.log("=== 1. TEST SINGLY LINKED LIST ===");
> const sll = new SinglyLinkedList();
> sll.append(10).append(20).append(30);
> sll.prepend(5);
> sll.print(); // 5 -> 10 -> 20 -> 30
>
> sll.pop(); // Xóa 30 trong O(n)
> sll.print(); // 5 -> 10 -> 20
>
> sll.reverse();
> sll.print(); // 20 -> 10 -> 5
>
> console.log("\n=== 2. TEST DOUBLY LINKED LIST ===");
> const dll = new DoublyLinkedList();
> dll.append("Node A").append("Node B").append("Node C");
> dll.prepend("Head Root");
> dll.printForward(); // Xuôi  : Head Root <-> Node A <-> Node B <-> Node C
> dll.printBackward(); // Ngược : Node C <-> Node B <-> Node A <-> Head Root
>
> dll.pop(); // Xóa "Node C" tức thời trong O(1)!
> dll.printForward(); // Xuôi  : Head Root <-> Node A <-> Node B
>
> dll.reverse();
> dll.printForward(); // Xuôi  : Node B <-> Node A <-> Head Root
> ```

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)

Tại sao việc chèn/xóa ở đầu Linked List lại đạt $O(1)$ trong khi Array mất $O(n)$? #card
?
Vì Linked List chỉ cần gán lại con trỏ `new_node.next = head` và cập nhật `head = new_node` (1 phép gán), không cần dịch chuyển bất kỳ phần tử nào khác trong RAM.
Khi nào nên ưu tiên dùng Doubly Linked List hơn Singly Linked List? #card
?
Khi cần duyệt hoặc xóa node theo cả 2 chiều, hoặc khi xây dựng các cấu trúc như [[LRU Cache]] và [[Queue & Deque|Deque]] yêu cầu xóa một node đã biết trong $O(1)$ mà không cần duyệt lại từ đầu để tìm node phía trước.
