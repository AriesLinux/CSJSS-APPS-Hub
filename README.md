<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1e3a8a,50:1d4ed8,100:3b82f6&height=220&section=header&text=CSJSS%20APPS%20Hub&fontSize=50&fontColor=ffffff&fontAlignY=36&desc=The%20Ultimate%20App%20Store%20for%20CSJSS%20Students%20and%20Staff&descSize=18&descAlignY=58&animation=fadeIn" width="100%" alt="CSJSS APPS Hub">

<br>

<img src="https://raw.githubusercontent.com/AriesLinux/CSJSS-Healthy-Kit/main/school_logo.jpg" height="110" alt="School Logo">

<br><br>

<img src="./CSJSS_APPS.png" width="80" alt="CSJSS APPS">
&nbsp;
<img src="./CSJSS_ONLINE.png" width="80" alt="CSJSS ONLINE">
&nbsp;
<img src="./CSJSS_Leaders.png" width="80" alt="CSJSS Leaders">
&nbsp;
<img src="./CSJSS_CampusNews.png" width="80" alt="CSJSS CampusNews">
&nbsp;
<img src="./CSJSS_Go!.png" width="80" alt="CSJSS Go!">
&nbsp;
<img src="./CSJSS_PASS.png" width="80" alt="CSJSS PASS">
&nbsp;
<img src="./CSJSS%20Healthy%20Kit%20ICON.png" width="80" alt="CSJSS Healthy Kit">
&nbsp;
<img src="./CSJSS_Lab.png" width="80" alt="CSJSS Lab">

<br><br>

<img src="https://img.shields.io/badge/Platform-iOS_%7C_Android-gray?style=for-the-badge&logo=apple&logoColor=white" alt="Platform">
<img src="https://img.shields.io/badge/Ecosystem-CSJ_Integrated-blue?style=for-the-badge&logo=google-cloud&logoColor=white" alt="Ecosystem">
<img src="https://img.shields.io/badge/Auth-CSJSS_SSO-green?style=for-the-badge" alt="Auth">
<img src="https://img.shields.io/badge/School-Caritas_St._Joseph-red?style=for-the-badge" alt="School">
<img src="https://img.shields.io/github/stars/AriesLinux/CSJSS-APPS-Hub?style=for-the-badge&logo=github&color=gold" alt="Stars">
<img src="https://img.shields.io/github/last-commit/AriesLinux/CSJSS-APPS-Hub?style=for-the-badge&color=2ea44f" alt="Last Commit">

<br><br>

**明愛聖若瑟中學專屬軟體發佈平台 & 數位校園生態系**

<br>

[English](./README_EN.md) | **繁體中文** | [粵語版本](./README_HK.md)

<br>

[應用矩陣](#apps) · [平台架構](#architecture) · [運行狀態](#status) · [CSJSS PASS](#pass) · [CSJSS Lab](#lab) · [安裝部署](#deploy) · [貢獻者](#credits)

</div>

---

<a id="apps"></a>

## 📱 應用矩陣 (App Matrix)

**CSJSS APPS** 不僅是一個下載器，它是整合全校數位資源的指揮中心，以下是目前託管的核心應用：

| 應用名稱 (App Name) | 類別 (Category) | 主要功能 (Key Features) |
| :--- | :---: | :--- |
| **🌐 CSJSS ONLINE** | `Web Portal` | 學校官網的原生 App 化封裝，支援重要公告推播通知 |
| **👔 CSJSS Leaders** | `Management` | **領袖/老師專用**，發佈當值時間表，管理學生秩序紀錄 |
| **📰 CSJSS CampusNews** | `Media` | **學生自製新聞台**，支援圖文編輯，影片上傳與即時評論互動 |
| **🏃 CSJSS Go!** | `Activity` | 校內活動報名，House (社) 比賽積分查詢，ECA 資訊匯總 |
| **💳 CSJSS PASS** | `Digital ID` | **旗艦功能**，整合 Apple Pay / Google Pay 的數位學生證 |
| **🧪 CSJSS Lab** | `Education` | 實驗室安全守則，**AR/VR 科學實驗模擬遊戲** |
| **🏥 CSJSS Healthy Kit** | `Health` | 基於 EazyUI 自研架構與 MIT App Inventor 開發的智能健康監測 APP，依賴 iRED 公司開發的 Smart Learning HEALTH KIT 硬件 |

---

<a id="architecture"></a>

## 🧩 平台架構 (Architecture Overview)

```mermaid
flowchart LR
    U["👥 學生 / 領袖 / 老師<br/>CSJSS Google Account"] -->|"SSO 一鍵登入"| S["🚀 CSJSS APPS Hub"]
    S --> P{"🔐 權限分級"}
    P --> A1["🌐 ONLINE"]
    P --> A3["📰 CampusNews"]
    P --> A4["🏃 Go!"]
    P --> A5["💳 PASS"]
    P --> A6["🧪 Lab"]
    P --> A7["🏥 Healthy Kit"]
    P -->|"領袖 / 老師"| A2["👔 Leaders"]
    S -.->|"OTA 更新通知"| U

    style U fill:#374151,stroke:#374151,color:#fff
    style S fill:#1d4ed8,stroke:#1d4ed8,color:#fff
    style P fill:#7c3aed,stroke:#7c3aed,color:#fff
```

---

<a id="status"></a>

## 📊 平台運行狀態 (Store Status)

### ✅ 核心服務 (Core Services)

| | 服務 | 說明 |
| :---: | :--- | :--- |
| 🔑 | **統一身份認證 (SSO)** | 一鍵登入所有 CSJSS 系列 App，無需重複輸入帳號 |
| 🔄 | **OTA 自動更新** | 當子應用有新版本時，商店會自動推送更新消息 |
| 🛡️ | **權限分級** | 自動識別使用者身份（登錄 CSJSS Google account）（學生/領袖/老師），解鎖對應 App 下載權限 |
| 📱 | **跨平台支援** | 完美適配 iOS (IPA) 與 Android (APK) 環境 |
| 🧪 | **Beta 測試版軟件分發** | 可提前試用還在開發階段的 APP |

> [!NOTE]
> CSJSS APPS 在 iOS 中並不需要 APP，所以在商店頁面會切換為一套 APP 整合。

### ⚠️ 已知問題 (Known Issues)

| 應用 | 狀態 |
| :--- | :--- |
| 🧪 **CSJSS Lab** | 💭 僅停留於概念階段 |
| 📰 **CSJSS CampusNews** | 💭 僅停留於概念階段 |
| 🌐 **CSJSS ONLINE** | 💭 僅停留於概念階段 |
| 👔 **CSJSS Leaders** | 💭 僅停留於概念階段 |
| 🏃 **CSJSS Go!** | 💭 僅停留於概念階段 |
| 💳 **CSJSS PASS** | 🚧 開發緩慢及受阻 |

---

<a id="pass"></a>

## 💳 CSJSS PASS 核心亮點 (Spotlight)

**將你的學生證放入手機錢包，體驗無感通行的便利**

<div align="center">

| 👛 Wallet Integration<br><sub>原生錢包整合</sub> | 📲 Tap to Check-in<br><sub>NFC 拍卡</sub> | 🔒 Security<br><sub>安全驗證</sub> |
| :--- | :--- | :--- |
| 支援一鍵加入 **Apple Wallet** (iPhone/Apple Watch)<br><br>支援一鍵加入 **Google Wallet** (Android) | 早上進校時，無需解鎖手機或開啟 App，直接透過 **NFC 感應** 記錄到校時間<br><br>圖書館借書、實驗室簽到、校內小食部身份驗證一拍即合 | 動態加密 QR Code，杜絕截圖借用與身份盜用 |

</div>

👉 **更多訊息請移步至 [CSJSS-PASS 倉庫](https://github.com/AriesLinux/CSJSS-PASS)**

---

<a id="lab"></a>

## 🧪 CSJSS Lab 創新體驗 (Innovation)

**打破物理限制，將科學實驗室裝進口袋**

<div align="center">

| 📚 安全守則資料庫 | 🔬 AR 元素週期表 | 🥽 VR 虛擬實驗 |
| :---: | :---: | :---: |
| 實驗前必讀指南，內建測驗功能，通過後方可解鎖實體實驗室進入權限 | 使用手機鏡頭掃描課本圖片，3D 懸浮顯示化學元素特性與結構 | 模擬危險化學反應（如鈉與水反應、強酸稀釋），讓同學在安全環境下觀察劇烈反應現象 |

</div>

> [!NOTE]
> CSJSS Lab 目前仍停留於概念階段。

---

<a id="deploy"></a>

## ⚙️ 安裝與部署 (Deployment)

> [!IMPORTANT]
> **由於這是校內專用商店，請依照以下步驟安裝：**

| 步驟 | 操作 | 說明 |
| :---: | :--- | :--- |
| **1** | 📥 **下載安裝包** | 前往校網下載 `CSJSS_Store_Installer`（iOS 描述檔 或 Android APK） |
| **2** | 🔏 **信任企業憑證 (iOS)** | 設定 → 一般 → VPN 與裝置管理 → 信任 `Caritas St. Joseph Secondary School` |
| **3** | 🔑 **身份登入** | 使用學校 Google 帳號（`@csjss.edu.hk`）登入商店，系統將自動派發對應權限 |
| **4** | 🚀 **一鍵部署** | 點擊首頁的 "Install All Essential Apps" 即可批量下載所有必備工具 |

---

<a id="credits"></a>

## 👏 開發貢獻者 (Credits)

| 角色 | 負責方 |
| :--- | :--- |
| 🧭 **Project Lead** | CSJ IT 部 |
| 🧪 **CSJSS Lab** | Science Society & STEM 部（提供科學內容與 VR 建模） |
| 🎨 **UI/UX Design** | EazyUI |

---

<div align="center">

**CSJSS APPS - Empowering Campus Life with Tech.**

發現 Bug？請透過 CSJSS Go! 內的「意見反饋」功能回報

<a href="https://github.com/AriesLinux/CSJSS-APPS-Hub">
  <img src="https://img.shields.io/github/stars/AriesLinux/CSJSS-APPS-Hub?style=social" alt="Star this repo">
</a>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:3b82f6,50:1d4ed8,100:1e3a8a&height=120&section=footer" width="100%" alt="footer">

</div>
