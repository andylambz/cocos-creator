
# 🛠️ Hướng Dẫn Sử Dụng Công Cụ XYZ

> Phiên bản: 1.0  
> Ngày cập nhật: 27/10/2025  
> Tác giả: Andy

---

## 📘 Giới thiệu

Công cụ **XYZ** giúp bạn tự động hóa quy trình xử lý dữ liệu một cách nhanh chóng và hiệu quả.  
Dưới đây là giao diện chính của công cụ:

![Giao diện công cụ XYZ](./assets/xyz-interface.png)

---

## ⚙️ Yêu cầu hệ thống

- Hệ điều hành: Windows / macOS / Linux
- Node.js >= 18
- Trình duyệt Chrome hoặc Edge (nếu là công cụ web)

---

## 🚀 Cài đặt

### Cách 1: Cài qua npm

```bash
npm install -g xyz-tool
```

### Cách 2: Tải trực tiếp từ GitHub

- Truy cập: [https://github.com/tennguoidung/xyz-tool](https://github.com/tennguoidung/xyz-tool)
- Tải file `.zip` và giải nén

---

## 🧪 Cách sử dụng cơ bản

### Bước 1: Khởi chạy công cụ

```bash
xyz run --input data.csv --output result.json
```

### Bước 2: Tùy chọn nâng cao

```bash
xyz run --input data.csv --output result.json --filter "status=active" --limit 100
```

> 📌 Ghi chú: Bạn có thể dùng `--help` để xem tất cả tùy chọn.

---

## 📂 Cấu trúc thư mục đầu ra

```text
output/
├── result.json
├── logs/
│   └── run.log
└── reports/
    └── summary.html
```

---

## 📸 Ví dụ minh họa

Dưới đây là ảnh chụp kết quả sau khi chạy công cụ:

![Ảnh kết quả](./assets/output-preview.png)

---

## 🧠 Mẹo sử dụng

- Dùng `--verbose` để hiển thị log chi tiết
- Kết hợp với `cron` để chạy định kỳ
- Tích hợp với API bằng cách dùng `--webhook`

---

## ❓ Câu hỏi thường gặp (FAQ)

**Q: Công cụ có hỗ trợ định dạng Excel không?**  
A: Có, bạn có thể dùng `--input data.xlsx`

**Q: Làm sao để lọc theo nhiều điều kiện?**  
A: Dùng cú pháp `--filter "status=active,type=premium"`

---

## 📞 Liên hệ & hỗ trợ

- 📧 Email: support@xyztool.com  
- 🌐 Website: [https://xyztool.com](https://xyztool.com)

---
