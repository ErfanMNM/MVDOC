---
sidebar_position: 2
---

# 📖 Chương 2: Kiến trúc hệ thống Machine Vision

## 2.1 Tổng quan kiến trúc

Một hệ thống Machine Vision điển hình bao gồm các thành phần chính sau:

1. **Camera** – để thu nhận hình ảnh
2. **Ống kính (Lens)** – để điều chỉnh trường nhìn và độ phóng đại
3. **Nguồn sáng (Lighting)** – để đảm bảo độ tương phản, loại bỏ nhiễu
4. **Thiết bị xử lý (Processor)** – xử lý hình ảnh (PC, smart camera hoặc vision controller)
5. **Phần mềm (Software)** – dùng để phân tích hình ảnh và ra quyết định
6. **I/O hoặc Giao tiếp** – để tương tác với hệ thống ngoài (PLC, Robot, v.v.)

<!-- IMAGE: Add block diagram of machine vision system architecture -->

---

## 2.2 Camera công nghiệp

### Loại camera phổ biến:
- **Area scan camera**: chụp ảnh vùng, thông dụng nhất
- **Line scan camera**: chụp từng dòng pixel, dùng cho vật chuyển động nhanh hoặc kích thước dài
- **3D camera**: thu nhận dữ liệu độ sâu, dùng trong đo lường 3D hoặc phát hiện vật thể không phẳng

### Thông số quan trọng:
- Độ phân giải (megapixel)
- Tốc độ khung hình (fps)
- Cảm biến (CMOS hoặc CCD)
- Giao tiếp (GigE, USB3, Camera Link, CoaXPress)

<!-- IMAGE: Add image comparing Area Scan vs Line Scan camera -->

---

## 2.3 Ống kính (Lens)

- Chọn lens phụ thuộc vào:
  - Kích thước cảm biến
  - Khoảng cách làm việc (Working distance)
  - Trường nhìn mong muốn (Field of View)
  - Độ phân giải yêu cầu

- Các loại phổ biến:
  - Fixed focal lens
  - Zoom lens
  - Telecentric lens (cho đo lường chính xác)

<!-- IMAGE: Add illustration showing field of view and lens selection -->

---

## 2.4 Hệ thống chiếu sáng

Ánh sáng là yếu tố then chốt tạo nên hình ảnh tốt để xử lý. Một số loại ánh sáng phổ biến:

- **Backlight**: ánh sáng từ phía sau vật, dùng để tạo biên dạng rõ ràng
- **Ring light**: ánh sáng vòng tròn, giúp chiếu đều quanh vật
- **Bar light**: chiếu ánh sáng tuyến tính, phù hợp cho vật thể dài
- **Coaxial light**: dùng gương phản chiếu cho bề mặt phản sáng

> **Mục tiêu:** tăng tương phản giữa đặc điểm cần kiểm tra và nền

<!-- IMAGE: Add lighting setup comparison (backlight vs ringlight vs barlight) -->

---

## 2.5 Thiết bị xử lý ảnh

### Loại thiết bị:
- **Smart camera**: tích hợp cảm biến + xử lý + I/O trong một thiết bị
- **Vision controller (PC-based)**: dùng máy tính công nghiệp, xử lý mạnh hơn, tùy biến cao
- **Embedded system**: tối ưu cho chi phí và tiết kiệm không gian

### Tiêu chí lựa chọn:
- Tốc độ xử lý yêu cầu
- Tính linh hoạt, mở rộng
- Giao tiếp với hệ thống khác (Ethernet, IO, Modbus, OPC, v.v.)

<!-- IMAGE: Add comparison of smart camera vs PC-based system -->

---

## 2.6 Phần mềm thị giác

### Chức năng chính:
- Xử lý ảnh (lọc, ngưỡng, tìm biên, histogram, morphology...)
- Nhận dạng đối tượng (blob, contour, shape match)
- Đo lường kích thước, góc, khoảng cách
- Đọc mã (Barcode, QR, Datamatrix), OCR
- Kết nối và điều khiển I/O

### Một số phần mềm phổ biến:
- Cognex VisionPro / Insight
- HALCON (MVTec)
- NI Vision (LabVIEW)
- OpenCV (thư viện mã nguồn mở)
- Matrox Design Assistant

<!-- IMAGE: Add screenshot of common vision software interface -->

---

## 2.7 Giao tiếp và tích hợp hệ thống

- Truyền dữ liệu kết quả sang:
  - PLC
  - HMI
  - Robot
  - Cơ sở dữ liệu MES/ERP

### Giao thức thường dùng:
- Digital I/O (Trigger, Output)
- Ethernet/IP, Modbus TCP, PROFINET
- OPC UA / MQTT

> Đảm bảo hệ thống thị giác có thể “ra quyết định” và “ra lệnh” cho thiết bị ngoại vi.

<!-- IMAGE: Add integration diagram showing vision system communicating with PLC and robot -->

---

## 📌 Tóm tắt chương

Kiến trúc hệ thống Machine Vision là sự kết hợp chặt chẽ giữa phần cứng (camera, lens, ánh sáng), phần mềm xử lý ảnh và giao tiếp với hệ thống tự động. Việc lựa chọn đúng cấu hình và thiết kế ánh sáng phù hợp là yếu tố quyết định hiệu quả của toàn bộ ứng dụng thị giác máy.

