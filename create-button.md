
## Tạo nút "Quay"

### Tạo nút “Quay” trong Scene

```
- Chuột phải vào Canvas → Create → UI Component → Button
- Đặt tên node là SpinButton
- Trong node SpinButton, bạn sẽ thấy có một Label con → đổi nội dung thành “Quay”
- Chọn node SpintButton/Label > Trong Inspector > component Label
    - string: "Quay"
- Chỉnh Position của SpinButton để đặt dưới khung slot (ví dụ: (0, -250))
```

### Kết nối sự kiện Click của nút “Quay”

```
- Chọn node SpinButton trong Hierarchy
- Trong Inspector > component Button > Click Events
- Nhập 1 để thêm 1 event
    - Cấu hình như sau:
        - Target: Kéo node GameManager vào đây
        - Component: Chọn SweetSlotGame
        - Handler: Chọn hàm spin

> Nếu bạn không thấy SweetSlotGame hoặc spin, hãy đảm bảo:
    - Script đã được gắn vào node GameManager
    - Hàm spin() được khai báo là public trong script
```

![create-button](assets/photos/create-button/create-button.png)

![create-button-2](assets/photos/create-button/create-button-2.png)
