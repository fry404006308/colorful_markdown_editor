# Markdown Editor Colorful

## Markdown

English | [简体中文](README-CN.md) | [繁體中文](README-TW.md)

A powerful and versatile markdown viewer that uses a WYSIWYG editor and supports viewing Word, Excel files, etc.

![](https://files.cnblogs.com/files/Renyi-Fan/colorful_markdown_editor_demo.gif)

This extension changes the default markdown editor to the vditor.

### Note 1

If your Markdown editor does not have colorful themes such as `Solarized_colorful`, add the following configuration to the `settings.json` file in VS Code.

```json
{
  "workbench.editorAssociations": {
    "*.md": "fanrenyi.markdownViewer",
    "*.markdown": "fanrenyi.markdownViewer"
  }
}
```

![](https://img2024.cnblogs.com/blog/1163900/202605/1163900-20260506104703488-371796145.jpg)

### Note 2

If you want to use the original vscode editor, insert this in your `settings.json`.

```json
{
  "workbench.editorAssociations": {
    "*.md": "default",
    "*.markdown": "default"
  }
}
```

### Note 3

Right-click in the editor to export Markdown as PDF, DOCX or HTML. PDF export relies on Chromium, and you can configure the Chromium browser path via `vscode-office.chromiumPath`.

![](https://img2024.cnblogs.com/blog/1163900/202605/1163900-20260505165615628-1039343710.png)

### Note 4

Only when the editor uses the colorful theme will the exported PDF be in color.

When the editor uses a colored theme, the exported HTML and PDF will be in color.

When the editor uses a non-colored theme, the exported HTML and PDF will be non-colored.

## Shortcuts

Shortcuts: Base on [Vditor shortcuts](shortcut.md) and more:

- Move list up: `Ctrl Alt I` / `⌘ ^ I`
- Move list down: `Ctrl Alt J` / `⌘ ^ J`
- Edit in VS Code: `Ctrl Alt E` / `⌘ ^ E`

### Summary

| Name                   | Keymap               | Remarks           |
| ---------------------- | -------------------- | ----------------- |
| Emoji                  | :/⌘ E                |                   |
| Headings               | Ctrl H / ⌘ H         | see below         |
| Bold                   | Ctrl B / ⌘ B         |                   |
| Italic                 | Ctrl I / ⌘ I         |                   |
| Strikeout              | Ctrl S / ⌘ S         |                   |
| Link                   | Ctrl K / ⌘ K         | see below         |
| Unordered List         | Ctrl L / ⌘ L         | see below         |
| Ordered List           | Ctrl O / ⌘ O         | see below         |
| Task List              | Ctrl J / ⌘ J         | see below         |
| Blockquote             | Ctrl ; / ⌘ ;         | see below         |
| Horizontal             | Ctrl Shift H / ⌘ ⇧ H |                   |
| Code Block             | Ctrl U / ⌘ U         | see below         |
| Inline Code            | Ctrl G / ⌘ G         |                   |
| Insert Block to Before | Ctrl Shift B / ⌘ ⇧ B | wysiwyg & ir mode |
| Insert Block to End    | Ctrl Shift E / ⌘ ⇧ E | wysiwyg & ir mode |
| Table                  | Ctrl M / ⌘ M         | see below         |
| Undo                   | Ctrl Z / ⌘ Z         |                   |
| Redo                   | Ctrl Y / ⌘ Y         |                   |
| Hide Edit              | Ctrl P / ⌘ P         | sv mode           |
| Fullscreen             | Ctrl ' / ⌘ '         |                   |
| Move Block to Up       | Ctrl Shift U / ⌘ ⇧ U | wysiwyg & ir mode |
| Move Block to Down     | Ctrl Shift D / ⌘ ⇧ D | wysiwyg & ir mode |
| Remove                 | Ctrl Shift X / ⌘ ⇧ X | wysiwyg mode      |
| At User                | @                    |                   |
| Mistyped               | Backspace            |                   |

### Headings Ctrl H / ⌘ H

| Name    | Keymap                                 |
| ------- | -------------------------------------- |
| Bigger  | Ctrl + / ⌘ +                           |
| Smaller | Ctrl - / ⌘ -                           |
| H1-H6   | Ctrl Alt 1/2/3/4/5/6 / ⌘ ⌥ 1/2/3/4/5/6 |
| Menu    | Ctrl H / ⌘ H                           |

Tips:

- Resize editor via ctrl/cmd+mouse scroll.
- Hyperlinks can be opened by ctrl/meta+click or double-click.

## Introduction

This extension supports previewing these common office file formats in VS Code.

- Markdown: .md
- Excel: .xls, .xlsx, .csv
- Word: .docx
- Svg: .svg
- Pdf: .pdf
- Font: .ttf, .otf, .woff, .woff2
- HttpRequest: .http
- Windows Reg: .reg
- Compressed file: .zip, .jar, .vsix, .rar

## HTML

The html editor supports live viewing. Press ctrl+shift+v to open the live view.

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
