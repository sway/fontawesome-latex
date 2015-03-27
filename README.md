# fontawesome.sty

[Font Awesome](http://fortawesome.github.io/Font-Awesome/) is a free (CC-BY-3.0) icon font from GitHub, that contains several different icons for various purposes. It is designed for web usage, and thus all the characters are defined in the private unicode range to avoid confusing screen readers.

I wanted to use some of the glyphs in my resumé in (Xe)LaTeX, however, due to the implementation it is not really easy to access them directly. To be able to include the individual glyphs in a document I created a translation table (`fontawesome.sty`), which defines each icon/glyph using its number, such as:

```
\def\faUploadAlt{\symbol{"F093}}
\def\faLemon{\symbol{"F094}}
\def\faPhone{\symbol{"F095}}
\def\faCheckEmpty{\symbol{"F096}}
\def\faBookmarkEmpty{\symbol{"F097}}
```

The codes are taken from the FontAwesome LESS/CSS file, and the names of the individual icons are preserved, only prefixed with fa and camel-cased to conform with LaTeX conventions.

The usage is simple, and it requires XeLaTeX to be used as compiler and the font to be installed as a system font.

1. Save the `fontawesome.sty` file from the gist into your project folder.
2. Put `\usepackage{fontawesome}` into the preamble
3. Define the font command for FontAwesome: `\newfontfamily{\FA}{FontAwesome Regular}`. This step requires fontspec and XeLaTeX, as regular LaTeX does not support direct usage of TTF/OTF system fonts.
4. Redefine required characters (optional): `\def\twitter{{\FA \faTwitter}}`
5. Use: `\href{http://twitter.com/swaycz}{\twitter\ swaycz}`

The outcome looks like this:

![](https://coderwall-assets-0.s3.amazonaws.com/uploads/picture/file/241/Screen_Shot_2012-07-13_at_1.32.16_AM.png)


