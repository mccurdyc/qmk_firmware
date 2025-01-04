# Creating a Keymap

```bash
qmk config user.keyboard=dz60
qmk config user.keymap=mccurdyc

qmk config compile.keyboard=default
qmk config compile.keymap=default
# now you can run `qmk compile` with no arguments

# Wrote configuration to '/Users/mccurdyc/Library/Application Support/qmk/qmk.ini'

qmk new-keymap -kb dz60
# Created a new keymap called mccurdyc in: /Users/mccurdyc/qmk_firmware/keyboards/dz60/keymaps/mccurdyc.
# Compile a firmware with your new keymap by typing: qmk compile -kb dz60 -km mccurdyc.
```

# Updating a Keymap

```bash
# make a change to keyboards/dz60/keymaps/mccurdyc; then
qmk compile -kb dz60 -km mccurdyc

# Or, if you've configured defaults
qmk config compile.keyboard=clueboard/66/rev4 compile.keymap=default
```

# Using QMK Configurator

```bash
# JSON to C file
qmk json2c -o keyboards/dz60/keymaps/mccurdyc/keymap.c keyboards/dz60/keymaps/mccurdyc/keymap.json

# C to JSON file
qmk c2json -km mccurdyc -kb dz60 -o keyboards/dz60/keymaps/mccurdyc/keymap.json keyboards/dz60/keymaps/mccurdyc/keymap.c
```

# Quantum Mechanical Keyboard Firmware

[![Current Version](https://img.shields.io/github/tag/qmk/qmk_firmware.svg)](https://github.com/qmk/qmk_firmware/tags)
[![Discord](https://img.shields.io/discord/440868230475677696.svg)](https://discord.gg/qmk)
[![Docs Status](https://img.shields.io/badge/docs-ready-orange.svg)](https://docs.qmk.fm)
[![GitHub contributors](https://img.shields.io/github/contributors/qmk/qmk_firmware.svg)](https://github.com/qmk/qmk_firmware/pulse/monthly)
[![GitHub forks](https://img.shields.io/github/forks/qmk/qmk_firmware.svg?style=social&label=Fork)](https://github.com/qmk/qmk_firmware/)

This is a keyboard firmware based on the [tmk\_keyboard firmware](https://github.com/tmk/tmk_keyboard) with some useful features for Atmel AVR and ARM controllers, and more specifically, the [OLKB product line](https://olkb.com), the [ErgoDox EZ](https://ergodox-ez.com) keyboard, and the Clueboard product line.

## Documentation

```
$ qmk compile -kb dz60 -km mccurdyc
$ sudo qmk flash -kb dz60 -km mccurdyc
```

* [See the official documentation on docs.qmk.fm](https://docs.qmk.fm)

The docs are powered by [VitePress](https://vitepress.dev/). They are also viewable offline; see [Previewing the Documentation](https://docs.qmk.fm/#/contributing?id=previewing-the-documentation) for more details.

You can request changes by making a fork and opening a [pull request](https://github.com/qmk/qmk_firmware/pulls).

## Supported Keyboards

* [Planck](/keyboards/planck/)
* [Preonic](/keyboards/preonic/)
* [ErgoDox EZ](/keyboards/ergodox_ez/)
* [Clueboard](/keyboards/clueboard/)
* [Cluepad](/keyboards/clueboard/17/)
* [Atreus](/keyboards/atreus/)

The project also includes community support for [lots of other keyboards](/keyboards/).

## Maintainers

QMK is developed and maintained by Jack Humbert of OLKB with contributions from the community, and of course, [Hasu](https://github.com/tmk). The OLKB product firmwares are maintained by [Jack Humbert](https://github.com/jackhumbert), the Ergodox EZ by [ZSA Technology Labs](https://github.com/zsa), the Clueboard by [Zach White](https://github.com/skullydazed), and the Atreus by [Phil Hagelberg](https://github.com/technomancy).

## Official Website

[qmk.fm](https://qmk.fm) is the official website of QMK, where you can find links to this page, the documentation, and the keyboards supported by QMK.
