[English](README.md) · [日本語](README.ja.md) · **繁體中文**

# 汐見灣鐵道 汐見線（汐見湾鉄道 汐見線）

BVE Trainsim 5 / 6 用的虛構路線資料。全長 27.4 km、12 站的地方私鐵，
從海濱城市一路開往霧氣繚繞的溫泉鄉——**一趟車程看盡十種風景**。

> 海 → 港 → 海岸線 → 市區高架 → 地下 → 大鐵橋 → 櫻並木 → 水田 → 里山 → 溪谷 → 溫泉街

## 路線諸元

| 項目 | 數值 |
|------|-----|
| 區間 | 汐見濱 〜 霧山溫泉 |
| 營業里程 | 27.4 km |
| 站數 | 12（其中 4 站有交會設備） |
| 軌距 | 1,067 mm |
| 電氣化 | 直流 1,500 V |
| 最高速度 | 95 km/h（山區 65 km/h） |
| 最急坡度 | 33 ‰（溪谷區間） |
| 最小曲線 | R160（溪谷區間） |
| 保安裝置 | ATS-Sn（4 現示自動閉塞・單線） |
| 運轉時分 | 各停 約 42 分 / 快速 約 38 分 |

## 十大風景帶

| # | 區間 (km) | 風景 |
|---|-----------|------|
| ① | 0.0–1.0 | 海濱都市（起點站・汐見濱） |
| ② | 1.0–3.8 | 太平洋海岸線・燈塔 |
| ③ | 3.8–5.8 | 俯瞰市區的高架 |
| ④ | 5.8–7.0 | 地下區間・地下車站 |
| ⑤ | 7.0–8.5 | 跨越大川的桁架鐵橋 |
| ⑥ | 8.5–12.5 | 櫻並木郊外住宅區 |
| ⑦ | 12.5–16.5 | 一望無際的水田 |
| ⑧ | 16.5–20.0 | 里山杉林・鎮守之森 |
| ⑨ | 20.0–24.0 | 溪谷（33‰・5 座隧道・3 座鋼橋） |
| ⑩ | 24.0–27.4 | 霧氣繚繞的溫泉街（終點） |

## 收錄場景（scenario）

| 場景 | 種別 | 天候 | 概要 |
|------|------|------|------|
| `scenario/shiomi_day.txt` | 各站停車 | 白天・晴 | 標準。全站停車・一人服務 |
| `scenario/shiomi_night.txt` | 各站停車 | 夜 | 只靠月光與車內燈的夜行班次 |
| `scenario/shiomi_rain.txt` | 各站停車 | 雨 | 濕軌易空轉，進階者取向 |
| `scenario/shiomi_rapid.txt` | 快速「しおかぜ」 | 白天・晴 | 通過 5 站・38 分 |

## 執行環境

- BVE Trainsim 5.7 以上 / BVE Trainsim 6
- 地圖格式 `BveTs Map 2.02`、編碼 **UTF-8**

## 安裝步驟（教學）

> **前提**：BVE Trainsim 為 **Windows 專用**（macOS 請透過 Parallels / Boot Camp / 虛擬機）。
> 若尚未安裝本體，請至官方網站取得 → [bvets.net 下載](https://bvets.net/en/download/)

### STEP 1 — 取得檔案
點本 repo 右上的 **Code → Download ZIP**，或用 Git：
```
git clone https://github.com/masonzeng702550/bve5-shiomi-line.git
```

### STEP 2 — 放進場景資料夾
把整個 `bve5-shiomi-line` 資料夾放到 BVE 的場景資料夾底下（例）：
```
文件\BveTs\Scenarios\bve5-shiomi-line\
```
在 BVE 的 **選項設定 → 場景（シナリオ）** 確認場景資料夾指向此處。
請勿改變 `scenario\` 與 `Shiomi\` 的相對位置（所有路徑皆為相對指定）。

### STEP 3 — 準備車輛，並改寫 `Vehicle =` 這行
本路線不含車輛。請取得任一**通勤形（建議 3 輛編組）**（見下方「取得相容車輛」），
再把 `scenario\` 內各 `.txt` 的這一行改成你車輛 `Vehicle.txt` 的相對路徑：
```
Vehicle = ..\..\vehicle\generic_3car\vehicle.txt   ← 改成你的實際路徑
```

### STEP 4 — 放置 3D 模型(.x)與貼圖
`Shiomi\structure\structures.txt` 每一行右側就是模型該擺放的路徑（例 `..\objects\coast\lighthouse.x`）。
把 `.x` 模型與 `.png` 貼圖放到對應的 `Shiomi\objects\...` 位置。
若想**先只測線形而不備美術素材**，把 structures.txt 相關行的行首加上 `#` 註解掉，
即可只保留軌道、通關全程駕駛。

### STEP 5 — 啟動
開啟 BVE → 在場景選擇畫面選 **「汐見線 普通 霧山温泉行」**（夜／雨／快速也會各自出現）→ 開始駕駛。

## 取得相容車輛（需另行準備）

各停與快速皆以 **3 輛編組**為前提（月台長、停車位置、時分都以 3 輛為基準），
但任何通勤形車輛都能駕駛。請從下列來源取得免費車輛，依 STEP 3 替換。
下載前**務必確認各配布來源的使用規約**。

| 來源 | 內容 |
|------|------|
| [官方下載（bvets.net）](https://bvets.net/en/download/) | 本體與官方範例車（京成千葉線等） |
| [BVE5 車輛資料一覽表（Players Wiki）](https://wikiwiki.jp/bvets/BVE5%E5%AF%BE%E5%BF%9C%E3%83%87%E3%83%BC%E3%82%BF%E4%B8%80%E8%A6%A7/%E8%BB%8A%E4%B8%A1%E3%83%87%E3%83%BC%E3%82%BF%E4%B8%80%E8%A6%A7%E8%A1%A8) | 社群最完整索引，看「通勤・近郊型電車」分類（最好找） |
| [テツドウのホームページ](https://tetsudo-1998.jimdofree.com/bve5/%E8%BB%8A%E4%B8%A1%E3%83%87%E3%83%BC%E3%82%BF/) | 大阪 Metro 系通勤車（御堂筋線 10 系等，7z 配布） |
| [中部新都市運輸区](https://bvetk.arkw.net/download.html) | 含通勤車的車輛・路線資料 |
| [横浜鉄道研究室](https://softwarenet.wixsite.com/yktrain/bve-data) | 含通勤車的配布資料一覽 |

> 不必剛好 3 輛也能跑；較長編組仍可啟動，但可能超出月台或停車位置偏移。

## 疑難排解

| 症狀 | 原因 | 處理 |
|------|------|------|
| 場景清單看不到 | 未設定場景資料夾 | 重新檢查 STEP 2 的選項設定 |
| `找不到檔案 …\*.x` | 未放置 3D 模型 | STEP 4（或把該行註解掉） |
| 無法啟動／車輛錯誤 | `Vehicle =` 路徑錯誤 | 重新確認 STEP 3 的路徑 |
| 出現亂碼 | 編碼問題 | 全部檔案皆 UTF-8，請用支援 UTF-8 的編輯器開啟 |

## 資料夾結構

```
scenario/                 場景（晝／夜／雨／快速）
Shiomi/
├── map/
│   ├── main*.txt         各班次的地圖本體（以 include 分割）
│   ├── 00_init.txt       全域初始設定
│   ├── 10..95_*.txt      各風景帶的線形與結構物
│   ├── signals.txt       閉塞・號誌・ATS-Sn 地上子
│   ├── trains.txt        對向列車
│   └── env_night/​rain.txt 夜間・雨天的環境覆寫
├── station/              停車場列表（各停 / 快速）
├── structure/            結構物列表
├── signal/               號誌現示列表
├── sound/  sound3d/      音效列表
└── objects/              3D 模型・貼圖（※本 repo 未收錄）
```

### 地圖設計方針

- 依風景帶以 `include` 分割，由 `main.txt` 統整載入順序。
- 夜／雨沿用既有的白天地圖，把 `env_night.txt` / `env_rain.txt`
  **最後 include**，於相同距離程覆寫光源／背景／霧
  （完全不複製線形與結構物）。
- 快速只替換停車場列表（`main_rapid.txt`）即實現。

## 關於素材

`Shiomi/objects/` 底下的 3D 模型(.x)與貼圖，以及車輛資料，
均未收錄於本 repo（請隨配布包附上，或自各配布來源取得），
並依結構物列表的路徑放置。出處請見 `Shiomi/objects/CREDITS.txt`。

## 授權

本人原創部分採 **CC BY-NC 4.0**。流用素材依各配布來源的規約。

---

*本資料為虛構作品，路線名・社名・站名・地名皆為架空。*
