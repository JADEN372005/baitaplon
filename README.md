# 🧩 StreakFlow - Ứng dụng Theo dõi Thói quen (Java Desktop)

**Phiên bản:** 1.0 (MVP)  
**Ngày phát hành:** 08/10/2025  
**Nền tảng:** Ứng dụng Desktop cho Windows (Java)

---

## 📝 Giới thiệu

**StreakFlow** là ứng dụng Java Desktop giúp người dùng **theo dõi và duy trì thói quen hằng ngày** một cách trực quan và hiệu quả.  
Ứng dụng **hoàn toàn cục bộ**, không yêu cầu đăng nhập hay kết nối Internet — phù hợp cho sinh viên hoặc cá nhân muốn học và áp dụng nguyên lý **habit tracking (theo dõi chuỗi thói quen)**.

---

## 🎯 Mục tiêu

- Hỗ trợ người dùng **tạo, xem, và theo dõi** các thói quen cá nhân.
- Tự động **tính toán streak (chuỗi liên tiếp)** dựa trên thói quen hoàn thành.
- Cung cấp **thống kê cơ bản** về quá trình thực hiện thói quen.
- Lưu trữ dữ liệu **an toàn cục bộ** trên thiết bị người dùng.

---

## 🧱 Phạm vi Dự án

| Đặc điểm | Mô tả |
|-----------|--------|
| **Loại ứng dụng** | Java Desktop (Local App) |
| **Người dùng** | Cá nhân (không tài khoản, không đăng nhập) |
| **Dữ liệu** | Lưu trữ cục bộ trên máy người dùng |
| **Giao diện** | Java Swing hoặc JavaFX |

---

## ⚙️ Yêu cầu Chức năng (Functional Requirements)

### **FR1. Quản lý Thói quen**
| Mã | Mô tả | Mức ưu tiên |
|----|--------|--------------|
| FR1.1 | Tạo thói quen mới với **Tên** và **Tần suất (Hàng ngày / Ngày cụ thể)** | Cao |
| FR1.2 | Xem danh sách thói quen cần thực hiện trong **ngày hiện tại**, kèm Streak hiện tại | Cao |
| FR1.3 | Chỉnh sửa hoặc xóa thói quen | Trung bình |

---

### **FR2. Theo dõi & Logic Streak**
| Mã | Mô tả | Mức ưu tiên |
|----|--------|--------------|
| FR2.1 | Đánh dấu / Bỏ đánh dấu “Hoàn thành” cho thói quen hôm nay | Cao |
| FR2.2 | Tính toán **streak**: tăng +1 nếu liên tục, reset nếu bỏ lỡ | Cao |
| FR2.3 | Hiển thị lịch sử hoàn thành (Hoàn thành / Bỏ lỡ) theo ngày | Trung bình |

---

### **FR3. Thống kê Cơ bản**
| Mã | Mô tả | Mức ưu tiên |
|----|--------|--------------|
| FR3.1 | Hiển thị **Chuỗi hiện tại**, **Chuỗi dài nhất**, và **Tổng số lần hoàn thành** | Trung bình |

---

### **FR4. Lưu trữ Dữ liệu Cục bộ**
| Mã | Mô tả | Mức ưu tiên |
|----|--------|--------------|
| FR4.1 | Lưu tất cả dữ liệu (thói quen, lịch sử, streak) **cục bộ** | Cao |
| FR4.2 | Khi khởi động lại, ứng dụng **tự động tải dữ liệu đã lưu** | Cao |

---

## 🧩 Yêu cầu Phi chức năng (Non-Functional Requirements)

### **NFR-T: Công nghệ**
| Mã | Mô tả |
|----|--------|
| NFR-T1 | Sử dụng ngôn ngữ **Java** |
| NFR-T2 | Giao diện được phát triển bằng **Swing** hoặc **JavaFX** |
| NFR-T3 | Dữ liệu lưu bằng **File Serialization** hoặc **SQLite** |

---

### **NFR-P: Hiệu năng**
| Mã | Mô tả |
|----|--------|
| NFR-P1 | Thời gian khởi động & tải dữ liệu **< 3 giây** |
| NFR-P2 | Đánh dấu “Hoàn thành” phản hồi **< 0.5 giây** |

---

### **NFR-U: Khả dụng**
| Mã | Mô tả |
|----|--------|
| NFR-U1 | Giao diện đơn giản, dễ đọc, rõ ràng |
| NFR-U2 | Các thao tác chính (Tạo, Check-in, Xóa) dễ truy cập |

---

## 🧠 Cấu trúc Hệ thống Dự kiến

```

src/
├── model/
│   ├── Habit.java
│   ├── HabitHistory.java
│   └── HabitManager.java
├── view/
│   ├── MainWindow.java
│   ├── HabitEditor.java
│   └── StatisticsView.java
├── controller/
│   └── HabitController.java
├── data/
│   ├── data.db  (hoặc data.ser)
│   └── DataHandler.java
└── Main.java

````

---

## 💾 Cơ chế Lưu trữ

- **Tùy chọn 1:** File Serialization (`.ser`)
- **Tùy chọn 2:** CSDL SQLite (`.db`)
- Dữ liệu bao gồm:
  - Danh sách thói quen
  - Lịch sử check-in
  - Thông tin streak

---

## 🚀 Hướng dẫn Cài đặt & Chạy

### **Yêu cầu:**
- Java 17 trở lên  
- IDE khuyến nghị: IntelliJ IDEA hoặc Eclipse

---

## 📈 Mục tiêu Tương lai (Phiên bản 2.0)

* Hỗ trợ **đồng bộ hóa đám mây** (Google Drive / Firebase)
* Giao diện **dark mode / theme tùy chọn**
* Biểu đồ trực quan về tiến độ thói quen
* Chức năng **nhắc nhở tự động**
