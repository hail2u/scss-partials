SCSS Partials
=============

SCCSファイルでインポートして使用する端切れ(partial)を放り込むリポジトリです。


INSTALLATION
------------

Three options are available:

  1. [Download package][1]
  2. Clone with Git: `$ git clone https://github.com/hail2u/scss-partials.git`
  3. Install with [Bower][2]: `$ bower install --save-dev hail2u-scss-partials`


USAGE
-----

`@import`を使ってSCSSファイルでインポートします。

    @import "reset";
    @import "clearfix";

拡張子とファイル名の先頭の`_`は不要です。


### \_clearfix.scss

clearfixを適用することができます。

    header {
      @include clearfix;
    }

IE6等のサポートが必要ないなら、生成されるコードがシンプルなminiclearfixを使用することもできます。

    article {
      @include miniclearfix;
    }


### \_emboss.scss

文字に`text-shadow`による軽いエンボスをかけることができます。

   h1 {
     @include black-emboss();
   }


### \_meyerweb-reset.scss

[meyerwebで公開されているReset CSS][3]をインポートすることができます。


### \_natural.scss

[結局どうすればいいの？ - Dive Into HTML5][4]などで使われているシンプルなスタイルをインポートすることができます。文字や背景、リンクなどの色やフォントサイズ等の設定を変更することも可能です。

    $link: green;
    $font-size: 12px;
    
    @import "natural";


### \_reset.scss

[hail2u.net][5]で使用していたリセットCSSをインポートすることができます。


### \_speech-bubble.scss

吹き出しを作ることができます。

    .speech-bubble {
      @include speech-bubble(#9cf, 6px, 12px, $24px);
    }

枠線付きを作ることもできます。

    .bordered-speech-bubble {
      @include bordered-speech-bubble(#9cf, #369, 4px, 8px, 16px, $24px);
    }


#### 引数

  1. `$bgcolor`: 背景及び吹き出しの尻尾の色
  2. `$round-size`: 吹き出しの四隅の丸さ
  3. `$tail-size`: 吹き出しのサイズ
  4. `$tail-position`: 吹き出しの位置


### \_vanilla.scss

[Vanilla CSS Un-Reset][6]をインポートすることができます。


### \_vendor-extension.scss

ベンダー拡張プロパティとCSS3でのプロパティを一括指定することができます。

  * box-sizing
  * transform
  * transform-origin
  * transform-style
  * perspective
  * perspective-origin
  * backface-visibility
  * transition
  * transition-property
  * transition-duration
  * transition-timing-function
  * transition-delay

値の指定はCSS3の仕様に従います。


### \_yui-base-min.scss

[YUI 3のCSS Base][7]をインポートすることができます。


### \_yui-fonts-min.scss

[YUI 3のCSS Fonts][8]をインポートすることができます。インポートしたドキュメントでは変数を使ってフォントサイズの変更が行えます。

    h1 {
      font-size: $yui-24px;
    }

`$yui-10px`から`$yui-26px`まで定義されています。


### \_yui-reset-min.scss

[YUI 3のCSS Reset][9]をインポートすることができます。


### \_fake-aa.scss

CSS Transformの`rotate(360deg)`で軽くぼかしがかかることを利用して、Google Chromeでフォントがギザギザに見えることがある問題への対処を行います。

    .fake-aa {
      @include fake-aa;
    
      font-family: "MS PMincho", serif;
    }


### \_grid-overlay.scss

ページ全体にグリッドのオーバーレイ画像をCSSグラデーションを利用して表示します。CSSグラデーションを利用しているためInternet Explorer 9以下やOpera 10以下では表示されません。

    body {
      @include grid-overlay(60px, 20px);
    }


#### 引数

  1. `$column`: カラムの幅
  2. `$gutter`: 溝(カラムとカラムの間)の幅


### \_normalize.scss

[normalize.css][10]をインポートすることができます。


### \_context-reset.scss

全てのプロパティーをその初期値にリセットすることができます。


### \_elegant-button.scss

少しグラデーションのかかったきれいなボタンを作ることができます。

    .elegant-button {
      @include elegant-button(#39c, #fff);
    }


#### 引数

  1. `$bg`: ボタンの背景色
  2. `$fg`: ボタンの前景色(文字色)


### \_image-replacement.scss

画像置換を行うためのテキストを隠すためのスタイルを導入できます。置換する画像の指定やサイズの決定は行えません。`text-indent`プロパティーを使ったものと`font-size`プロパティーを使ったもの、擬似要素を使ったものの3種類があります。


### \_black-prints.scss

印刷向けに文字色や背景色をモノクロにリセットするためのスタイルを導入できます。印刷向けスタイルシートをインラインで埋め込む時に役に立ちます。


### \_corpolate-colors.scss

様々な企業のコーポレートカラーを手軽に参照できます。


### \_selection.scss

選択した時のスタイルをまとめて指定できます。

    ::-moz-selection {
      @include selection(#fff, #369);
    }
    
    ::selection {
      @include selection(#fff, #369);
    }


### \_lego-colors.scss

レゴブロックのカラースキームを手軽に参照できます。


### \_centering.scss

縦方向または横方向、及び両方向に中央揃えすることができます。

    .centered-hv {
      @include centering-known();
    
      width: 80px;
      height: 80px;
    }

`width`と`height`プロパティーは必須です。ウィンドウではなく親要素のサイズを基準に中央揃えしたい場合は、親要素に`position: relative`が必要になります。

`centering-unknown`というミックスインもありますが実験段階で、上手く動かないかもしれません。


#### 引数

  1. `$horizontal`: 横方向に中央揃えするかどうか
  2. `$vertical`: 縦方向に中央揃えするかどうか


LICENSE
-------

SCSSファイルにライセンス条項が明記されていない限りすべて[パブリック・ドメイン][11]として提供されています。


[1]:  https://github.com/hail2u/scss-partials/archive/master.zip
[2]:  http://bower.io/
[3]:  https://github.com/hail2u/scss-column-equation.git
[4]:  http://hail2u.net/documents/diveintohtml5-semantics.html
[5]:  http://hail2u.net/
[6]:  http://noscope.com/vanilla-css
[7]:  http://developer.yahoo.com/yui/3/cssbase/
[8]:  http://developer.yahoo.com/yui/3/cssfonts/
[9]:  http://developer.yahoo.com/yui/3/cssreset/
[10]: http://necolas.github.io/normalize.css/
[11]: http://unlicense.org/
