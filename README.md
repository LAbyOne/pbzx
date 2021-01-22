# pbzx stream parser

This repository is a fork of PHPdev32's implementation of the `pbzx` stream
parser program of which the original source code can be found [here][source].
Pbzx is a format employed in later versions of OSX disk images (starting with
10.10) to encode payload data in `.pkg` files. Pbzx unpacks `.pkg` files and
outputs to stdout to be unpacked with `cpio`. Note that `.pkg` files are plain
`.xar` archives.

    pbzx SomePkg.pkg | cpio -i  # or
    pbzx -n Payload  | cpio -i

To compile `pbzx`, do

    clang -llzma -lxar -I /usr/local/include pbzx.c -o pbzx

> If `<lzma.h>` or `<xar/xar.h>` are missing, install them with [Homebrew]
> using
>
>     brew install xz && brew link xz

  [source]: http://www.tonymacx86.com/general-help/135458-pbzx-stream-parser.html
  [Homebrew]: http://brew.sh/

## License

Copyright (C) 2017  Niklas Rosenstein
#
Copyright (C) 2014  PHPdev32

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
