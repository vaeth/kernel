# kernel

(C) Martin Väth <martin@mvath.de>
This project is under the BSD license 2.0 (“3-clause BSD license”).

If you want to configure/compile your linux kernel as a user and install it
as root, usually several standard commands should be entered.
I got bored of typing these over and over and thus have written a convenient
script to automate this task.

This POSIX shell script is optimized for usage under Gentoo with portage
(and can use __app-portage/eix-0.32.2__ or newer to speed up):
It uses portage to determine some default paths and settings;
it is currently untested in different environments.

You must have `push.sh` from https://github.com/vaeth/push (v2.0 or newer)
in your `$PATH`.

This script requires that you have set `KBUILD_OUTPUT` so that the
output really can occur as a user. (You should set it also in the root
environment or in make.conf to the same value so that ebuilds will
honour that place).

If you want to transfer X data, you should also have the `sudox` script from
https://github.com/vaeth/sudox (v4.1.0 or better newer) in your `$PATH`.
If you want that the hard status line is set, also the `title` script from
https://github.com/vaeth/runtitle (version 2.3 o newer) is required in
your `$PATH`.

### Installation

For installation, copy the content of `bin/` with executable permission in your
`$PATH` (perhaps to `/usr/bin`). To obtain support for __zsh completion__,
copy the content of `zsh/` to a directory of your zsh's `$fpath`
(perhaps to `/usr/share/zsh/site-functions/`).

There is also an ebuild in the `mv` repository
(available by `app-select/eselect-repository` or `app-portage/layman`).
