# Markdown Editor Colorful

## Markdown

這是一個功能強大，顏色豐富的所見即所得的markdown編輯器

![](https://files.cnblogs.com/files/Renyi-Fan/colorful_markdown_editor_demo.gif)

整合[Vditor](https://github.com/Vanessa219/vditor)實現對markdown的所見即所得編輯。

### 命令和設定命名空間

Markdown 相關的命令、自訂編輯器 ID 和設定使用 `fanrenyi-markdown.*` 命名空間。非 Markdown 的 Office 相關功能使用 `fanrenyi-office.*`。為了相容舊使用者，外掛仍會讀取舊的 `vscode-office.*` Markdown 設定，但新的設定範例都使用 `fanrenyi-markdown.*`。

### 注意點1

如果你的markdown編輯器中沒有彩色主題 `Solarized_colorful` 等，在vscode設定 `settings.json` 中增加以下配置。

```json
{
  "workbench.editorAssociations": {
    "*.md": "fanrenyi-markdown.viewer",
    "*.markdown": "fanrenyi-markdown.viewer"
  }
}
```

![](https://images.cnblogs.com/cnblogs_com/Renyi-Fan/1188097/o_260604123900_no_colorful_theme02.jpg)

### 注意點2

如果你需要使用原生markdown編輯器, 在vscode設定 `settings.json` 中增加以下配置.

```json
{
  "workbench.editorAssociations": {
    "*.md": "default",
    "*.markdown": "default"
  }
}
```

### 注意點3

在編輯器開啟右鍵選單可將markdown匯出為pdf, docx或者html, pdf依賴於chromium, 可透過 `fanrenyi-markdown.chromiumPath`配置chromium瀏覽器路徑.

![](https://img2024.cnblogs.com/blog/1163900/202605/1163900-20260505165615628-1039343710.png)

### 注意點4

編輯器在彩色主題的情況下，匯出的html和pdf為彩色。

編輯器在非彩色主題的情況下，匯出的html和pdf為非彩色。

## 自訂 Markdown 樣式

自訂樣式透過專門的 `Custom` 編輯器主題生效，可以同時影響 Vditor 編輯器和匯出的 PDF。

最簡單的使用方式：

1. 執行命令 `Markdown: Create Custom Style Example File`。
2. 外掛會建立 `.vscode/markdown-custom-style.css`。
3. 外掛會自動把 `fanrenyi-markdown.editorTheme` 切換為 `Custom`。
4. 修改並儲存產生的 CSS 檔案即可。

也可以在 `settings.json` 中手動配置：

```json
{
  "fanrenyi-markdown.editorTheme": "Custom",
  "fanrenyi-markdown.customStyle.enabled": true,
  "fanrenyi-markdown.customStyle.cssFile": "${workspaceFolder}/.vscode/markdown-custom-style.css",
  "fanrenyi-markdown.customStyle.variable": {
    "fontFamily": "\"Segoe UI\", \"Microsoft YaHei\", Arial, sans-serif",
    "fontSize": "16px",
    "lineHeight": "1.78",
    "textColor": "#263238",
    "backgroundColor": "#fbfcf8",
    "h1Color": "#145c52",
    "h2Color": "#8a4f14",
    "linkColor": "#0b7285",
    "blockquoteBorderColor": "#4c9f70",
    "blockquoteBackgroundColor": "#eef7f1",
    "inlineCodeColor": "#9b2c2c",
    "inlineCodeBackground": "#f7e9e9",
    "codeBlockBackground": "#f4f6f8",
    "tableBorderColor": "#b8c2cc",
    "tableHeaderBackground": "#edf2f7",
    "tableEvenRowBackground": "#f7fafc"
  }
}
```

`fanrenyi-markdown.customStyle.variable` 只修改對應的單一屬性。例如 `h2Color` 只會修改二級標題顏色。如果需要邊框、間距、陰影等更複雜的樣式，請寫在 CSS 檔案中。

支援的變數欄位：

`fontFamily`, `fontSize`, `lineHeight`, `textColor`, `backgroundColor`, `h1Color`, `h2Color`, `h3Color`, `h4Color`, `h5Color`, `h6Color`, `h1FontSize`, `h2FontSize`, `h3FontSize`, `linkColor`, `strongColor`, `emphasisColor`, `blockquoteBorderColor`, `blockquoteBackgroundColor`, `inlineCodeColor`, `inlineCodeBackground`, `codeBlockColor`, `codeBlockBackground`, `codeFontFamily`, `tableBorderColor`, `tableHeaderColor`, `tableHeaderBackground`, `tableEvenRowBackground`.

樣式優先順序：

1. 主題 CSS。
2. `fanrenyi-markdown.customStyle.cssFile`。
3. `fanrenyi-markdown.customStyle.css`。
4. `fanrenyi-markdown.customStyle.variable`。

產生的 `markdown-custom-style.css` 中包含更詳細的選擇器範例，覆蓋標題、段落、清單、任務清單、引用、程式碼、表格、圖片、數學公式、Mermaid 圖、details 摺疊區塊以及部分 Vditor UI 區域。Vditor 編輯器中的選擇器通常以 `#vditor` 開頭；匯出 PDF 中的選擇器通常以 `.content-wrapper` 開頭。

## 快捷鍵

快捷鍵: 基於[Vditor快捷鍵](shortcut.md)以及更多:

- 將清單上移一行: `Ctrl Alt I` / `⌘ ^ I`
- 將清單下移一行: `Ctrl Alt J` / `⌘ ^ J`
- 在VS Code中編輯: `Ctrl Alt E` / `⌘ ^ E`

### 通用

| 名称           | 快捷键               | 备注              |
| -------------- | -------------------- | ----------------- |
| 表情           | :/⌘ E                |                   |
| 标题           | Ctrl H / ⌘ H         | 参见下文          |
| 粗体           | Ctrl B / ⌘ B         |                   |
| 斜体           | Ctrl I / ⌘ I         |                   |
| 删除线         | Ctrl S / ⌘ S         |                   |
| 链接           | Ctrl K / ⌘ K         | 参见下文          |
| 无序列表       | Ctrl L / ⌘ L         | 参见下文          |
| 有序列表       | Ctrl O / ⌘ O         | 参见下文          |
| 任务列表       | Ctrl J / ⌘ J         | 参见下文          |
| 引用           | Ctrl ; / ⌘ ;         | 参见下文          |
| 分割线         | Ctrl Shift H / ⌘ ⇧ H |                   |
| 代码块         | Ctrl U / ⌘ U         | 参见下文          |
| 代码           | Ctrl G / ⌘ G         |                   |
| 元素前插入空块 | Ctrl Shift B / ⌘ ⇧ B | wysiwyg & ir 模式 |
| 元素后插入空块 | Ctrl Shift E / ⌘ ⇧ E | wysiwyg & ir 模式 |
| 表格           | Ctrl M / ⌘ M         | 参见下文          |
| 撤销           | Ctrl Z / ⌘ Z         |                   |
| 重做           | Ctrl Y / ⌘ Y         |                   |
| 隐藏编辑器     | Ctrl P / ⌘ P         | sv 模式           |
| 全屏           | Ctrl ' / ⌘ '         |                   |
| 向上移动块元素 | Ctrl Shift U / ⌘ ⇧ U | wysiwyg & ir 模式 |
| 向下移动块元素 | Ctrl Shift D / ⌘ ⇧ D | wysiwyg & ir 模式 |
| 移除当前元素   | Ctrl Shift X / ⌘ ⇧ X | wysiwyg 模式      |
| At 用户        | @                    |                   |
| 错误输入       | Backspace            |                   |

### 标题 Ctrl H / ⌘ H

| 名称     | 快捷键                                 |
| -------- | -------------------------------------- |
| 变大     | Ctrl + / ⌘ +                           |
| 变小     | Ctrl - / ⌘ -                           |
| H1-H6    | Ctrl Alt 1/2/3/4/5/6 / ⌘ ⌥ 1/2/3/4/5/6 |
| 弹出菜单 | Ctrl H / ⌘ H                           |

## 介紹

本擴充功能支援在VS Code中預覽以下常見的辦公檔案格式：

- Markdown: .md
- Excel: .xls, .xlsx, .csv
- Word: .docx
- Svg: .svg
- Pdf: .pdf
- 字型: .ttf, .otf, .woff, .woff2
- HTTP請求: .http
- Windows登錄檔: .reg
- 壓縮檔案: .zip, .jar, .vsix, .rar

## 其他功能

- 圖示主題: 內建了Material Icon Theme部分icon
- Excel: 支援對xlsx, csv等excel檔案進行預覽和儲存(注意xlsx儲存會丟失格式, csv則不支援gbk中文)
- HTML: 編輯HTML的過程中按下ctrl+shift+v可實時預覽.
- PDF: 支援直接預覽pdf檔案
- HTTP: 用於傳送http請求, 由於REST Client本地請求有bug, 修改後進行整合.

## Credits

- Vscode Office: [vscode-office](https://github.com/cweijan/vscode-office)
- PDF rendering: [mozilla/pdf.js/](https://github.com/mozilla/pdf.js/)
- Docx rendering: [VolodymyrBaydalka/docxjs](https://github.com/VolodymyrBaydalka/docxjs)
- XLSX rendering:
  - [SheetJS/sheetjs](https://github.com/SheetJS/sheetjs): XLSX parsing
  - [myliang/x-spreadsheet](https://github.com/myliang/x-spreadsheet): XLSX rendering
- HTTP: [Rest Client](https://github.com/Huachao/vscode-restclient)
- Markdown: [Vanessa219/vditor](https://github.com/Vanessa219/vditor)
- Material Icon theme: [PKief/vscode-material-icon-theme](https://github.com/PKief/vscode-material-icon-theme)
