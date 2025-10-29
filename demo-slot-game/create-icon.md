
### 📑 Table of Contents

- [📘 Chuẩn bị hình ảnh kẹo](#-chuẩn-bị-hình-ảnh-kẹo)
- [📘 Tạo prefab cho từng biểu tượng](#-tạo-prefab-cho-từng-biểu-tượng)

***

Thêm biểu tượng, hình ảnh kẹo vào project

#### 📘 Chuẩn bị hình ảnh kẹo

Hình ảnh kẹo
- ./assets/photos/icons/candy-cane.png
- ./assets/photos/icons/candy.png
- ./assets/photos/icons/sweets.png

Tìm và tải các hình ảnh PNG kẹo (nền trong suốt) từ các nguồn miễn phí như:
    - https://www.flaticon.com/
    - https://www.freepik.com/
    - https://opengameart.org/

- Kéo các file ảnh vào thư mục `assets/symbols/` (tạo nếu thư mục chưa có) trong Cocos Creator


![symbols](./assets/photos/add-icons/symbols.png)

***

#### 📘 Tạo prefab cho từng biểu tượng

##### 🧱 Tạo Node

Trong cửa sổ Hierarchy
Right click Canvas > Create > Empty Node
- `Name` : `CandyNode`

Chọn node `CandyNode`> Inspector
- `Anchor Point` : (0.5, 0.5)
- `ContentSize` : 100 x 100

##### 🧱 Tạo Sprite

Right click `CandyNode`
Create > 2D Object > Sprite
- `Name` : `CandySprite`

Chọn node `CandySprite`
Inspector 
- `Anchor Point` : (0.5, 0.5)
- `Position` : (0, 0)
- `Content Size` : 100 x 100
- `Type` : Simple
- `Sprite Frame` : chọn hình ảnh kẹo (ví dụ: candy.png)

##### 🧱 Tạo Prefab

- Trong cửa sổ Hierarchy, kéo node `CandyNode` vào thư mục `assets/prefabs`
- Cocos Creator sẽ tạo một Prefab `CandyNode.prefab`

> 📌 **Note**  
> Sau khi tạo prefab xong có thể xóa các node icon đi không cần giữ lại

Lặp lại các bước để tạo prefab cho các icon còn lại
Và ta đã có 3 prefab tương ứng cho 3 icon

![create-prefab-icon](./assets/photos/add-icons/create-prefab-icon.png)

***

🔙 [Back](index.md)
