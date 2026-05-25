# Neon Blaster - 網頁射擊遊戲

![Neon Blaster](https://img.shields.io/badge/version-v2.0-00ffcc?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
![Platform](https://img.shields.io/badge/platform-Web-orange?style=flat-square)

一個使用原生 HTML5 Canvas + ES6 Class 開發的 2D 射擊遊戲，採用物件導向程式設計（OOP）模式，適合做為學習作品集展示。

---

## 🎮 遊戲玩法

### 操作方式
| 按鍵 | 功能 |
|------|------|
| `↑ ↓ ← →` 或 `WASD` | 移動飛船 |
| `空白鍵` | 發射子彈 |
| `P` | 暫停遊戲 |
| `ESC` | 返回主選單 |

### 主選單操作
| 按鍵 | 功能 |
|------|------|
| `↑ ↓` 或 `W S` | 選擇項目 |
| `Enter` 或 `空白鍵` | 確認 |

---

## ✨ v2.0 新增功能

### 🏆 成就系統（12個成就）
| 成就 | 圖示 | 條件 |
|------|------|------|
| 初試啼聲 | 🎯 | 殺死第一個敵人 |
| 小試身手 | 🔟 | 累計擊殺 10 |
| 殺敵好手 | 💀 | 累計擊殺 50 |
| 百連斬 | ⚔️ | 累計擊殺 100 |
| 連擊新手 | 🔥 | 達成 10 連擊 |
| 連擊達人 | ✨ | 達成 25 連擊 |
| 初窺門徑 | 🌟 | 升到 5 級 |
| 略有小成 | ⭐ | 升到 10 級 |
| 波瀾不驚 | 🌊 | 到達第 10 波 |
| 滴水不漏 | 🛡️ | 無傷通關 |
| Boss殺手 | 👹 | 擊敗 Boss |
| 高分選手 | 🏆 | 分數超過 5000 |

### 🔥 COMBO 連擊系統
- 2 秒內連續殺敵可累積連擊數
- 連擊數越高，顯示效果越華麗
- 10 連擊 = 橙色，20 連擊 = 紫色

### 📊 結算統計
- **評級系統**：S（傳說）/ A（傑出）/ B（良好）/ C（普通）/ D（繼續努力）
- **詳細統計**：分數、擊殺數、最高連擊、存活時間、波次、等級、命中率、造成傷害、收集道具

### 📈 經驗值系統
- 殺敵獲得經驗值
- 升級提升屬性：回血、加速、射速加快、分數倍率提升

---

## 👾 敵人類型

| 敵人 | 圖示 | 顏色 | 特性 | 血量 | 分數 |
|------|------|------|------|------|------|
| BasicEnemy | ◉ | 🔴 #ff4466 | 追蹤玩家，直線前進 | 30 | 10 |
| FastEnemy | ◈ | 🟠 #ff8800 | 高速移動，體積小 | 20 | 20 |
| TankEnemy | ◉ | 🟣 #aa44ff | 高血量，緩慢，有白色邊框 | 80 | 30 |
| ShooterEnemy | ◎ | 🔵 #00aaff | 會向玩家發射子彈 | 40 | 25 |
| ExploderEnemy | ◌ | 🔴 #ff2200 | 接近時會爆炸 | 15 | 15 |
| BossEnemy | ✪ | 🟣 #ff00ff | 巨大，高血量，傷害高 | 500 | 200 |

---

## 🎁 道具系統

| 道具 | 顏色 | 效果 |
|------|------|------|
| 🟢 回復 | 綠色愛心 | 恢復 30 血量 |
| 🟠 炸彈 | 橙色圓形 | 清除畫面上所有敵人 |
| 🔵 護盾 | 藍色六邊形 | 無敵 5 秒 |
| 🟡 分數 | 黃色星星 | 2 倍分數持續 10 秒 |
| 🟣 速度 | 紫色閃電 | 移動速度 +60% |
| 🔷 冰凍 | 青色雪花 | 所有敵人凍結 5 秒 |
| 🟤 磁鐵 | 金色 U 形 | 自動吸引附近道具 |

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
│   ├── HealthUp
│   ├── BombUp
│   ├── ShieldUp
│   ├── ScoreUp
│   ├── SpeedUp
│   ├── FreezeUp
│   └── MagnetUp
├── Particle（粒子效果）
└── FloatingText（浮動文字）
```

### OOP 設計模式
- **封裝（Encapsulation）**：屬性與方法包裝在類別內
- **繼承（Inheritance）**：子類別繼承 `GameObject` 基礎類
- **多形（Polymorphism）**：不同敵人類別覆寫 `draw()` 和 `update()` 方法
- **工廠模式（Factory Pattern）**：`EnemyFactory.create()` 統一建立敵人

---

## 📁 專案結構

```
neon-blaster/
├── index.html      # 遊戲主檔案（所有程式碼在單一 HTML 檔案中）
├── background.jpg  # 背景圖片
└── README.md       # 本說明文件
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
- 畫面震動效果
- 背景網格動畫

---

## 📝 作者

TENGmm — 學習作品集專案

## 🔗 相關連結

- GitHub: https://github.com/TENGmm/neon-blaster