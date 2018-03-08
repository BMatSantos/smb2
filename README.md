# Super Mario Bros. 2, The Disassembly
A disassembly of Super Mario Bros. 2, in progress.

This is built for use with ASM6 (https://github.com/freem/asm6f/).
For your convinience, a binary of that is included.

## Building
To build, run

    build

This will generate a few files:

* `smb2.nes`, your ROM
* `comparison.txt`, a byte comparison against the original ROM
* `smb2.lst`, the assembler listing
* `assembler.txt` and `assembler-err.txt`, logs from the assembler
* a bunch of assorted other files

By default, the build script will build a byte-for-byte copy of the game.
You can change this behavior by removing the `-d_COMPATIBILITY_` flag from `build.bat`.

## Assembly
The "source" lives in the `asm` directory:

* `prg-x.asm` are the program banks.
* `defs.asm` are some definitions.
* `ram.asm` are definitions and labels for RAM addresses.

The `tools/Super Mario Bros. 2 (USA) 2.asm` file is an auto-generated disassembly
from a certain disassembly tool. If you modify it (for some reason),
you can use `php tools/asm.php` to re-split the disassembly and clean it up.
Note that doing so will *lose all changes* in the split disassembly!

If you want to build the *Rev A* version of the game that fixes a soft-lock bug
involving the Fryguy boss, you should check out the `rev-a` branch.

## Whoops
If you goof up and something breaks, `tools/offsetcompare.php` may help;
it uses labels like `unk_byte_ABCD` to check if the code has gotten
shifted or offset in some way (so you can go fix it).
