# Neurodata Marp Poster Template

Instructions for using this template in VSCode:
- Download Marp extension for VSCode.
- In VSCode `Preferences->Settings`, search Marp. Enable `Marp: Enable HTML`.
- Add our CSS theme to the list of markdown themes. This can be done by going into `.vscode/settings.json` and adding the css file to the list of Marp themes:

```
{
    ...
    "markdown.marp.themes": [
        "<local-relative-path>/poster.css"
    ]
    ...
}
```
 where `<local-relative-path>` is the path relative to the folder that you have open in VSCode. Alternatively, you can add the path to `Preferences -> Settings` then search `Markdown › Marp: Themes`

- Add the following header to your poster file (`.md`):

```
---
marp: true
theme: poster
paginate: false
size: 36:24
---
```

- You should be able to automatically render youor poster file when by opening the preview pane to the side.
