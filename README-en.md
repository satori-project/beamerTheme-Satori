# beamerTheme-Satori

[日本語](/README.md)

---

## Overview

Satori Theme is a Beamer theme with Japanese language support.

---

## Usage

1. Create any tex file.
   - You can use [template.tex](/template.tex) as a base.
   - Place [beamerthemesatori.sty](beamerthemesatori.sty) in the same directory.
2. Describe the slide contents and save the file in UTF-8.
   - Find out how to describe slides in Beamer on your own.
3. Start a terminal at the same directory as the created tex file.
   - Windows: With the target folder open in Explorer, type `cmd` or `powershell` in the address bar and press Enter.
   - Mac: Right-click the target folder in the Finder and click `New Terminal at Folder` from the context menu.
4. Typeset (`lualatex fileName.tex`).
   - It is not necessary to mention the extension `.tex`.

---

## Features

### 1) Hue customisation

By specifying the following in the preamble, the colour theme is automatically set according to the specified hue.

```latex
\defineColorWithHue{Hue:0-360}
```

- The following websites and others provide a good overview of hues.
  - [HSB Color Picker](https://codepen.io/HunorMarton/details/eWvewo)
- The appropriate saturation and lightness are automatically set according to the intrinsic lightness of the hue.
  - See [sample.pdf](/sample.pdf) for more information on this.

### 2) Title page customisation

By specifying the following in the preamble, you can easily customise the design of title page.

```latex
\titlePattern{X}
```

- Specify any Roman alphabet from A to J for `X` above.
- See [titlepages.pdf](/titlepages.pdf) for a sample title page pattern.
- If the display appears distorted after typesetting, it should be typeset again.

### 3) Watermark

By specifying the following in the preamble, you can use any image you like as a watermark.

```latex
\waterMark{imageFile}{opacity}{size(height)}{x-shift}{y-shift}{rotate(counterclockwise)}
```

- `x-shift` and `y-shift` require a unit. If 0 is given, the display will be centred on the screen.
- `rotate(counterclockwise)` is the number of degrees you want to rotate. (No units required.)
- If the display appears distorted after typesetting, it should be typeset again.

e. g.

```latex
\waterMark{hoge.png}{.05}{1.2}{-3cm}{-0.5cm}{20}
```

### 4) Logo display

By specifying the following in the preamble, any image you like can be displayed at the top right of each page.

```latex
\renewcommand{\logoImage}{hoge.png}
```

- Comment out the above if you do not want the logo to be displayed.

---

## Licence

See [LICENCE file](/LICENCE).

---

## Acknowledgements

This Beamer theme is based on [beamer-modern theme](https://github.com/nkly/beamer-modern) by Nikolai Obedin.  
I would like to thank him for releasing this wonderful theme into the public domain.
