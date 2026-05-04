# Colorful Markdown Editor

## Markdown

這是一個功能強大，顏色豐富的所見即所得的markdown編輯器

![colorful_markdown_editor_demo.gif](https://files.cnblogs.com/files/Renyi-Fan/colorful_markdown_editor_demo.gif)

整合[Vditor](https://github.com/Vanessa219/vditor)實現對markdown的所見即所得編輯。

如果你需要使用原生markdown編輯器, 在vscode設定中增加以下配置.

```json
{
  "workbench.editorAssociations": {
    "*.md": "default",
    "*.markdown": "default"
  }
}
```

在編輯器開啟右鍵選單可將markdown匯出為pdf, docx或者html, pdf依賴於chromium, 可透過 `vscode-office.chromiumPath`配置chromium瀏覽器路徑.

![colorful_markdown_editor_export](images/README/colorful_markdown_editor_export.png)

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
