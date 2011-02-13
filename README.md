SCSS Partials
=============

SCCSファイルにインポートして使用する端切れ(partial)を放り込むリポジトリです。


USAGE
-----

`@import`を使ってSCSSファイルでインポートします。

    @import "reset";
    @import "clearfix";

拡張子とファイル名の先頭の`_`は不要です。


### \_yui-fonts-min.scss

インポートしたドキュメントで変数を使ってフォントサイズの変更が行えます。

    h1 {
      font-size: $yui-24px;
    }

`$yui-10px`から`$yui-26px`まで定義されています。


LICENSE
-------

SCSSファイルにライセンス条項が明記されていない限りすべて[パブリック・ドメイン](http://unlicense.org/)として提供されています。
