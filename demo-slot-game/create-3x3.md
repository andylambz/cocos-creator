
## Tạo khung 3x3

### Tạo Node SlotGrid

#### Tạo node SlotGrid
```
- Chuột phải vào Canvas > Create > Empty Node
- Đặt tên: SlotGrid
- Chỉnh Anchor về (0.5, 0.5)
- Chỉnh Position về (0, 0) để nằm giữa màn hình
```

![create-slotgrid](./assets/photos/create-3x3/create-slotgrid.png)

![slot-grid](./assets/photos/create-3x3/slot-grid.png)

#### Thêm Layout cho SlodGrid để tự động sắp xếp ô

```
- Chọn node SlotGrid
- Trong Inspector, nhấn Add Component → UI → Layout
- Cấu hình Layout: 
    - Type: Grid
    - Resize Mode: Container
    - Start Axis: Horizontal
    - Spacing X: 10, Spacing Y: 10 (khoảng cách giữa ô)
```
> Layout sẽ tự động sắp xếp các ô thành lưới 3x3

![slot-grid-add-component-layout](./assets/photos/create-3x3/slot-grid-add-component-layout.png)

### Tạo Prefab SlotCell

#### Tạo Node SlotCell
```
- Trong cửa sổ Hierarchy, chuột phải vào Canvas > Create > Empty Node
- Đặt tên node mới là SlotCell
- Chọn node SlotCell → trong Inspector, chỉnh: 
    - Anchor: (0.5, 0.5)
    - ContentSize: 100 x 100 (hoặc kích thước bạn muốn cho ô slot)
```

![slot-cell](./assets/photos/create-3x3/slot-cell.png)

#### Thêm Sprite vào SlotCell để hiển thị biểu tượng

```
- Chuột phải vào SlotCell > Create > 2D Object > Sprite
- Đặt tên là Symbol
- Chọn node Symbol → trong Inspector: 
    - Anchor: (0.5, 0.5)
    - Position: (0, 0)
    - ContentSize: 100 x 100
    - Type: Simple
    - Sprite Frame: để trống (sẽ gán bằng code sau)
```

> Đây là nơi bạn sẽ gán hình ảnh kẹo khi quay slot

![slot-cell-add-sprite](./assets/photos/create-3x3/slot-cell-add-sprite.png)

#### Tạo Prefab từ SlotCell

```
- Tạo thư mục assets/prefabs (nếu chưa có)
- Trong cửa sổ Hierarchy, kéo node SlotCell vào thư mục assets/prefabs
- Cocos Creator sẽ tạo một Prefab SlotCell.prefab
```

> Xoá node SlotCell khỏi scene nếu không cần giữ lại

![slot-cell-create-prefab](./assets/photos/create-3x3/slot-cell-create-prefab.png)

#### Sử dụng Prefab trong khung slot

```
- Kéo SlotCell.prefab vào node SlotGrid nhiều lần (ví dụ: 9 lần cho lưới 3x3)
- Các ô sẽ tự động sắp xếp nếu SlotGrid có Layout Component
```

```
- Chỉnh SlotGrid
- Chọn node SlotGrid
    - Trong Inspector > Layout
        - Constraint: FIXED_COL
        - Constraint Num: 3
    - Anchor Point: 1.5 : 0.5 (cacn giữa màn hinh)
```

![use-slot-cell](./assets/photos/create-3x3/use-slot-cell.png)
