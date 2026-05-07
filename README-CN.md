# Markdown Editor Colorful

## Markdown

这是一个功能强大，颜色丰富的所见即所得的markdown编辑器

![](https://files.cnblogs.com/files/Renyi-Fan/colorful_markdown_editor_demo.gif)

集成[Vditor](https://github.com/Vanessa219/vditor)实现对markdown的所见即所得编辑.

### 注意点1

如果你的markdown编辑器中没有彩色主题 `Solarized_colorful` 等, 在vscode设置 `settings.json`中增加以下配置.

```json
{
  "workbench.editorAssociations": {
    "*.md": "fanrenyi.markdownViewer",
    "*.markdown": "fanrenyi.markdownViewer"
  }
}
```

![](https://img2024.cnblogs.com/blog/1163900/202605/1163900-20260506104703488-371796145.jpg)

### 注意点2

如果你需要使用原生markdown编辑器, 在vscode设置 `settings.json`中增加以下配置.

```json
{
  "workbench.editorAssociations": {
    "*.md": "default",
    "*.markdown": "default"
  }
}
```

### 注意点3

在编辑器打开右键菜单可将markdown导出为pdf, docx或者html, pdf依赖于chromium, 可通过 `vscode-office.chromiumPath`配置chromium浏览器路径.

![](https://img2024.cnblogs.com/blog/1163900/202605/1163900-20260505165615628-1039343710.png)

### 注意点4

编辑器在彩色主题的情况下，导出的html和pdf为彩色。编辑器在非彩色主题的情况下，导出的html和pdf为非彩色。

## 快捷键

快捷键: 基于[Vditor快捷键](shortcut.md)以及更多:

- 将列表上移一行: `Ctrl Alt I` / `⌘ ^ I`
- 将列表下移一行: `Ctrl Alt J` / `⌘ ^ J`
- 在VS Code中编辑: `Ctrl Alt E` / `⌘ ^ E`

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

## 介绍

本扩展支持在VS Code中预览以下常见的办公文件格式：

- Markdown: .md
- Excel: .xls, .xlsx, .csv
- Word: .docx
- Svg: .svg
- Pdf: .pdf
- 字体: .ttf, .otf, .woff, .woff2
- HTTP请求: .http
- Windows注册表: .reg
- 压缩文件: .zip, .jar, .vsix, .rar

## 其他功能

- 图标主题: 内置了Material Icon Theme部分icon
- Excel: 支持对xlsx, csv等excel文件进行预览和保存(注意xlsx保存会丢失格式, csv则不支持gbk中文)
- HTML: 编辑HTML的过程中按下ctrl+shift+v可实时预览.
- PDF: 支持直接预览pdf文件
- HTTP: 用于发送http请求, 由于REST Client本地请求有bug, 修改后进行集成.

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
