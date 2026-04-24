# HỆ THỐNG ĐIỀU KHIỂN CẤP NƯỚC TÒA NHÀ CAO TẦNG (PROFINET-BASED)

Dự án triển khai giải pháp điều khiển cấp nước tự động cho hạ tầng tòa nhà cao tầng, sử dụng giao thức truyền thông công nghiệp **Profinet** để kết nối PLC trung tâm với các trạm **Remote I/O**. Hệ thống đảm bảo tính ổn định cao, tối ưu hóa năng lượng và khả năng giám sát tập trung qua giao diện HMI.

---

## 1. Tổng quan hệ thống
Hệ thống vận hành dựa trên kiến trúc điều phối thiết bị ngoại vi qua mạng Profinet, cho phép trao đổi dữ liệu liên tục giữa bộ điều khiển chính (IO Controller) và các trạm chức năng (IO Devices). Toàn bộ tín hiệu từ cảm biến và lệnh điều khiển đến cơ cấu chấp hành được xử lý theo thời gian thực.

### Kiến trúc phân đoạn chức năng
* **Trạm 1 (Bể ngầm):** Giám sát mực nước bồn chứa, đo lưu lượng đầu vào và điều khiển hệ thống bơm cấp chính để đảm bảo nguồn cấp ổn định.
* **Trạm 2 (Khu vực tầng cao):** Duy trì áp suất ổn định thông qua bơm tăng áp và hệ thống van điều tiết, đảm bảo áp lực nước cho các hộ dân ở tầng cao.
* **Trạm 3 (Khu vực tầng thấp):** Giám sát lưu lượng tiêu thụ và hỗ trợ điều khiển bơm phân phối nhằm tối ưu hóa hiệu suất vận hành và tiết kiệm năng lượng.

---

## 2. Thành phần thiết bị cốt lõi
Hệ thống tích hợp các thiết bị cơ điện và cảm biến chuẩn công nghiệp:

| Thiết bị | Chức năng kỹ thuật |
| :--- | :--- |
| **PLC & Remote I/O** | Bộ xử lý trung tâm và các trạm thu thập dữ liệu phân tán qua mạng Profinet. |
| **Biến tần (VFD)** | Điều khiển tốc độ động cơ bơm, duy trì áp suất ổn định và giảm dòng khởi động. |
| **Máy bơm tăng áp** | Giữ ổn định áp suất đường ống tại các khu vực sử dụng cuối (vòi sen, máy giặt...). |
| **Cảm biến áp suất** | Cung cấp tín hiệu phản hồi (Feedback) cho vòng điều khiển PID để duy trì áp suất hằng số. |
| **Cảm biến lưu lượng** | Đo lường, giám sát tốc độ dòng chảy và kiểm soát lượng nước tiêu thụ. |
| **Cảm biến mực nước** | Theo dõi mức nước tại bể ngầm và bể mái để ngăn ngừa tình trạng cạn bơm hoặc tràn bể. |
| **Van điều khiển & Van 1 chiều** | Điều tiết dòng chảy và bảo vệ đường ống khỏi hiện tượng thủy kích hoặc dòng chảy ngược. |

---

## 3. Quy trình vận hành & Logic điều khiển
Hệ thống được thiết kế với các thuật toán điều khiển thông minh nhằm tối ưu hóa hiệu suất và tuổi thọ thiết bị:

### Chế độ vận hành Tự động (Auto Mode)
* **Điều khiển luân phiên:** Hệ thống tự động luân phiên các bơm để cân bằng thời gian vận hành, kéo dài tuổi thọ thiết bị.
* **Điều khiển tăng cường:** Trong giờ cao điểm khi nhu cầu sử dụng nước tăng mạnh, hệ thống sẽ kích hoạt đồng thời nhiều bơm.
* **Dự phòng nóng:** Khi một bơm gặp sự cố, hệ thống tự động ngắt thiết bị lỗi và kích hoạt bơm còn lại vận hành liên tục cho đến khi có sự can thiệp kỹ thuật.

### Giám sát và Cảnh báo
* **Giao diện HMI:** Hiển thị trực quan trạng thái thiết bị, giá trị áp suất, lưu lượng và mực nước thời gian thực.
* **Quản lý cảnh báo (Alarm):** Hệ thống tự động phát hiện các trạng thái bất thường như cạn nước, quá áp hoặc lỗi bơm để cảnh báo tức thời cho người vận hành.
* **Phân tích xu hướng (Trend View):** Lưu trữ dữ liệu áp suất và lưu lượng dưới dạng biểu đồ, hỗ trợ phân tích hiệu suất và thực hiện bảo trì dự báo (Predictive Maintenance).

---

## 4. Thông số kỹ thuật nền tảng
* **Giao thức truyền thông:** Profinet RT (Real-Time).
* **Phương thức điều khiển:** PID Control, Interlock Logic, Alternating Control.
* **Nền tảng tích hợp:** TIA Portal (PLC Programming & HMI Design).

---
*Dự án phục vụ mục đích nghiên cứu, phát triển và triển khai thực tế trong lĩnh vực tự động hóa tòa nhà.*
