# Markdown Editor Colorful

## Markdown

这是一个功能强大，颜色丰富的所见即所得的markdown编辑器

![](https://files.cnblogs.com/files/Renyi-Fan/colorful_markdown_editor_demo.gif)

集成[Vditor](https://github.com/Vanessa219/vditor)实现对markdown的所见即所得编辑.

### 命令和设置命名空间

Markdown 相关的命令、自定义编辑器 ID 和设置使用 `fanrenyi-markdown.*` 命名空间。非 Markdown 的 Office 相关功能使用 `fanrenyi-office.*`。为了兼容旧用户，插件仍会读取旧的 `vscode-office.*` Markdown 设置，但新的配置示例都使用 `fanrenyi-markdown.*`。

### 注意点1

如果你的markdown编辑器中没有彩色主题 `Solarized_colorful` 等, 在vscode设置 `settings.json`中增加以下配置.

```json
{
  "workbench.editorAssociations": {
    "*.md": "fanrenyi-markdown.viewer",
    "*.markdown": "fanrenyi-markdown.viewer"
  }
}
```

![](https://images.cnblogs.com/cnblogs_com/Renyi-Fan/1188097/o_260604123900_no_colorful_theme02.jpg)

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

在编辑器打开右键菜单可将markdown导出为pdf, docx或者html, pdf依赖于chromium, 可通过 `fanrenyi-markdown.chromiumPath`配置chromium浏览器路径.

![](https://images.cnblogs.com/cnblogs_com/Renyi-Fan/1188097/o_260604124858_export02.jpg)

### 注意点4

编辑器在彩色主题的情况下，导出的html和pdf为彩色。编辑器在非彩色主题的情况下，导出的html和pdf为非彩色。

## 自定义 Markdown 样式

自定义样式通过专门的 `Custom` 编辑器主题生效，可以同时影响 Vditor 编辑器和导出的 PDF。

最简单的使用方式：

1. 执行命令 `Markdown: Create Custom Style Example File`。
2. 插件会创建 `.vscode/markdown-custom-style.css`。
3. 插件会自动把 `fanrenyi-markdown.editorTheme` 切换为 `Custom`。
4. 修改并保存生成的 CSS 文件即可。

也可以在 `settings.json` 中手动配置：

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

`fanrenyi-markdown.customStyle.variable` 只修改对应的单个属性。例如 `h2Color` 只会修改二级标题颜色。如果需要边框、间距、阴影等更复杂的样式，请写在 CSS 文件中。

支持的变量字段：

`fontFamily`, `fontSize`, `lineHeight`, `textColor`, `backgroundColor`, `h1Color`, `h2Color`, `h3Color`, `h4Color`, `h5Color`, `h6Color`, `h1FontSize`, `h2FontSize`, `h3FontSize`, `linkColor`, `strongColor`, `emphasisColor`, `blockquoteBorderColor`, `blockquoteBackgroundColor`, `inlineCodeColor`, `inlineCodeBackground`, `codeBlockColor`, `codeBlockBackground`, `codeFontFamily`, `tableBorderColor`, `tableHeaderColor`, `tableHeaderBackground`, `tableEvenRowBackground`.

样式优先级：

1. 主题 CSS。
2. `fanrenyi-markdown.customStyle.cssFile`。
3. `fanrenyi-markdown.customStyle.css`。
4. `fanrenyi-markdown.customStyle.variable`。

生成的 `markdown-custom-style.css` 中包含更详细的选择器示例，覆盖标题、段落、列表、任务列表、引用、代码、表格、图片、数学公式、Mermaid 图、details 折叠块以及部分 Vditor UI 区域。Vditor 编辑器中的选择器通常以 `#vditor` 开头；导出 PDF 中的选择器通常以 `.content-wrapper` 开头。

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
