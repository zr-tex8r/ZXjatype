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

基本的な機能の説明については以下の Web ページでも行っているのでそちらも
参照してほしい。

  * [ZXjatype パッケージ]
    (http://zrbabbler.sp.land.to/zxjatype.html)

### パッケージ読込

xeCJK と一緒に読み込む場合：

    \usepackage[<オプション>...,<xeCJKのオプション>...]{zxjatype}

xeCJK と別個に読み込む場合：

    \usepackage[<xeCJKのオプション>...]{xeCJK}
    \usepackage[<オプション>...]{zxjatype}

有効なオプションは以下の通り：

  * `default`：（既定）パッケージ読込直後に日本語用の設定への切替を行う。      （`\zxjapanesestyle` を実行する。）
  * `nodefault`： `default` の否定。 xeCJK の初期設定が保持される。
  * `CJKchecksingle`：（既定）xeCJK の文字ウィドウ抑制機能を有効にする。
    （`CheckSingle=true` を設定する。）
  * `noCJKchecksingle`： `CJKchecksingle` の否定。xeCJK の初期設定の通り
    で文字ウィドウ抑制機能が無効になる。
  * `adjustcharclass`：（既定）日本語の組版規則に合わせて xeCJK の文字
    クラス設定を変更する。
  * `noadjustcharclass`： `adjustcharclass` の否定。 xeCJK の文字クラス
    設定を変更しない。
  * `kanakinsoku`： 小書き仮名を行頭禁則の対象にする。具体的には、これら
    の文字の文字クラスを「閉じ括弧類」に変更する。  
    ※この扱いには副作用があって、直後に約物がある場合の空きが不正になる
    （約物が並んでいると解釈されるため）。 
  * `nokanakinsoku`：（既定）小書き仮名を行頭禁則の対象にしない。具体的
    にはこれらの文字の文字クラスを「通常 CJK 文字」に変更する。  
    ※`kanakinsoku`・`nokanakinsoku` の何れの場合も xeCJK の設定に変更を
    加えることに注意。変更したくない場合は `noadjustcharclass` にする。
  * `useinhibitglue`： pTeX と互換の `\inhibitglue` 命令を定義する。  
    ※ただし現状の実装は不完全で問題があることが判っている。
  * `nouseinhibitglue`：（既定） `useinhibitglue` の否定。`\inhibitglue`
    は定義されない。
  * `prefercjk`： 一部の記号類の文字クラスを「非 CJK 文字」（欧文扱い）
    から「通常 CJK 文字」（和文扱い）に変更する。  
    ※和文扱いの範囲が LuaTeX-ja の初期状態とほぼ同じになる。
  * `noprefercjk`：（既定）`prefercjk` の否定。

### 機能

xeCJK の CJK フォントファミリ設定において、`\setjafontscale` で設定された
和文スケール値が `Scale` の値として設定される。以下の命令が対象となる。

  - `\setCJKmainfont`
  - `\setCJKsansfont`
  - `\setCJKmonofont`
  - `\setCJKfamilyfont`

zxjatype の独自の命令。

  * `\setjafontscale{<実数>}`： 和文スケール値を設定する。  
    ※空の引数も可能で、この場合は和文スケール値設定が抑止される。
  * `\>`： 明示的に和欧文間空白を出力する。  
    ※数式モード中では LaTeX カーネルの定義が維持される。  
    ※他のパッケージで再定義が行われている場合は定義されない。
  * `\inhibitglue`： その箇所で和文文字間に自動的に入る空白を抑制する。  
    ※`useinhibitglue` オプション指定時にのみ定義される。
  * `\<`： `\inhibitglue` と同義。  
    ※他のパッケージで再定義が行われている場合は定義されない。
  * `\textrawen{<テキスト>}`： 和文処理を無効化し、引数のテキストを欧文
    フォントで出力する。
  * `rawentext` 環境： `\textrawen` の環境版。
  * `\textrawja{<テキスト>}`： 和文処理を無効化し、引数のテキストを和文
    フォントで出力する。
  * `rawjatext` 環境： `\textrawja` の環境版。
  * `\zxjapanesestyle`： 日本語用の設定に切り替える。  
    ※この命令はユーザによる再定義が可能。
  * `\zxusejapaneseparameter`： 和欧文間空白と和文間空白を日本語組版に
    適した値にする。
  * `\zxuseoriginalparameter`： 和欧文間空白と和文間空白を xeCJK の初期
    設定に戻す。

なお、`\zxjapanesestyle` の初期値は以下のとおりである：

    \xeCJKsetup{
      AllowBreakBetweenPuncts = true,
      PunctStyle = fullwidth,
    }%
    \zxusejapaneseparameters

### 旧版との互換のための命令

  * `\setjamainfont`： xeCJK の `\setCJKmainfont` と同義。
  * `\setjasansfont`： xeCJK の `\setCJKsansfont` と同義。
  * `\setjamonofont`： xeCJK の `\setCJKmonofont` と同義。
  * `\setjafamilyfont`： xeCJK の `\setCJKfamilyfont` と同義。
  * `\jafamily`： xeCJK の `\CJKfamily` と同義。

### 参考：0.6 版で廃止された機能

  * `\(no)jafamilyinverbatim` 命令


更新履歴
--------

  * Version 0.7  ‹2020/01/22›
      - xeCJK 2.x 版の使用を非推奨（将来廃止予定）とする。
      - `(no)prefercjk` オプションを新設。
      - 和文スケール値を `\zxjatypeJaScale` に格納する。
      - バグ修正。

  * Version 0.6c ‹2018/05/03›
      - バグ修正。

  * Version 0.6b ‹2017/08/03›
      - `(no)useinhibitglue` オプション。
      - `(no)kanakinsoku` オプション。

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
