Consolas for Powerline
======================

powerline-consolas is the patched version of the Consolas font for MS Windows.
This font is compatible with
[vim-powerline](https://github.com/Lokaltog/vim-powerline)
and
[powerline](https://github.com/Lokaltog/powerline).

I've manually patched the original font since it's practically impossible to
use correctly the Powerline fontpatcher with it.

Usage
-----

To use this font, just install it and add the following line to your vimrc file:

    set guifont=Powerline_Consolas:h11

where `h11` is the desired font size.

Further information and troubleshooting
---------------------------------------

Always refer to the [vim-powerline][VimPowDoc] or [powerline][PowDoc]
documentation if something doesn't work as you expected and to understand how
Powerline itself works.

You can also find helpful in [this article][CodeJury] by Eugene Ching, which
inspired me.

[VimPowDoc]: https://github.com/Lokaltog/vim-powerline
[PowDoc]: http://lokaltog.github.com/powerline/index.html
[CodeJury]: http://codejury.com/consolas-font-in-vim-powerline-windows/
