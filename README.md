# Thiết kế và Triển khai Hệ thống Mạng Doanh nghiệp Đa tầng

> **Đạt kết quả đánh giá 9.0/10.Các bạn tham khảo nếu sai thi phản hồi cho mình với nha**
> Triển khai mô phỏng hạ tầng mạng hiện đại trên Cisco Packet Tracer, tập trung vào tính bảo mật và khả năng mở rộng.

##  Mục tiêu Dự án
Thiết kế toàn diện hạ tầng kết nối vật lý và logic cho doanh nghiệp. Đảm bảo các phòng ban (Ban Giám đốc, Kế toán, Kỹ thuật, Nhân sự) vận hành biệt lập nhưng vẫn có thể giao tiếp thông qua chính sách bảo mật định sẵn.
<img width="1121" height="556" alt="SoDoMang" src="https://github.com/user-attachments/assets/ffdac566-70d8-4b30-b03c-7e10c99231e5" />

##  Giải pháp Kỹ thuật & Các bước triển khai
Dự án được thực hiện tuần tự qua các giai đoạn cốt lõi:

1. **Quản trị hạ tầng (Tầng 2):** Sử dụng **VTP** để đồng bộ hóa cơ sở dữ liệu VLAN (từ VLAN 2 đến VLAN 7) trên toàn hệ thống Switch.
2. **Định tuyến (Tầng 3):** Thiết lập **Inter-VLAN Routing** trên Router (SV_DinhHuuTriet) giúp thông suốt luồng dữ liệu nội bộ.
3. **Kết nối Internet (NAT):** 
   - **NAT Overload:** Cho phép toàn hệ thống truy cập mạng PUBLIC.
   - **Static NAT:** Ánh xạ riêng máy PC9 qua IP Public tĩnh `90.90.90.90`.
4. **Bảo mật hệ thống (ACL):**
   - Chặn **VLAN 2 (Ban Giám đốc)** truy cập vào **Server 1** (`192.168.9.10`) để bảo vệ dữ liệu nhạy cảm.
   - Chặn máy **PC10** truy cập dịch vụ Web trên **Server 0** (`192.168.10.10`).

##  Quy hoạch địa chỉ IP 

<img width="949" height="397" alt="z7778662782979_9acc0d20d49dcfc93446f6a4099605f1" src="https://github.com/user-attachments/assets/d5722998-c190-4090-a654-771ca1fdc6ed" />

##  Cấu trúc thư mục
├── lab_files/         # File mô phỏng (.pkt)
├── documentation/     # Báo cáo chi tiết (.pdf/.docx)
└── topology/          # Hình ảnh sơ đồ mạng thực tế
