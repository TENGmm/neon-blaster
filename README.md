# Neon Blaster - 網頁射擊遊戲

![Neon Blaster](https://img.shields.io/badge/version-v1.0-00ffcc?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
![Platform](https://img.shields.io/badge/platform-Web-orange?style=flat-square)

一個使用原生 HTML5 Canvas + ES6 Class 開發的 2D 射擊遊戲，採用物件導向程式設計（OOP）模式。
https://tengmm.github.io/neon-blaster/
---

## 🎮 遊戲玩法

### 操作方式
| 按鍵 | 功能 |
|------|------|
| `↑ ↓ ← →` | 移動飛船 |
| `空白鍵` | 發射子彈 |
| `P` | 暫停遊戲 |
| `R` | 重新開始 |

### 敵人類型

| 敵人 | 圖示 | 顏色 | 特性 | 血量 | 分數 |
|------|------|------|------|------|------|
| BasicEnemy | ◉ | 🔴 #ff4466 | 追蹤玩家，直線前進 | 30 | 10 |
| FastEnemy | ◈ | 🟠 #ff8800 | 高速移動，體積小 | 20 | 20 |
| TankEnemy | ◉ | 🟣 #aa44ff | 高血量，緩慢，有白色邊框 | 80 | 30 |
| ShooterEnemy | ◎ | 🔵 #00aaff | 會向玩家發射子彈 | 40 | 25 |
| ExploderEnemy | ◌ | 🔴 #ff2200 | 接近時會爆炸 | 15 | 15 |
| BossEnemy | ✪ | 🟣 #ff00ff | 巨大，高血量，傷害高 | 500 | 200 |



> 每種敵人的視覺設計都使用霓虹發光效果（Neon Glow），提升遊戲的視覺體驗。

### 道具系統
| 道具 | 顏色 | 效果 |
|------|------|------|
| 🟢 綠色 | 回復膠囊 | 恢復 30 血量 |
| 🟠 橙色 | 炸彈 | 清除畫面上所有敵人 |
| 🔵 藍色 | 護盾 | 無敵 5 秒 |
| 🟡 黃色 | 分数加成 | 2 倍分數持續 10 秒 |
| 🟣 紫色 | 速度提升 | 移動速度 +50% |
| 🔷 青藍色 | 冰凍 | 所有敵人凍結 5 秒 |
| 🟤 金色 | 磁鐵 | 自動吸引附近道具 10 秒 |

---

## 🏗️ 技術架構

本遊戲以 **ES6 Class** 實作物件導向設計，展示以下 OOP 概念：

### 類別層級
```
GameObject（基礎類）
├── Player（玩家）
├── Bullet（子彈）
├── Enemy（敵人）
│   ├── BasicEnemy
│   ├── FastEnemy
│   ├── TankEnemy
│   ├── ShooterEnemy
│   ├── ExploderEnemy
│   └── BossEnemy
├── PowerUp（道具）
└── Particle（粒子效果）
```

### OOP 設計模式
- **封裝（Encapsulation）**：屬性與方法包裝在類別內
- **繼承（Inheritance）**：子類別繼承 `GameObject` 基礎類
- **多形（Polymorphism）**：不同敵人類別覆寫 `draw()` 和 `update()` 方法

---

## 📁 專案結構

```
neon-blaster/
├── index.html   # 遊戲主檔案（所有程式碼在單一 HTML 檔案中）
└── README.md    # 本說明文件
```

---

## 🚀 開始遊戲

直接用瀏覽器開啟 `index.html` 即可遊玩，無需任何伺服器或安裝。

---

## ⚙️ 遊戲設定

難度會影響玩家初始屬性：

| 難度 | 血量 | 速度 | 射速 |
|------|------|------|------|
| 簡單 | 200 | 7 | 正常 |
| 普通 | 150 | 6 | 正常 |
| 困難 | 100 | 5 | 較慢 |

---

## 🎨 視覺效果

- 霓虹風格（Neon Glow Effect）
- 粒子爆炸效果
- 子彈軌跡
- 敵人受擊閃爍
- 背景星空移動

---

## 📝 作者

TENGmm — 學習作品集專案

## 🔗 相關連結

- GitHub: https://github.com/TENGmm/neon-blaster
