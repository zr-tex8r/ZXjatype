ZXjatype Package
================

LaTeX: Standard conforming typesetting of Japanese, for XeLaTeX

This package tries to provide working configuration of the [xeCJK package]
suitable for Japanese typesetting.

[xeCJK package]: https://www.ctan.org/pkg/xecjk

### System requirement

  * TeX format: LaTeX
  * TeX engine: XeTeX (v0.9995 or later)
  * Dependent packages:
      - etoolbox
      - xeCJK

### Installation

  - `*.sty`   → $TEXMF/tex/xelatex/zxjatype/


The zxjatype package
--------------------

### Package loading

    \usepackage[<option>...,<xeCJK option>...]{zxjatype}

The following options are available:

    * `default`: Enables the setting for Japanese document from the
      beginning.
    * `nodefault`: Negation of `default`. The default settings of xeCJK
      will used.

All other options are passed to xeCJK.

### Usage

    * `\zxjapanesestyle`: Applies the setting for Japanese document.

Revision History
----------------

  * Version 0.7  ‹2020/01/22›
  * Version 0.6c ‹2018/05/03›
  * Version 0.6b ‹2017/08/03›
  * Version 0.6a ‹2017/08/02›
  * Version 0.6  ‹2012/09/09›
  * Version 0.5  ‹2012/05/01›
  * Version 0.4  ‹2010/08/15›
  * Version 0.3a ‹2009/11/18›
  * Version 0.3  ‹2009/11/16›
  * Version 0.2a ‹2009/11/01›
  * Version 0.2  ‹2009/10/25›

--------------------
Takayuki YATO (aka. "ZR")  
https://github.com/zr-tex8r
