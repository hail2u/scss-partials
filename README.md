SCSS Partials
=============

SCCSファイルにインポートして使用する端切れ(partial)を放り込むリポジトリです。


USAGE
-----

`@import`を使ってSCSSファイルでインポートします。

    @import "reset";
    @import "clearfix";

拡張子とファイル名の先頭の`_`は不要です。


### \_clearfix.scss

clearfixを簡単に利用することができます。

    header {
      @include clearfix;
    }

IE6等のサポートが必要ないなら、生成されるコードがシンプルなminiclearfixを使用することもできます。

    article {
      @include miniclearfix;
    }


### \_emboss.scss

`text-shadow`による軽いエンボスを手軽にかけることができます。

   h1 {
     @include black-emboss();
   }


### \_meyerweb-reset.scss

[meyerwebで公開されているReset CSS](http://meyerweb.com/eric/tools/css/reset/)をインポートすることができます。


### \_natural.scss

[結局どうすればいいの？ - Dive Into HTML5](http://hail2u.net/documents/diveintohtml5-semantics.html)などで使われているシンプルなスタイルをインポートすることができます。文字や背景、リンクなどの色やフォントサイズ等の設定を変更することも可能です。

    $link: green;
    $font-size: 12px;
    
    @import "natural";


### \_reset.scss

[hail2u.net](http://hail2u.net/)で使用しているリセットCSSをインポートすることができます。


### \_speech-bubble.scss

吹き出しのデザインを変更することができます。

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

[Vanilla CSS Un-Reset](http://noscope.com/vanilla-css)をインポートすることができます。


### \_vendor-extension.scss

ベンダー拡張プロパティとCSS3でのプロパティを一括指定することができます。

  * background-origin
  * background-size
  * border-radius
  * box-shadow
  * box-sizing
  * transform
  * transform-origin
  * transition
  * transition-property
  * transition-duration
  * transition-function
  * transition-delay

値の指定はCSS3の仕様に従います。


### \_yui-base-min.scss

[YUI 3のCSS Base](http://developer.yahoo.com/yui/3/cssbase/)をインポートすることができます。


### \_yui-fonts-min.scss

[YUI 3のCSS Fonts](http://developer.yahoo.com/yui/3/cssfonts/)をインポートすることができます。インポートしたドキュメントでは変数を使ってフォントサイズの変更が行えます。

    h1 {
      font-size: $yui-24px;
    }

`$yui-10px`から`$yui-26px`まで定義されています。


### \_yui-reset-min.scss

[YUI 3のCSS Reset](http://developer.yahoo.com/yui/3/cssreset/)をインポートすることができます。


### \_utils.scss

その他単機能のミックスインをインポートすることができます。

#### fake-aa

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


LICENSE
-------

SCSSファイルにライセンス条項が明記されていない限りすべて[パブリック・ドメイン](http://unlicense.org/)として提供されています。
