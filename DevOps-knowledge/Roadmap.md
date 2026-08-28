[]()![[Pasted image 20260619091959.png|532]]

Khóa học "DevOps Engineer in 3 Months" được thiết kế nhằm giúp bạn trang bị đầy đủ kỹ năng để có thể sẵn sàng làm việc (job-ready) trong vòng 3 tháng. Dưới đây là lộ trình chi tiết các bước bạn cần trải qua dựa trên hệ thống các bài học:

**1. Kiến thức Nền tảng và Mạng (Fundamentals & Networking)**

- Nắm vững các khái niệm cơ bản về DevOps và cách cải thiện vòng đời phát triển phần mềm (SDLC).
- **Hệ điều hành Linux:** Hiểu cấu trúc thư mục, quản lý người dùng, quản lý file, phân quyền, quản lý tiến trình, mạng, ổ đĩa và các phím tắt trình soạn thảo Vi.
- **Mạng (Networking):** Làm quen với các khái niệm mạng cơ bản và nắm rõ Mô hình OSI.

**2. Máy ảo và Kịch bản Vỏ (Virtual Machines & Shell Scripting)**

- **Máy ảo (Virtual Machines):** Khái niệm nền tảng về máy ảo, cách tạo máy ảo trên AWS/Azure, giao diện dòng lệnh AWS CLI và cách kết nối vào máy chủ EC2 (ví dụ thông qua Mobaxterm).
- **Shell Scripting:** Nắm vững việc viết kịch bản Linux Shell (từ con số 0 đến thành thạo) và ứng dụng thực tế vào dự án AWS.

**3. Quản lý Mã nguồn (Version Control)**

- Sử dụng **Git và GitHub/GitLab**, hiểu rõ các khái niệm về kiểm soát phiên bản.
- Nắm vững chiến lược phân nhánh Git (Git Branching Strategy) trong môi trường làm việc thực tế và cách triển khai, đưa ứng dụng đầu tiên của bạn lên môi trường AWS.

**4. Điện toán Đám mây (Cloud Computing - AWS & Azure)**

- **AWS Nâng cao:** Nắm vững Top 15 dịch vụ AWS quan trọng nhất cho kỹ sư DevOps. Bạn sẽ phải đi sâu vào các dịch vụ từ cơ bản đến quản trị kiến trúc như: IAM, EC2, VPC, Security Group & NACL, Route53, và S3 Buckets.
- **Kiến trúc đám mây thực tế:** Tìm hiểu cách triển khai kiến trúc 3 tầng (Three-tier Architecture), thiết lập bộ cân bằng tải (ALB, NLB, GWLB), CloudFront (CDN), quản lý container với ECR/ECS, và dịch vụ phi máy chủ (Serverless) thông qua AWS Lambda. Theo dõi hệ thống qua CloudWatch và quản lý cấu hình bằng AWS Config.
- **Nhập môn Azure:** Làm quen với các nguyên tắc cơ bản của Azure Cloud, Resource, Resource Groups và Azure Resource Manager.

**5. Cơ sở Hạ tầng dưới dạng Mã & Quản lý Cấu hình (IaC & Configuration Management)**

- **Ansible:** Học quản lý cấu hình từ cơ bản đến nâng cao (so sánh với Puppet) và thực hành trên các dự án trực tiếp.
- **Terraform & AWS CFT:** Viết cơ sở hạ tầng dưới dạng mã (IaC). Học cách dùng Terraform (tạo dự án, Remote Backend, Modules) và AWS CloudFormation (CFT) để quản trị tài nguyên tự động.

**6. Vận hành và Điều phối Container (Docker & Kubernetes)**

- **Docker:** Học cách đóng gói ứng dụng (Containerization, ví dụ với Django), tối ưu giảm 800% dung lượng image với Multi Stage Builds. Quản lý lưu trữ qua Docker Volumes/Bind Mounts và nắm rõ các loại mạng Docker Networking (Bridge, Host, Overlay).
- **Kubernetes (K8s):** Bắt đầu với kiến trúc tổng thể, học cách quản lý hàng trăm cluster qua KOPS. Triển khai ứng dụng qua Pods, ReplicaSets, Deployments, Services (Load Balancing, Discovery), và Ingress.
- **K8s Nâng cao:** Áp dụng hệ thống phân quyền K8s RBAC, Custom Resources, ConfigMaps, Secrets, và học cách giám sát hệ thống bằng Prometheus & Grafana.

**7. Tích hợp và Triển khai Liên tục (CI/CD)**

- Hiểu nền tảng hệ thống CI/CD là gì và cách nó hoạt động.
- Sử dụng **Jenkins** với Docker Agent và áp dụng quy trình GitOps vào dự án.
- Sử dụng **GitHub Actions** (so sánh với Jenkins) và tự cấu hình runner.
- **AWS CI/CD Pipeline:** Xây dựng hệ thống pipeline xuyên suốt trên AWS bằng CodeCommit, CodePipeline.

**8. Quản lý dự án & Chuẩn bị phỏng vấn**

- Làm quen với các công cụ quản lý dự án dành cho DevOps và hiểu rõ kỹ sư DevOps phải làm gì trong tuần đầu tiên nhận việc.
- Thông qua khóa học, bạn cũng sẽ được rèn luyện bộ câu hỏi phỏng vấn thực tế cho từng chuyên đề trọng tâm: Shell Scripting, Git, Terraform, Docker, Kubernetes, AWS, và CI/CD.
