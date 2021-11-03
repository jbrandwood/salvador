salvador -- a fast, near-optimal compressor for the ZX0 format
==============================================================

salvador is a command-line tool and a library that compresses bitstreams in the ZX0 format. 

The tool outputs compressed files that are within 0.02% on average, of the files produced by the zx0 packer itself. The compressor is, however, several orders of magnitude faster, with compression speed similar to [apultra](https://github.com/emmanuel-marty/apultra). 

The compressor can pack files of any size, however, due to the 31.5 KB window size, files larger than 128-256 KB will get a better ratio with apultra. This will not be an issue when compressing for the main target, 8-bit micros. By default, salvador compresses for the modern (V2) format. The classic, legacy format is also supported; use the -classic flag on the command line.

salvador is written in portable C. It is fully open-source under a liberal license. You can use the ZX0 decompression libraries for your target environment. As with LZSA and apultra, you can do whatever you like with it.

The output is fully compatible with the [ZX0](https://github.com/einar-saukas/ZX0) compressor by Einar Saukas.

Decompression code:

 * [z80](https://github.com/einar-saukas/ZX0/tree/main/z80) by Einar Saukas, Urusergi and spke.
 * [8088](https://github.com/emmanuel-marty/unzx0_x86) by Emmanuel Marty. 
 * [68000](https://github.com/emmanuel-marty/unzx0_68000) by Emmanuel Marty. 

License:

* The salvador code is available under the Zlib license.
* The match finder (matchfinder.c) is available under the CC0 license due to using portions of code from Eric Bigger's Wimlib in the suffix array-based matchfinder.
