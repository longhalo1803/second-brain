---
title: Computer Networks & Protocols MOC
tags:
  - backend
  - moc
  - networks
type: moc
status: completed
created: 2026-09-25
updated: 2026-09-30
aliases:
  - Computer Networks & Protocols MOC
  - Backend Networks Hub
---

# 📁 Computer Networks & Protocols MOC (Backend Engineering)

> **Điều hướng**: [[00 - Master Dashboard|🧭 Backend Dashboard]] | [[Roadmap - Backend Full Course|📋 Backend Roadmap]] | [[00 - Master Knowledge Hub|🌐 Master Hub]]

Chuyên đề này tập trung vào các **Giao thức Mạng tầng Giao vận & Ứng dụng (L4–L7)** dưới lăng kính của Kỹ sư Backend (Socket Programming, API Design, Streaming & High-Throughput I/O).

> [!NOTE]
> **Cầu Nối Sang Khóa Học Hạ Tầng Mạng CCNA**:
> Đối với toàn bộ kiến thức chuyên sâu về **Hạ tầng mạng vật lý, Chuyển mạch Layer 2 (VLAN, STP, EtherChannel), Định tuyến Layer 3 (OSPF, BGP, Subnetting VLSM), và Vận hành Thiết bị Cisco**, vui lòng truy cập khóa học độc lập:
> 👉 **[[Network-CCNA/00 - Maps of Content/00 - Master Dashboard|🌐 Khóa Học Network-CCNA (Cisco 200-301 Master Hub)]]**

---

## 📊 Bảng Tra Cứu Toàn Diện

- **[[Table|📊 Bảng Tra Cứu Toàn Diện 20 Giao Thức Mạng Cho Backend]]**

---

## 📚 Danh Mục Giao Thức Theo Phân Lớp

### 1. Tầng Giao Vận & Lõi (Core Transport & Routing)

- [[Core Transport & Routing/TCP - IP|TCP - IP]]: Bắt tay 3 bước, điều khiển luồng, chống tắc nghẽn.
- [[Core Transport & Routing/UDP|UDP]]: Giao thức phi kết nối, tối ưu cho thời gian thực và streaming.
- [[Core Transport & Routing/QUIC|QUIC]]: Nền tảng của HTTP/3, giảm 0-RTT, khắc phục Head-of-Line Blocking.
- [[Core Transport & Routing/BGP|BGP]]: Định tuyến Path-Vector liên miền giữa các Autonomous Systems.

### 2. Giao Thức Web & Ứng Dụng (Web & Remote Protocols)

- [[Web & Remote Protocols/HTTP - HTTPS|HTTP - HTTPS]]: REST APIs, phân biệt HTTP/1.1 vs HTTP/2 vs HTTP/3.
- [[Web & Remote Protocols/WebSocket|WebSocket]]: Kết nối hai chiều Full-duplex thời gian thực.

### 3. Giao Thức Bảo Mật (Security Protocols)

- [[Security Protocols/TLS|TLS]]: Mật mã lai (ECDHE, AES-GCM), tiêu chuẩn bảo vệ HTTPS.
- [[Security Protocols/SSL|SSL]]: Tiền thân lỗi thời của TLS (Hiện bị cấm tuyệt đối).
- [[Security Protocols/SSH|SSH]]: Giao thức kết nối và mã hóa quản trị máy chủ từ xa.

### 4. Quản Trị Hệ Thống & Phân Giải Mạng (Network & System Management)

- [[Network & System Management/DNS|DNS]]: Hệ thống phân giải tên miền ra IP.
- [[Network & System Management/DHCP|DHCP]]: Giao thức cấp phát địa chỉ IP động.
- [[Network & System Management/NTP|NTP]]: Đồng bộ thời gian phân tán cho cơ sở dữ liệu và bảo mật.
- [[Network & System Management/ARP|ARP]]: Ánh xạ địa chỉ IP sang địa chỉ vật lý MAC trong mạng LAN.
- [[Network & System Management/ICMP|ICMP]]: Giao thức chẩn đoán mạng (Ping, Traceroute).
- [[Network & System Management/SNMP|SNMP]]: Giám sát tình trạng phần cứng và thiết bị mạng.
- [[Network & System Management/RIP & OSPF|RIP & OSPF]]: Các giao thức định tuyến nội miền (IGP).

### 5. Truyền Tải Tệp Tin (File Transfer Protocols)

- [[File Transfer Protocols/FTP|FTP]]: Truyền tệp truyền thống qua cổng 21/20 (Clear text).
- [[File Transfer Protocols/FTPS|FTPS]]: Truyền tệp bảo mật qua lớp mã hóa TLS.
- [[File Transfer Protocols/SFTP|SFTP]]: Truyền tệp an toàn chạy qua tầng giao vận SSH.
