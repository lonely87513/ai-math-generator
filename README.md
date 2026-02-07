# 🎮 AI 數學小天才 - 小三數學題目生成器

## 📚 項目簡介

呢個係一個 AI 驅動既數學題目生成器，專為香港澳門小學三年級學生設計。

### ✨ 主要功能

- 🎲 **隨機出题** - 根據題庫模板智能生成新題目
- ⏱️ **計時挑戰** - 60秒限時答最多題
- 📊 **積分系統** - 連續答對有bonus
- ⭐ **星星獎勵** - 每3題對有星星
- 🎵 **音效回饋** - Duolingo風格音效
- ✨ **粒子效果** - 答對時有慶祝動畫
- 🎯 **多種題型** - 加/減/乘/除/混合

## 🚀 使用方法

### 方法一：直接用網頁版
1. 開啟 `index.html` 檔案
2. 選擇題型（加/減/乘/除/混合）
3. 按「開始挑戰」
4. 輸入答案，按 Enter 確認

### 方法二：GitHub Pages（推薦）
```bash
# 上傳到 GitHub
git init
git add .
git commit -m "Initial commit"
gh repo create ai-math-generator --public --source=. --push
# 然後在 GitHub Settings 啟用 GitHub Pages
```

## 📁 檔案結構

```
ai-math-generator/
├── index.html          # 主網頁（HTML + CSS + JS）
├── problem-bank.json    # 題庫（JSON格式）
└── README.md           # 說明文件
```

## 🎯 題庫格式

題庫使用 JSON 格式，方便 AI 閱讀同擴展：

```json
{
  "grade_3": {
    "addition": [
      {
        "template": "小明有{N1}粒糖，媽媽再比{N2}粒佢，總共有幾多粒？",
        "range_N1": [1, 50],
        "range_N2": [1, 30],
        "answer": "N1 + N2",
        "context": "糖果"
      }
    ]
  }
}
```

### 模板變量
- `{N1}`, `{N2}`, `{N3}`, `{N4}` - 可替換的數字
- `range_N1` - N1 的範圍 [最小, 最大]
- `answer` - 答案公式

## 🎨 界面特色

- 🌈 **色彩繽紛** - 紫色漸變背景
- 🎮 **遊戲化設計** - 像玩遊戲咁學數學
- 📱 **響應式** - 手機同電腦都用得
- 🔊 **音效** - 答對有成功音效，錯咗有提示

## 🔧 自定義

### 新增題目
喺 `problem-bank.json` 度加入新 template：

```json
{
  "template": "新題目模板{N1}...{N2}...",
  "range_N1": [最小, 最大],
  "range_N2": [最小, 最大],
  "answer": "N1 + N2",
  "context": "情境"
}
```

### 調整難度
修改 `GAME_CONFIG` 物件：
```javascript
const GAME_CONFIG = {
    timeLimit: 60,      // 秒數
    maxQuestions: 10,   // 最大題數
    pointsPerCorrect: 100  // 每題分數
};
```

## 🤖 AI Prompt

如果要 AI 閱讀題庫並生成新格式：

```
你是一個小學數學題目專家。

任務：閱讀題庫，將每題轉為JSON格式：
{
  "template": "小明有{N1}粒糖，買咗{N2}粒，總共幾多？",
  "operation": "加法",
  "range_N1": [1, 50],
  "range_N2": [1, 30],
  "answer": "N1 + N2",
  "context": "糖果"
}
```

## 📚 題目來源

- 香港教育局課程指引
- MamaLovePrint 小三數學工作紙
- 考評局小三基本能力評估

## 🔗 相關連結

- **Notion 規劃**: https://www.notion.so/...
- **GitHub**: https://github.com/lonely87513/ai-math-generator

## 📝 更新日誌

**v1.0.0** (2026-02-07)
- ✅ 基本遊戲功能
- ✅ 計時挑戰模式
- ✅ 加減乘除題型
- ✅ 積分系統
- ✅ 音效同粒子效果

---

Made with ❤️ by Nathan & 小肥羊 🐑
