# Typora Theme: npy-notebook theme

[English](./README.md) | [简体中文](./README-zh_CN.md)

This theme is a derivative of the [Gitbook Theme](https://theme.typora.io/theme/Gitbook/), customized with personal touches. Gitbook Theme is open-sourced under the [GPL 3.0](https://github.com/h16nning/typora-gitbook-theme?tab=GPL-3.0-1-ov-file).

## Changelog 📚

- [x] 2024.07.16: Modify the font source file of PingFang SC.
- [x] 2024.07.08: At the request of [@Jacklouis0425](https://github.com/Jacklouis0425), and considering that many users prefer to use the dark mode, I have added the Dark Mode feature. The README documentation has been updated accordingly.

## Installation 🔨

### Install the Typora application

Please refer to [the installation guidance from the official website of Typora](https://typora.io/), activating or not activating the license does not affect the theme from taking effect and being used normally.

### Install this theme

This repository provides two themes for Typora users: light and dark. The CSS files are named `npy-notebook.css` and `npy-notebook-dark.css`, respectively.

1. Launch Typora and enter the `Theme` page of the Menu.

   ![image-20240709112348566](https://raw.githubusercontent.com/bonjour-npy/Image-Hosting-Service/main/typora_imagesimage-20240709112348566.png)

2. Click the button `Open Theme Folder`。

3. **Copy all of the files** from the `npy-notebook` folder, the `npy-notebook.css` and `npy-notebook-dark.css` files into the **Typora Theme Folder**.

   - If you are using the source code from the repository, you can find the files in the `src` directory.
   - If you are using the zip file from the Releases page, you can extract the files from the zip file.

   **The `npy-notebook` folder** contains the fonts and configuration files that are required for the themes to work.

   **The `npy-notebook.css` and `npy-notebook-dark.css` files** contain the rest of the configuration files for the themes.

4. Simply restart Typora and you can select the `NpyNotebook` or `NpyNotebookDark` theme from the `Themes` page.

## Features Overview ✨

### Automatic Title Numbering

Leveraging Markdown's title syntax, upon completing input of the title and pressing Enter, the theme will automatically add sequential numbers in front of the title based on the current title level and position. 

Numbering starts from level 2 titles (H2) as the first level of the automatic numbering scheme. For instance, the first level 2 title will be numbered as `1`, the first level 3 title will be numbered as  `1.1`, and the number of the second level 2 title will be `2`.

See the figure below for the results. 

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

### Fonts

#### Font size

The default global font size has been increased from 16px to 18px. The body font size for writing paragraphs has been increased from 0.95rem to 1rem.

#### Font family

When you need to mix Chinese and English in your notes, you can't go wrong with the classic serif font family combo—SimSun and Times New Roman.

```css
font-family: "Times New Roman", serif;
```

Of course, many users prefer sans-serif fonts for website UIs and digital reading. In this case, pairing PingFang (for Chinese) with SF Pro (for English) from iOS, iPadOS, and macOS is an excellent choice.

This repository offers options for both serif and sans-serif font pairings mentioned above. The default setting is the serif combination. If you want to switch to sans-serif fonts, you can make the following changes to the theme file `npy-notebook.css`.

```css
/* 将下面有衬线字体代码行注释，并取消无衬线字体代码行注释。 */
--font-family: "Times New Roman", serif;
/* --font-family: 'SF Pro Display Medium', 'PingFangSC Medium', sans-serif; */
```

### Modified the style of headings

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

### Modified the highlighting color of code blocks

```css
    --codeboxes: #373737;
    --codeboxes-lighter: #646464;
```

### Modify the highlighting color of backticks

Since the backtick highlighting directly used the `borders` color, we modified the `borders` color for the dark theme and adjusted the font and font size for backtick highlighting.

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

### Other features of the [Gitbook Theme](https://theme.typora.io/theme/Gitbook/)

Please refer to [the official Gitbook Theme website](https://theme.typora.io/theme/Gitbook/).

## Feedback 👍

If you encounter any issues or bugs while using this, I'd love to hear from you!

Feel free to join the discussion in the repository's [Issues](https://github.com/bonjour-npy/typora-npy-notebook-theme/issues) section or contribute through [Pull requests](https://github.com/bonjour-npy/typora-npy-notebook-theme/pulls).