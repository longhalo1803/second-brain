---
title: Master Knowledge Hub (Obsidian Second Brain)
aliases:
  - Master Hub
  - Trang chủ
  - Knowledge Dashboard
  - Home
tags:
  - meta
  - dashboard
  - moc
type: moc
created: 2026-08-28
updated: 2026-08-28
---

# 🌐 Computer Science & AI Master Knowledge Hub

> **Trung tâm điều hướng tổng quan toàn bộ hệ sinh thái tri thức (Second Brain).**
> Được tối ưu hóa cho đồ thị liên kết hai chiều (**Graph View**), tra cứu nhanh và tự học chuyên sâu theo **Alvar Method (First Principles)** cùng **Antigravity CLI**.

---

## 🗺️ 1. Bản Đồ Liên Kết Đa Miền (Cross-Domain Graph)

```mermaid
flowchart TD
    Hub(["🌐 MASTER KNOWLEDGE HUB"]):::main

    subgraph D1["🧠 AI & AGENTIC ENGINEERING"]
        AI["AI Knowledge Hub"]
        AI_F["Context RAM & LLM Attention"]
        AI_M["Tri-Memory & RAG Systems"]
        AI_H["Agent Harness & Tool Loops"]
    end

    subgraph D2["⚙️ BACKEND & PROTOCOLS"]
        BE["Backend Roadmap"]
        BE_P["TCP/IP, UDP, QUIC, BGP"]
        BE_W["HTTP/HTTPS, WebSocket, TLS/SSL"]
        BE_S["System Design & APIs"]
    end

    subgraph D3["🗄️ DATABASE ENGINE & TUNING"]
        DB["Database Overview MOC"]
        DB_S["Disk Block, Page, Buffer Cache & WAL"]
        DB_O["Index B+Tree & Cost Optimizer"]
        DB_L["Lock, MVCC & Deadlock"]
    end

    subgraph D4["🧭 DSA & ALGORITHMIC THINKING"]
        DSA["DSA Master MOC"]
        DSA_M["Big-O Notation & Mental Models"]
        DSA_S["Linear, Trees, Graphs & DSU"]
        DSA_P["LeetCode Algorithmic Patterns"]
    end

    subgraph D5["🚀 DEVOPS & INFRASTRUCTURE"]
        DO["DevOps Roadmap"]
        DO_C["Docker & Containerization"]
        DO_K["Kubernetes (K8s) & IaC (Terraform)"]
        DO_P["CI/CD Pipeline & Monitoring"]
    end

    subgraph D6["🌐 NETWORK & CCNA 200-301"]
        NET["CCNA Master Dashboard"]
        NET_L2["Switching: VLAN, Trunk, RSTP, EtherChannel"]
        NET_L3["Routing: IPv4/v6 Subnetting, OSPFv2, NAT"]
        NET_SEC["Security & Automation: ACL, Snooping, DNA-C"]
    end

    %% Hub to Domains
    Hub ==> AI
    Hub ==> BE
    Hub ==> DB
    Hub ==> DSA
    Hub ==> DO
    Hub ==> NET

    %% Cross-Domain Links
    AI -.->|Vector Search và Retrieval| DB
    BE -.->|Storage và Query Execution| DB
    DB -.->|B+Tree, Hash, LRU Cache| DSA
    BE -.->|Microservices và Ingress| DO
    AI -.->|Tool Calling và MCP Server| BE
    NET -.->|L2/L3 Underlay và Transport| BE
    NET -.->|Campus Infrastructure và VPC| DO

    classDef main fill:#1e293b,stroke:#38bdf8,stroke-width:3px,color:#f8fafc,font-weight:bold;
```

---

## 📚 2. Điều Hướng 6 Trụ Cột Tri Thức (Domain Modules)

| Trụ cột                  | Bản đồ trung tâm (MOC / Roadmap)                                                                | Lĩnh vực trọng tâm                                                                    |
| :----------------------- | :---------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------ |
| 🧠 **AI & LLMOps**       | [[AI-knowledge/00 - MOC (Map of Content)\|🗺️ MOC - AI Knowledge Hub]]                           | Context RAM, Tri-Memory, PydanticAI, MCP, LangGraph, LLM-as-a-Judge, Continuous Eval. |
| 🗄️ **Database Engine**   | [[Database-knowledge/00 - Maps of Content/MOC - Database Overview\|🗺️ MOC - Database Overview]] | Disk I/O, Buffer Cache, B+Tree Index, Cost Optimizer, Lock & Deadlock, MVCC.          |
| 🧭 **DSA & Patterns**    | [[DSA-learn/00 - Meta & Maps/Master MOC\|🗺️ Master MOC - DSA]]                                  | Big-O, Mental Models, Data Structures, Algorithms, Two Pointers, Sliding Window, DP.  |
| ⚙️ **Backend Protocols** | [[Backend-full-course/Roadmap\|📋 Roadmap - Backend Engineering]]                               | TCP/IP, UDP, QUIC, BGP, WebSocket, HTTP/3, TLS/SSL, DNS, SFTP/SSH.                    |
| 🚀 **DevOps & Cloud**    | [[DevOps-knowledge/Roadmap\|📋 Roadmap - DevOps & Cloud Native]]                                | Linux Kernel, Docker Multi-stage, Kubernetes Ingress, Terraform IaC, Prometheus.      |
| 🌐 **Network & CCNA**    | [[Network-CCNA/00 - Maps of Content/00 - Master Dashboard\|📋 MOC - Network & Cisco CCNA]]      | OSI, Switching L2 (VLAN, STP), Routing L3 (OSPF, NAT), ACL, DNA-C, Packet Tracer.    |

---

## ⚡ 3. Hướng Dẫn Tra Cứu & Học Tập Nhanh

- **Mở nhanh bất kỳ ghi chú nào:** Nhấn `Ctrl + O` (hoặc `Cmd + O` trên macOS) và gõ tên khái niệm.
- **Tìm kiếm toàn cục:** Nhấn `Ctrl + Shift + F` để tìm kiếm trên toàn bộ 5 mảng kiến thức.
- **Xem đồ thị liên kết:** Nhấn `Ctrl + G` để mở **Graph View** toàn cục.
- **Quy chuẩn nạp tri thức mới:** Xem chi tiết tại [[README#📐 5. Quy Định Chung Khi Nạp Tri Thức (Universal Specification)|Universal Specification trong README.md]].
- **Quy trình học tương tác cùng AI CLI:** Xem chi tiết tại [[docs/WORKFLOW_AI_LEARNING_OBSIDIAN|Workflow Học Tập agy CLI]].
