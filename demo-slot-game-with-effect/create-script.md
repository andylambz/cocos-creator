
### 📑 Table of Contents

- [📘 Tạo script SlotGameWithEffectScript](#-tạo-script-slotgamewitheffectscript)
- [📘 Tạo GameManager](#-tạo-gamemanager)
- [📘 Run](#-run)

***

#### 📘 Tạo script SlotGameWithEffectScript

Right click assets/scripts > Create > Typescript
- `Name` :`SlotGameWithEffectScript.ts`

```Typescript
import { _decorator, Component, instantiate, Label, Node, Prefab, tween, Vec3 } from 'cc';
const { ccclass, property } = _decorator;

@ccclass('SlotGameWithEffectScript')
export class SlotGameWithEffectScript extends Component {

    @property(Node)
    scoreLabel: Node = null;
    @property([Prefab])
    symbols: Prefab[] = [];
    @property([Node])
    columns: Node[] = [];

    private score: number = 0;
    
    generateColumnSymbols(column: Node) {
        const container = column.getChildByName('Mask')?.getChildByName('SymbolContainer');
        if (!container) return;

        container.removeAllChildren();

        // Tạo 9 biểu tượng ngẫu nhiên
        for (let i = 0; i < 9; i++) {
            const randomIndex = Math.floor(Math.random() * this.symbols.length);
            const symbol = instantiate(this.symbols[randomIndex]);
            symbol.name = `symbol_${randomIndex}`;
            container.addChild(symbol);
        }
    }

    spinColumn(column: Node, delay: number) {
        const container = column.getChildByName('Mask')?.getChildByName('SymbolContainer');
        if (!container) return;

        const targetY = -container.children.length * 100 + 300;

        tween(container)
            .delay(delay)
            .to(0.4, { position: new Vec3(0, targetY, 0) }, { easing: 'quadOut' })
            .call(() => {
                // Giữ lại 3 biểu tượng giữa
                const midSymbols = container.children.slice(3, 6);
                container.removeAllChildren();
                midSymbols.forEach(symbol => {
                    container.addChild(symbol);
                    symbol.setPosition(new Vec3(0, 0, 0)); // reset vị trí
                });
                container.setPosition(new Vec3(0, 0, 0)); // reset container
            })
            .start();
    }

    
    spin() {
        for (let i = 0; i < this.columns.length; i++) {
            const column = this.columns[i];
            this.generateColumnSymbols(column);
            this.spinColumn(column, i * 0.2); // lệch thời gian giữa các cột
        }

        this.scheduleOnce(() => {
            this.checkWin();
        }, 1.2);
    }

    checkWin() {
        const midSymbols: string[] = [];

        for (let i = 0; i < this.columns.length; i++) {
            const column = this.columns[i];
            const container = column.getChildByName('Mask')?.getChildByName('SymbolContainer');
            if (!container) continue;

            const midSymbolNode = container.children[1]; // hàng giữa
            midSymbols.push(midSymbolNode.name);
            console.log(`Cột ${i} Biểu tượng giữa: ${midSymbolNode.name}`);
        }

        console.log('Biểu tượng giữa:', midSymbols);

        // Kiểm tra nếu cả 3 biểu tượng giữa giống nhau
        if (midSymbols.length === 3 && midSymbols.every(name => name === midSymbols[0])) {
            this.score += 10;
            this.updateScoreLabel();
            console.log('Thắng! +10 điểm');
        } else {
            console.log('Không trúng thưởng');
        }
    }

    updateScoreLabel() {
        const labelComp = this.scoreLabel.getComponent(Label);
        if (labelComp) {
            labelComp.string = `Điểm: ${this.score}`;
        }
    }
}

```

***

#### 📘 Tạo GameManager

Right click Canvas > Create > Empty Node
- `Name` : `GameManager`

Add component > Custom Script > SlotGameWithEffectScript
- `Score Label` : kéo node ScoreLabel vào
- `Symbols` : kéo 3 biểu tượng keo vào (prefab)
- `Columns` : kéo 3 ColumnX vào


##### 📖 Kết nối sự kiện spin với SpinButton

Chọn SpinButton > Click Events > thêm 1 event cho array > array [0]
- `Target` : Kéo node GameManager vào đây
- `Component` : Chọn `SlotGameWithEffectScript`
- `Handler` : Chọn hàm spin

***

#### 📘 Run

Chạy thử demo

***

🔙 [Back](index.md)
