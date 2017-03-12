KMAC keyboard firmware
======================
Korean custom keyboard designed by Byungho Kim and KBDMania community.

**Note that this is not the official firmware**

Supported models
----------------
At the moment only the TKL models are supported.

Build
-----
[tmk_core](https://github.com/tmk/tmk_core) is included as a submodule. To be
able to build it must first initialized and updated:

    $ git submodule update --init

Then simply run `make` like:

    $ make

Keymap
------
There are 2 different types of PCB, winkey and winkeyless. A default keymap file
are included for each of these.

To define your own keymap create a file named `keymap_<name>.c`. See [keymap
documentation](https://github.com/tmk/tmk_core/blob/master/doc/keymap.md) in the
[tmk_core repository](https://github.com/tmk/tmk_core) and existent keymap files
for instructions.

To build a firmware binary hex file with a certain keymap run make with `KEYMAP`
option like:

    $ make KEYMAP=[winkey|winkeyless|<name>]

### 1. Winkey
This is the default keymap.

See [keymap_winkey.c](keymap_winkey.c) for details.

#### 1.0. Winkey Default Layer
     ,---.   ,---------------. ,---------------. ,---------------. ,-----------.
     |Esc|   |F1 |F2 |F3 |F4 | |F5 |F6 |F7 |F8 | |F9 |F10|F11|F12| |PrS|ScL|Pau|
     `---'   `---------------' `---------------' `---------------' `-----------'
     ,-----------------------------------------------------------. ,-----------.
     |~  |  1|  2|  3|  4|  5|  6|  7|  8|  9|  0|  -|  =|Backsp | |Ins|Hom|PgU|
     |-----------------------------------------------------------| |-----------|
     |Tab  |  Q|  W|  E|  R|  T|  Y|  U|  I|  O|  P|  [|  ]|    \| |Del|End|PgD|
     |-----------------------------------------------------------| '-----------'
     |Fn0   |  A|  S|  D|  F|  G|  H|  J|  K|  L|  ;|  '|Return  |
     |-----------------------------------------------------------|     ,---.
     |Shift   |  Z|  X|  C|  V|  B|  N|  M|  ,|  .|  /|Shift     |     |Up |
     |-----------------------------------------------------------| ,-----------.
     |Ctl|Gui|Alt|             Space             |Alt|Gui|App|Ctl| |Lef|Dow|Rig|
     `-----------------------------------------------------------' `-----------'

#### 1.1. Winkey Media Layer
     ,---.   ,---------------. ,---------------. ,---------------. ,-----------.
     |Led|   |   |   |   |   | |   |   |   |   | |   |   |   |   | |   |   |Slp|
     `---'   `---------------' `---------------' `---------------' `-----------'
     ,-----------------------------------------------------------. ,-----------.
     |   |   |   |   |   |   |   |   |   |   |Mut|V- |V+ |       | |   |   |   |
     |-----------------------------------------------------------| |-----------|
     |     |   |   |   |   |   |   |   |   |Stp|Ply|Prv|Nxt|Media| |   |   |   |
     |-----------------------------------------------------------| '-----------'
     |      |   |   |   |   |   |   |   |   |   |   |   |        |
     |-----------------------------------------------------------|     ,---.
     |        |   |   |Clc|   |   |   |   |   |   |   |Caps      |     |   |
     |-----------------------------------------------------------| ,-----------.
     |   |   |   |                               |   |   |   |   | |   |   |   |
     `-----------------------------------------------------------' `-----------'


### 2. Winkeyless
Layout with 1.5 unit modifiers.

See [keymap_winkeyless.c](keymap_winkeyless.c) for details.

#### 2.0. Winkeyless Default Layer
     ,---.   ,---------------. ,---------------. ,---------------. ,-----------.
     |Esc|   |F1 |F2 |F3 |F4 | |F5 |F6 |F7 |F8 | |F9 |F10|F11|F12| |PrS|ScL|Pau|
     `---'   `---------------' `---------------' `---------------' `-----------'
     ,-----------------------------------------------------------. ,-----------.
     |~  |  1|  2|  3|  4|  5|  6|  7|  8|  9|  0|  -|  =|Backsp | |Ins|Hom|PgU|
     |-----------------------------------------------------------| |-----------|
     |Tab  |  Q|  W|  E|  R|  T|  Y|  U|  I|  O|  P|  [|  ]|    \| |Del|End|PgD|
     |-----------------------------------------------------------| '-----------'
     |Fn0   |  A|  S|  D|  F|  G|  H|  J|  K|  L|  ;|  '|Return  |
     |-----------------------------------------------------------|     ,---.
     |Shift   |  Z|  X|  C|  V|  B|  N|  M|  ,|  .|  /|Shift     |     |Up |
     |-----------------------------------------------------------| ,-----------.
     |Ctl |Gui|Alt |             Space             |Alt |Gui|Ctl | |Lef|Dow|Rig|
     `-----------------------------------------------------------' `-----------'

#### 2.1. Winkeyless Media Layer
     ,---.   ,---------------. ,---------------. ,---------------. ,-----------.
     |Led|   |   |   |   |   | |   |   |   |   | |   |   |   |   | |   |   |Slp|
     `---'   `---------------' `---------------' `---------------' `-----------'
     ,-----------------------------------------------------------. ,-----------.
     |   |   |   |   |   |   |   |   |   |   |Mut|V- |V+ |       | |   |   |   |
     |-----------------------------------------------------------| |-----------|
     |     |   |   |   |   |   |   |   |   |Stp|Ply|Prv|Nxt|Media| |   |   |   |
     |-----------------------------------------------------------| '-----------'
     |      |   |   |   |   |   |   |   |   |   |   |   |        |
     |-----------------------------------------------------------|     ,---.
     |        |   |   |Clc|   |   |   |   |   |   |   |Caps      |     |   |
     |-----------------------------------------------------------| ,-----------.
     |    |   |    |                               |    |   |    | |   |   |   |
     `-----------------------------------------------------------' `-----------'

Bootloader
---------
The PCB is hardwired to run the bootloader if the key at the `Caps Lock`
position is held down when connecting the keyboard.

It is still possible to use Boot Magic and Command to access the bootloader
though.
