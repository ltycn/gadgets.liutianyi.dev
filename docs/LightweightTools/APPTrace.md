---
sidebar_label: APPTrace
sidebar_class_name: lightweight tools
---

# APPTrace

APPTrace是用于测量windows软件开启速度的小工具。

在一些大型软件的启动过程中，我发现在呈现最终用户可交互的界面之前，通常会出现若干个子程序子窗口，用于加载程序所需的额外组件。而从用户启动程序开始的这一秒，主进程的窗口标题也会随时间不断变化。

这个小程序要做的，是通过监控主程序窗口标题的变化，来达到记录应用启动时间的效果。

## 使用方法

```
AppTrace.exe "c:\path\to\exe"
```

![](.\APPTrace\1.png)


:::tip

不同的应用程序在启动过程中会创建若干不同的窗口加载程序。请在第一次打开时仔细观察最后弹出主程序窗口的标题，并以此为标准判断打开的时间

:::

![](.\APPTrace\2.png)

## 可参考标题名

| DCC    | Title                                                         | Showup Times |
|--------|---------------------------------------------------------------|--------------|
| 3DMax  | Untitled - Autodesk 3ds Max 2025                              | 1            |
| AutoCAD| Autodesk AutoCAD 2025 - [Start]                               | 2            |
| MAYA   | untitled - Autodesk MAYA 2025.1: untitled                     | 1            |
| AE     | Adobe After Effects 2024 - Untitled Project.aep               | 1            |
| AI     | Adobe Illustrator 2024                                        | 1            |
| LR     | Lightroom Catalog - Adobe Photoshop Lightroom Classic - Library| 1            |
| PS     | Adobe Photoshop 2024                                          | 1            |
| Excel  | EXCEL-10M-COUNT - Protected View - Excel                      | 1            |
| Excel  | EXCEL-100M-COUNT - Protected View - Excel                     | 1            |
| PPT    | PPT-30M-COUNT - Protected View - Microsoft PowerPoint         | 1            |
| PPT    | PPT-100M-COUNT - Protected View - Microsoft PowerPoint        | 1            |
