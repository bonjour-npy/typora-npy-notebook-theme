# Typora 主题：npy-notebook theme

该主题基于 [Gitbook Theme](https://theme.typora.io/theme/Gitbook/) 并加入个人喜好因素修改而来，Gitbook Theme 根据 [GPL 3.0](https://github.com/h16nning/typora-gitbook-theme?tab=GPL-3.0-1-ov-file) 开源。

## 更新日志 📚

- [x] 2024.07.08：应亲爱的[譞譞同学（@Jacklouis0425）](https://github.com/Jacklouis0425)的要求，考虑到部分高手都喜欢用暗黑模式，因此新增了 Dark Mode，README 文档已相应更新。

## 安装方法 🔨

### 安装 Typora 软件

根据[官网](https://typora.io/)教程完整 Typora 软件的安装，许可证的激活与否不影响主题生效以及正常使用。

### 安装主题

本仓库为 Typora 用户提供了明、暗两种主题，css 文件分别为 `npy-notebook.css` 以及 `npy-notebook-dark.css`。

1. 打开 Typora 后进入设置的`主题`页面。

   ![image-20240708113741394](https://raw.githubusercontent.com/bonjour-npy/Image-Hosting-Service/main/typora_imagesimage-20240708113741394.png)

2. 点击`打开主题文件夹`。

3. 将仓库中 `src` 目录中或 `Release` 中下载的 zip 压缩包中的全部文件（`npy-notebook` 文件夹以及 `npy-notebook.css`、`npy-notebook-dark.css` 文件）复制、粘贴至上一步打开的主题文件夹目录中。

   `npy-notebook` 目录中包含了主题生效所需的字体及配置文件，各 css 文件中是主题其它的定义配置文件。

4. 重启 Typora 程序，在设置的主题选项中选择  `NpyNotebook`  或 `NpyNotebookDark` 主题即可看到生效。

## 特性说明 ✨

### 增加了标题自动编号

使用 Markdown 的标题语法，当完成键入并敲击回车后，主题会自动根据当前标题的等级以及所在位置，在键入字体前方加入自动编号，编号从 2 级标题 H2 作为自动编号的 1 级序号。如第一个 2 级标题序号是 `1`，其下的第一个 3 级标题序号是 `1.1`，第二个 2 级标题序号是 `2`。

效果如下图所示。

![image-20240708114525906](https://raw.githubusercontent.com/bonjour-npy/Image-Hosting-Service/main/typora_imagesimage-20240708114525906.png)

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

### 字体

#### 字体大小调整

全局字体从 16 px 调整为 18 px，书写段落 body 字体从 0.95 rem 调整为 1 rem。

#### 字体的选择

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

### 标题样式调整

```css
/* 标题样式进行统一调整，修改 1 级标题分割线像素厚度，修改各级标题段前后间距 */

h1 {
    font-size: 2.2rem;
    font-weight: 700;
    line-height: 1.5;
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
    /* padding-bottom: 0.5rem; */
    border-bottom: solid 3px var(--borders);
}

h2 {
    font-size: 1.7rem;
    font-weight: 700;
    line-height: 1.5;
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
}

h3 {
    font-size: 1.375rem;
    font-weight: 700;
    line-height: 1.5;
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
}

h4 {
    font-size: 1.15rem;
    font-weight: 700;
    line-height: 1.5;
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
}

h5 {
    font-size: 0.95rem;
    font-weight: 700;
    line-height: 1.5;
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
}

h6 {
    font-size: 0.95rem;
    font-weight: 400;
    line-height: 1.5;
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
}
```

### 代码块高亮颜色调整

```css
    --codeboxes: #373737;
    --codeboxes-lighter: #646464;
```

### 反引号高亮颜色调整

反引号高亮直接使用了 `borders` 的颜色，因此修改了暗黑主题下的 `borders` 颜色，并修改了反引号高亮的字体和字号。

```css
/* 修改反引号高亮的样式 */
code {
    padding: 0.2rem 0.4rem;
    background-color: var(--borders);
    font-size: 1rem;
    font-family: var(--font-family);
    border-radius: 0.2rem;
    box-decoration-break: clone;
    -webkit-box-decoration-break: clone;
}
```

### Gitbook 主题的其他特性

[Gitbook Theme](https://theme.typora.io/theme/Gitbook/) 的其他特性请参考其官方网站。

## 讨论与交流 👍

由于 css 样式大部分继承自 [Gitbook Theme](https://theme.typora.io/theme/Gitbook/)，因此大概率没法直接上架 Typora 官方主题商店：[Typora Themes Gallery](https://theme.typoraio.cn/)。

不过大家如果在使用过程中遇到什么问题或者 bug，非常欢迎你们在仓库的 [Issues](https://github.com/bonjour-npy/typora-npy-notebook-theme/issues) 或 [Pull requests](https://github.com/bonjour-npy/typora-npy-notebook-theme/pulls) 环节一起讨论交流。

感谢[萱萱同学（@xuanx33）](https://github.com/xuanx33)的陪伴和支持，希望你可以认真做笔记，祝学习和工作顺利。