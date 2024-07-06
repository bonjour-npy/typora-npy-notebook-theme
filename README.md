# Typora 主题：npy-notebook theme

该主题基于 [Gitbook Theme](https://theme.typora.io/theme/Gitbook/) 并加入个人喜好因素修改而来，Gitbook Theme 根据 [GPL 3.0](https://github.com/h16nning/typora-gitbook-theme?tab=GPL-3.0-1-ov-file) 开源。

## 安装方法

### 安装 Typora 软件

根据[官网](https://typora.io/)教程完整 Typora 软件的安装，激活与否不影响主题的使用。

### 安装主题

1. 打开 Typora 后进入设置的`主题`页面。

   ![image-20240706182526264](https://raw.githubusercontent.com/bonjour-npy/Image-Hosting-Service/main/typora_imagesimage-20240706182526264.png)

2. 点击`打开主题文件夹`。

3. 将仓库中 `src` 目录中的全部文件（`npy-notebook` 文件夹以及 `npy-notebook.css`文件）复制，粘贴至上一步打开的目录中。

4. 重启 Typora 程序，在设置的主题选项中选择 `NpyNotebook` 主题即可看到效果。

## 特性说明

### 增加了标题自动编号

使用 Markdown 的标题语法，当完成键入并敲击回车后，主题会自动根据当前标题的等级以及所在位置，在键入字体前方加入自动编号，编号从 2 级标题 H2 作为自动编号的 1 级序号。如第一个 2 级标题序号是 `1`，其下的第一个 3 级标题序号是 `1.1`，第二个 2 级标题序号是 `2`。

效果如下图所示。

![image-20240706183534884](https://raw.githubusercontent.com/bonjour-npy/Image-Hosting-Service/main/typora_imagesimage-20240706183534884.png)

```css
/* Add List Number for each Heder here. */

#write h1 {
    counter-reset: h2;
  }
  #write h2 {
    counter-reset: h3;
  }
  #write h3 {
    counter-reset: h4;
  }
  #write h4 {
    counter-reset: h5;
  }
  #write h5 {
    counter-reset: h6;
  }
  
  #write h2:before {
    counter-increment: h2;
    content: counter(h2);
    margin-right: 0.5em;
  }
  
  #write h3:before, h3.md-focus.md-heading:before {
    counter-increment: h3;
    content: counter(h2) "." counter(h3);
    margin-right: 0.5em;
  }
  
  #write h4:before, h4.md-focus.md-heading:before {
    counter-increment: h4;
    content: counter(h2) "." counter(h3) "." counter(h4);
    margin-right: 0.5em;
  }
  
  #write h5:before, h5.md-focus.md-heading:before {
    counter-increment: h5;
    content: counter(h2) "." counter(h3) "." counter(h4) "." counter(h5);
    margin-right: 0.5em;
  }
  
  #write h6:before, h6.md-focus.md-heading:before {
    counter-increment: h6;
    content: counter(h2) "." counter(h3) "." counter(h4) "." counter(h5) "." counter(h6);
    margin-right: 0.5em;
  }
```

### 字体的选择

当你的笔记需要进行中英文混排时，选择经典的有衬线（serif）字体家族搭配总不会让你失望——宋体与新罗马。

```css
font-family: "Times New Roman", serif;
```

当然，不排除大部分同学对于网站 UI 等电子阅读的偏好是无衬线字体（sans-serif），这时选择来自 iOS、iPadOS 以及 macOS 等的苹方与 SF Pro 字体进行搭配也是非常好的选择。

本仓库为以上两种有衬线与无衬线字体搭配均提供了选择，默认为有衬线搭配。当你需要切换为无衬线字体时，对主题文件 `npy-notebook.css` 进行以下修改即可。

```css
/* 将下面有衬线字体代码行注释，并取消无衬线字体代码行注释。 */
--font-family: "Times New Roman", serif;
/* --font-family: 'SF Pro Display Medium', 'PingFangSC Medium', sans-serif; */
```

### Gitbook 主题的其他特性

[Gitbook Theme](https://theme.typora.io/theme/Gitbook/) 的其他特性请参考其官方网站。