# ⚔️ 倚天屠龍記：群俠格鬥傳 v2.5 (Yitian Wuxia Fighter)

一款基於 HTML5 Canvas、Web Audio API 與 Web Speech API 打造的《倚天屠龍記》2D 武俠格鬥網頁遊戲，針對 **iPad Pro (ProMotion 120Hz)**、**Microsoft Edge** 與桌面瀏覽器進行全觸控與智慧配音深度優化。

---

## 🌟 遊戲特色 (v2.5)

- **27 位可玩武林群俠**：涵蓋第一批（張無忌、趙敏、周芷若、張三丰、滅絕師太、謝遜）、明教高層法王（陽頂天、楊逍、范遙、黛綺絲、殷天正、韋一笑）、紅顏與死敵（小昭、殷離、黃衣女子、殷野王、成昆）、汝陽王府高手（鹿杖客、鶴筆翁、方東白、阿二、阿三、剛相）與四大隱藏傳奇宗師（火工頭陀、何足道、郭襄、鬥酒神僧）。
- **6 大經典決戰場景自動載入**：明教光明頂、武當紫霄宮、大都萬安寺、靈蛇島海岸、冰火島極境、少林屠獅大會，支援場景縮圖預覽與自訂背景上傳。
- **純淨去背立繪動態格鬥**：移除傳統幾何攻擊線條，改以角色去背立繪身形位移、殘影、武器寒光與柔和真氣粒子呈現打擊感。
- **三大遊戲模式**：
  - `⚔️ 3v3 組隊車輪戰`（支援情侶／師徒／教派宿命羈絆加成）
  - `📜 6 大關卡破關劇情`
  - `🥋 1v1 自由對戰`
- **iPad Pro 智慧防女聲配音系統**：內建 `CHAR_VOICE_PROFILES` 聲線鎖定與 Web Audio 武俠合成語音雙軌機制，徹底解決 iPadOS 預設女聲誤套用至男性角色的問題。
- **戰局暫停選單 (`⏸️ 暫停 [P]`)**：隨時鎖定戰局時間軸、試聽 P1/P2 聲線或重新開局。

---

## 📁 專案目錄結構

```text
yitian-wuxia-fighter/
├── index.html                        # 模組化主遊戲入口（自動載入 css/、js/ 與 assets/ 圖檔）
├── css/
│   └── style.css                     # 遊戲介面、iPad 滿版劇院模式與半透明觸控 HUD 樣式
├── js/
│   ├── assets_map.js                 # 27 位角色圖資與 6 大場景底圖相對路徑映射表
│   └── game.js                       # 核心物理引擎、AI 決策、粒子特效、語音合成與劇情系統
├── assets/
│   ├── characters/                   # 27 位角色獨立資料夾（每位含 full.jpg、avatar.jpg、sprite.webp）
│   ├── stages/                       # 6 大經典場景高解析 WebP 底圖 (stage_0 ~ stage_5)
│   └── originals/                    # 原始高解析角色生成原畫與參考圖檔
├── scripts/
│   ├── prepare_assets.py             # 原畫裁切與頭像生成 Python 腳本
│   └── make_cutouts.py               # OpenCV GrabCut 自動去背與 WebP 立繪生成腳本
├── standalone/
│   ├── yitian_wuxia_fighter_v2.5_standalone.html  # 單檔離線完整版（內嵌全數 Base64 圖資，免伺服器直接開玩）
│   └── yitian_wuxia_fighter_v1.html               # v1 初版存檔
├── push_to_github.sh                 # macOS / Linux 一鍵推送至 GitHub 腳本
├── push_to_github.bat                # Windows 一鍵推送至 GitHub 批次檔
└── README.md                         # 專案說明文件
```

---

## 🚀 快速啟動與部署至 GitHub (`thn-lab`)

### 方式一：於 GitHub 建立 Private 專案並推送全部檔案
1. 前往 [GitHub 建立新專案](https://github.com/new)，Owner 選擇 **`thn-lab`**：
   - **Repository name**: `yitian-wuxia-fighter`
   - **Visibility**: 選擇 **Private**（私人專案）
   - 點擊 **Create repository**（請勿勾選自動產生 README，以便直接推送本專案）。
2. 解壓縮本專案壓縮包，於專案根目錄開啟終端機執行：
   ```bash
   ./push_to_github.sh https://github.com/thn-lab/yitian-wuxia-fighter.git
   ```
   （Windows 用戶可直接雙擊執行 `push_to_github.bat`）。

### 方式二：單機直接遊玩
- **模組化版本**：於專案目錄執行 `python3 -m http.server 8000`，瀏覽器開啟 `http://localhost:8000` 即可遊玩。
- **單檔離線版**：直接用瀏覽器（Edge / Safari / Chrome）打開 `standalone/yitian_wuxia_fighter_v2.5_standalone.html` 即可免伺服器離線遊玩。
