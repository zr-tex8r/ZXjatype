ZXjatype バンドル
=================

LaTeX: XeLaTeX と xeCJK パッケージを利用した日本語組版の支援

本パッケージは、日本語組版に適した [xeCJK パッケージ]の設定を提供する。

[xeCJK パッケージ]: https://www.ctan.org/pkg/xecjk

### 前提環境

  * フォーマット： LaTeX
  * エンジン： XeTeX（0.9995 版以降）
  * 前提パッケージ：
      - etoolbox
      - xeCJK

### インストール

  - `*.sty`   → $TEXMF/tex/xelatex/zxjatype/


zxjatype パッケージ ― 本体
---------------------------

まだ解説が書けておりません…。基本的な機能の説明については以下の Web
ページで行っていますのでそちらを参照してください。

  * [ZXjatype パッケージ]
    (http://zrbabbler.sp.land.to/zxjatype.html)


更新履歴
--------

  * Version 0.6b ‹2017/08/03›
      - (試験的) `(no)useinhibitglue` オプション。
      - (試験的) `(no)kanakinsoku` オプション。

  * Version 0.6a ‹2017/08/02›
      - バグ修正。

  * Version 0.6  ‹2012/09/09›
      - xeCJK 3.x 版に対応させる。xeCJK 3.x 版用に新たに実装されたコードは
        2.x 版と併用できないので、zxjatype 0.5 版のコードをそのまま残して
        xeCJK が 2.x 版の場合はそちらを有効にする。
      - 実装上の制限により、日本語用に特別に調整した句読点スタイル quasijis
        の実装を止めた。日本語には、xeCJK で用意された句読点スタイルの
        fullwidth を使用する。
      - `\setCJK...font` 命令でも `\setjafontscale` の設定が効くようにする、
        すなわち `\setja...font` 命令の動作と同じにする。
      - `\setjafontscale{}` (空引数)で和文スケール設定を付加しない設定に切り
        替えられるようにした。
      - `\[no]usejafamilyinverbatim` 命令を廃止した。

  * Version 0.5  ‹2012/05/01›
      - 「行頭禁則の仮名」+「開き括弧」の間の空きが入らない現象を修正。
      - xeCJK の「大きな」内部マクロに対してパッチを当てる処理を etoolbox
        の `\patchcmd` で行うように変更。

  * Version 0.4  ‹2010/08/15›
      - xeCJK 2.3.10 版/2.3.15 版での動作を確認。
      - 一部の命令の名前を変更。基本的にこのパッケージで提供される命令の名前は
        \CJK.. や \xeCJK.. で始まらないようにした。(ただしその結果として、命令
        の出自によって「接頭辞」がまちまちになってしまっている。)

  * Version 0.3a ‹2009/11/18›

  * Version 0.3  ‹2009/11/16›
      - `\[no]jafamilyinverbatim` 追加。
      - `\textrawja`/`\textrawen` 追加。
      - `rawjatext`/`rawentext` 追加。
      - bxbase の `\Ux`/`\UI` のドライバを追加。

  * Version 0.2a ‹2009/11/01›
      - リリース作業のミスで生じたバグを修正。

  * Version 0.2  ‹2009/10/25›
      - 最初の公開版。

--------------------
Takayuki YATO (aka. "ZR")  
https://github.com/zr-tex8r
