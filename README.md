# Đánh giá an ninh hệ thống Firewall và IDS bằng Snort & Iptables

## Giới thiệu đồ án
Dự án nghiên cứu và triển khai hệ thống phòng thủ đa lớp trên môi trường mạng ảo hóa Linux. Mô hình kết hợp sức mạnh ngăn chặn gói tin trực tiếp của Iptables (Firewall) và khả năng giám sát, phân tích chuyên sâu cảnh báo xâm nhập của Snort (IDS).

## Mô hình mạng thực nghiệm (Network Topology)
Hệ thống được thiết lập trên nền tảng VMware Workstation, phân tách luồng dữ liệu thành 3 vùng mạng biệt lập:
* **Vùng không tin cậy (Attacker):** Máy ảo Kali Linux (IP: 192.168.232.50) đóng vai trò kẻ tấn công bên ngoài.
* **Vùng kiểm soát (Gateway):** Máy ảo Ubuntu Server (IP ngoài: 192.168.232.1 | IP trong: 10.0.0.1) làm cổng giao tiếp, được cấu hình Netplan và Iptables/Snort.
* **Vùng được bảo vệ (Victim):** Máy ảo Windows (IP: 10.0.0.10) đóng vai trò là máy trạm mạng nội bộ.

## Công nghệ & Giao thức áp dụng
* **Hệ điều hành:** Ubuntu Server, Kali Linux, Windows.
* **Bảo mật:** Iptables (Packet Filtering), Snort (Network-based IDS).
* **Giao thức phân tích:** TCP/IP, ICMP.

## Tính năng & Kết quả đạt được
* Cấu hình thành công định tuyến tĩnh (Static Route) và tính năng chuyển tiếp gói tin (IP Forwarding) giữa các phân vùng.
* Thiết lập luật tùy chỉnh (local.rules) cho Snort để tự động nhận diện và cảnh báo các gói tin ICMP (Ping) khả nghi từ Kali Linux.
* Phát hiện và ghi log thành công hành vi quét cổng chuyên sâu bằng công cụ Nmap.

## 📂 Tài liệu & Demo
* [Xem báo cáo cấu hình chi tiết (PDF)]
* [Xem Video Demo thực tế hệ thống](https://youtu.be/NGW7gABLz1o)
