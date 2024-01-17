# beamerTheme-Satori

[English](/README-en.md)

---

## 概要

Satoriテーマは、日本語環境に対応したBeamerテーマ（LuaLaTeX専用）です。

ネットの海には多数の素敵なBeamerテーマがありますが、その多くが海外製で、

- 日本語を使用するためにプリアンブルに書くべき事柄が多い
- 日本語文字とローマ字の太さがちぐはぐになることがある

等の問題があります。  
Satoriテーマはデフォルトでフォント・ルビなどの設定が組み込まれ、すぐに日本語スライドを作成できます。

---

## 使い方

1. 任意のtexファイルを作成する。
   - [template.tex](/template.tex)を元にするとよい。
   - 同じディレクトリ階層に[beamerthemesatori.sty](themeFile/beamerthemesatori.sty)を置くこと。
2. スライド内容を記述し、UTF-8で保存する。
   - Beamerでのスライド記述方法は、適宜調べること。
3. 作成したtexファイルと同じ階層でターミナル起動。
   - Windows：エクスプローラーで対象フォルダを開いた状態で、アドレスバーに`cmd`または`powershell`と入力してEnter。
   - Mac：Finderで対象フォルダを右クリックして、コンテキストメニューから「フォルダに新規ターミナル」をクリック。
4. タイプセット（`lualatex ファイル名.tex`）。
   - 拡張子`.tex`は記載しなくてもよい。

---

## 独自機能

### 機能1：色相指定

プリアンブルで以下の指定をすると、色相に応じたカラーテーマが自動で設定されます。

```latex
\defineColorWithHue{色相}
```

- 色相については以下のサイトなどを参照。
  - [HSL/HSV カラーピッカー(お便利ツール.com)](https://www.oh-benri-tools.com/tools/color/hsl-hsv-color-picker)
  - [カラー値計算(tomariのホームページ)](https://tomari.org/main/java/color/ccal.html)
  - [HSB Color Picker](https://codepen.io/HunorMarton/details/eWvewo)
- 大抵のお絵かきソフトでは、カラーサークル周辺にHSV値が表示されてる筈。
  - そのなかの`H`が色相(Hue)。カラーサークルの外周部分に相当。
- 色相の固有明度に応じて、大体よい感じに設定される（ハズ）。
  - 詳細は[sample.pdf](/sample.pdf)を参照。

### 機能2：タイトルデザイン

プリアンブルで以下の指定をすると、タイトルページのデザインを簡単に変更できます。

```latex
\titlePattern{X}
```

- 上記`X`にはA～Jの任意のローマン・アルファベットを指定。
- タイトルページデザインのサンプルは、[titlepages.pdf](/titlepages.pdf)を参照。
- 1回のタイプセットで表示崩れが発生する場合、再度タイプセットすること。

### 機能3：ウォーターマーク

プリアンブルで以下の指定をすると、好きな画像をウォーターマークとして使用できます。

```latex
\waterMark{画像}{不透明度}{サイズ(1＝画面一杯)}{x座標移動}{y座標移動}{回転(反時計回り)}
```

- `x座標移動`, `y座標移動`は、単位つきで指定。デフォルト（どちらも`0`）は画面中央。
- `回転(反時計回り)`は回転させたい度数を指定（単位不要：`30`と指定すれば30度左回転）。
- 1回のタイプセットで表示崩れが発生する場合、再度タイプセットすること。

例：

```latex
\waterMark{hoge.png}{.05}{1.2}{-3cm}{-0.5cm}{20}
```

### 機能4：右上ロゴ表示

プリアンブルで以下の指定をすると、好きな画像を各ページ右上に表示させられます。

```latex
\renewcommand{\logoImage}{hoge.png}
```

- ロゴ表示したくない場合は上記をコメントアウトする。

---

## 使用許諾

[LICENCEファイル](/LICENCE)を参照。

---

## 謝辞

このテーマはNikolai Obedin氏の[beamer-modernテーマ](https://github.com/nkly/beamer-modern)をベースとして作成されました。  
素晴らしいテーマをパブリック・ドメインで公開してくださった氏に感謝の意を表します。
