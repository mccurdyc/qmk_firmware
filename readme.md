# Cloning the repo

```bash
git clone --recurse-submodules git@github.com:mccurdyc/qmk_firmware.git
```

# Updating a Keymap

Look at my keymap - https://github.com/mccurdyc/qmk_firmware/tree/master/keyboards/1upkeyboards/1up60hse/keymaps/mccurdyc

> [!CAUTION]
> 1. Do NOT store the JSON file in the keymap directory, `qmk compile` will fail
> 2. Do NOT overwrite keyboard.json file

1. Use the QMK Configurator - https://config.qmk.fm/#/1upkeyboards/1up60hse/LAYOUT_60_ansi
2. Use the "Upload from URL" button on QMK Configurator

    ```txt
    https://raw.githubusercontent.com/mccurdyc/qmk_firmware/refs/heads/master/keyboards/1upkeyboards/1up60hse/mccurdyc.json
    ```

3. Make Edits
4. Download the new JSON file to the same place

    ```bash
    cp ~/Downloads/1upkeyboards_1up60hse_1upkeyboards_1up60hse_mccurdyc.json keyboards/1upkeyboards/1up60hse/mccurdyc.json
    ```

5. JSON to C

    ```bash
    qmk json2c -o keyboards/1upkeyboards/1up60hse/keymaps/mccurdyc/keymap.c keyboards/1upkeyboards/1up60hse/mccurdyc.json
    ```

6. Compile C

    ```bash
    qmk compile -kb 1upkeyboards/1up60hse -km mccurdyc
    ```

7. Put the keyboard in Bootloader mode
    - For this keyboard, hold "reset" on the bottom of the keyboard until the keyboard no longer types
8. Flash

    ```bash
    qmk flash -km mccurdyc -kb 1upkeyboards/1up60hse
    ```
9. Confirm typing works. If it doesn't, you are probably flashing the wrong keyboard

# Creating a Keymap

```bash
qmk config user.keyboard=1upkeyboards/1up60hse
qmk config user.keymap=mccurdyc

qmk config compile.keyboard=default
qmk config compile.keymap=default
# now you can run `qmk compile` with no arguments

# Wrote configuration to '/Users/mccurdyc/Library/Application Support/qmk/qmk.ini'

qmk new-keymap -kb 1upkeyboards/1up60hse
# Created a new keymap called mccurdyc in: /Users/mccurdyc/qmk_firmware/keyboards/1upkeyboards/1up60hse/keymaps/mccurdyc.
```
