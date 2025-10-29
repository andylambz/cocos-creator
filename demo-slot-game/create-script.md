
### 📑 Table of Contents

- [📘 Tạo script SweetSlotGame](#-tạo-script-sweetslotgame)
- [📘 Tạo node GameManager](#-tạo-node-gamemanager)

***

#### 📘 Tạo script SweetSlotGame

##### 🧱 Tạo script

> Tạo script `SweetSlotGame.ts`

- Trong cửa sổ Assets, chuột phải vào thư mục `assets/scripts` (hoặc tạo thư mục mới nếu chưa có)
- Chọn Create > TypeScript
- Đặt tên file là `SweetSlotGame.ts`


![create-type-script](./assets/photos/create-script/create-type-script.png)

##### 🧱 Viết script

Mở file `SweetSlotGame.ts`, thêm nội dung sau:

```Typescript
import { _decorator, Component, Node, Prefab, instantiate } from 'cc';
const { ccclass, property } = _decorator;
@ccclass('SweetSlotGame')
export class SweetSlotGame extends Component {
@property([Node])
    slotCells: Node[] = [];
@property([Prefab])
    symbols: Prefab[] = [];
spin() {
        for (let i = 0; i < this.slotCells.length; i++) {
            const randomIndex = Math.floor(Math.random() * this.symbols.length);
            const symbol = instantiate(this.symbols[randomIndex]);
const cell = this.slotCells[i];
            cell.removeAllChildren(); // Xoá biểu tượng cũ
            cell.addChild(symbol);    // Thêm biểu tượng mới
        }
    }
}
```

***

#### 📘 Tạo node GameManager

Dùng để gắn script vào node để quản lý sau khi tạo

##### 📖 Tạo node `GameManager`

##### 🧱 Add component

Chọn node GameManager > 
Add Component > Custom Script > SweetSlotGame >
Inspector
- `Slote Cells` : slotCells, mảng các SlotCell
- `Symbols` : symbols, mảng các Prefab biểu tượng kẹo

##### 📖 Gán dữ liệu vào script

Gán slotCells
- Kéo từng node `SlotCell` trong `SlotGrid` vào mảng slotCells
- Theo thứ tự từ trái sang phải, trên xuống dưới

Gán symbols
- Kéo các Prefab biểu tượng kẹo vào mảng symbols

![create-node-game-manager](./assets/photos/create-script/create-node-game-manager.png)

***

🔙 [Back](index.md)
