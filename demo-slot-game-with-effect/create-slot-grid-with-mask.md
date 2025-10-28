# Tạo SlotGrid và Mask

## Tạo SlotGrid và Mask theo cấu trúc như sau

```
SlotGrid (Horizontal Layout)
├── Column0 (Node)
│   └── Mask (Rect)
│       └── SymbolContainer (Vertical Layout)
│           ├── Symbol1
│           ├── Symbol2
│           ├── Symbol3 ← hiển thị
│           ├── Symbol4 ← hiển thị
│           ├── Symbol5 ← hiển thị
│           ├── Symbol6
│           └── Symbol7
├── Column1
├── Column2
```

## Thiết lập từng phần

### Tạo node SlotGrid

- Chọn SLotGameScene > Right click Canvas > Create > Empty Node
- Gắn Layout > Chọn Add component > Create > UI > Layout
  - Type: HORIZONTAL
  - Resize Mode: None
  - Horizontal Direction: LEFT_TO_RIGHT

### Tạo node Column0

- Right click SlotGrid > Create > Empty Node
- Kích thước: width = 100, height = 300 (3 biểu tượng × 100px)
- Không cần Layout

### Tạo Mask

- Right click Column0 > Create > 2D Object > Mask
  - Type: GRAPHICS_RECT
    • Content Sizee: width = 100, height = 300
    • Đặt ở giữa ColumnX

### Tạo SymbolContainer

- Right click Mask > Create > Empty Node
  - Name: SymbolContainer
- Gắn Layout, Chọn Add Component > UI > Layout
  - Type: VERTICAL
  - Resize Mode: CONTAINER
  - Vertical Direction: TOP_TO_BOTTOM

### Thêm sumbol vào SymbolContainer

- Kéo prefabs/SlotCell (đã tạo ở demo trước) vào SymbolContainer
- Kéo 7 hoặc 9 symbol vào

### Tiếp tục làm tương tự cho các column còn lại

- Có thể duplicate từ Column0

![create-slot-grid-and-mask](photos/create-slot-grid-and-mask.png)

***
[Back](index.md)
