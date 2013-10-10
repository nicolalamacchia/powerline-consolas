Consolas for Powerline
======================

This is the patched version of the Consolas font for MS Windows.  This font is
compatible with
[vim-powerline](https://github.com/Lokaltog/vim-powerline)
and
[powerline](https://github.com/Lokaltog/powerline).

I've manually patched the original font since it's practically impossible to
use correctly the Powerline fontpatcher with it.  I think this is due to a
series of reasons (that I won't list here) that aren't directly correlated to
the script itself.

Installation and usage
----------------------

### Install the vanilla Consolas font family

Fist of all you need the Consolas font family to be installed on your system.
If you're running Windows Vista or later, you should find it already installed,
otherwise here's how you can install it manually:

* download Microsoft PowerPoint Viewer for free from the Microsoft Download
  Center;
* extract the downloaded `.exe` installer (`PowerPointViewer.exe`);
* find the file `ppviewer.cab` somewhere inside the extracted folder and
  extract it too;
* install `CONSOLA.ttf`, `CONSOLAB.ttf`, `CONSOLAI.ttf` and `CONSOLAZ.ttf`
  contained within the unpacked `ppviewer.cab`.

**NOTE**: Consolas comes also bundled with the following packages and software:

* Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint File
  Formats;
* Microsoft Visual Studio (2005+, the Consolas font package is available for
  download from the Microsoft Download Center for the older versions);
* Microsof Office (2007+).

### Use the patched font

To use this font, just download the file `consola.ttf` and install it, then
put the following lines in your vimrc file:

    " Setting the font to Consolas, 11 pt
    if has("gui_running")
      if has("gui_gtk2")
        set guifont=Consolas\ 11
      else
        set guifont=Consolas:h11
      endif
    endif
    
If you need fallback fonts, do the following:

    if has('gui_win32')
      " On Vim 7.4.16 the following line still doesn't work with gui_gtk
      set guifont=Consolas:h11:cANSI,Inconsolata:h12,Courier New:h11
    else " not win32
      let consolas=system('fc-list | grep -c Consolas')
      let inconsolata=system('fc-list | grep -c Inconsolata')
      if (consolas > 0)
        set guifont=Consolas\ 11
      elseif (inconsolata > 0)
        set guifont=Inconsolata\ 12
      else
        set guifont=DejaVu\ Sans\ Mono\ 10
        " or simply
        " set guifont=Monospace\ 10
      endif
    endif
    
See `:help guifont` and `:help setting-guifont` in Vim.

Please note that to install this font you'll need to **overwrite** the original
one!  Do your backups, if you want, I'm not responsible for the loss of your
previous version of Consolas!  Anyway, in case you do lose it and want it back,
follow the instructions above to reinstall it.

Why overwrite?
--------------

I made a version of this font with a different family name ("Powerline
Consolas") which was giving me lot of headaches and was killing my free time.
I couldn't end up with working alternative styles ( **bold**, *italic* and 
***bold italic*** ) when re-generating them from the original ttf files.  I 
decided, then, to take advantage of the existing Consolas family.  Perhaps this
solution is less elegant, but at least it works.

Further information and troubleshooting
---------------------------------------

Always refer to the [vim-powerline][VimL] or [powerline][Python]
documentation if something doesn't work as you expected and to understand how
Powerline itself works.

You could also find helpful [this article][CodeJury] by Eugene Ching, which
inspired me.

For more information about the Consolas font family, visit [this
page][Microsoft] (copyright, trademarks and technical details) and [this
page][LucasFonts] (history).

Please, contact me if the font is being naughty with you.

[VimL]: https://github.com/Lokaltog/vim-powerline/blob/develop/doc/Powerline.txt
[Python]: http://lokaltog.github.com/powerline/index.html
[CodeJury]: http://codejury.com/consolas-font-in-vim-powerline-windows/
[Microsoft]: http://www.microsoft.com/typography/fonts/family.aspx?FID=300
[LucasFonts]: http://www.lucasfonts.com/case-studies/calibri-consolas
