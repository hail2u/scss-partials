SCSS Partials
=============

SCCSファイルにインポートして使用する端切れ(partial)を放り込むリポジトリです。


USAGE
-----

`@import`を使ってSCSSファイルでインポートします。

    @import "reset";
    @import "clearfix";

拡張子とファイル名の先頭の`_`は不要です。


### \_speech-bubble.scss

吹き出しのデザインを変更することができます。

    .speech-bubble {
      @include speech-bubble(#9cf, 6px, 12px, $24px);
    }

#### 引数

  1. `$bgcolor`: 背景及び吹き出しの尻尾の色
  2. `$round-size`: 吹き出しの四隅の丸さ
  3. `$tail-size`: 吹き出しのサイズ
  4. `$tail-position`: 吹き出しの位置


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


### \_yui-fonts-min.scss

インポートしたドキュメントで変数を使ってフォントサイズの変更が行えます。

    h1 {
      font-size: $yui-24px;
    }

`$yui-10px`から`$yui-26px`まで定義されています。


LICENSE
-------

SCSSファイルにライセンス条項が明記されていない限りすべて[パブリック・ドメイン](http://unlicense.org/)として提供されています。
