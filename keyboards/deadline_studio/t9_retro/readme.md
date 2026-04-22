# Deadline Studio T9 Retro

TKL-style keyboard from Deadline Studio, using an STM32F401RET6 MCU.

* Keyboard Maintainer: [lexbrugman](https://github.com/lexbrugman)
* Hardware Supported: Deadline Studio T9 Retro (soldered PCB, STM32F401RET6)
* Hardware Availability: Deadline Studio

Make example for this keyboard (after setting up your build environment):

    qmk compile -kb deadline_studio/t9_retro -km default

Flashing example for this keyboard:

    qmk flash -kb deadline_studio/t9_retro -km default

See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

## Bootloader

Enter the bootloader in 3 ways:

* **Bootmagic reset**: Hold down the key at (0,0) in the matrix (usually the top left key or Escape) and plug in the keyboard
* **Physical reset button**: Briefly press the button on the back of the PCB
* **Keycode in layout**: Press the key mapped to `QK_BOOT` (Fn + Esc in the default keymap)

## Pin mapping status

**This port was reconstructed from a VIAL JSON without access to the original firmware or schematic.** The matrix size (6 rows × 18 columns), layout, and MCU are confirmed. The row/column pin assignments in `keyboard.json` are **placeholders** based on common STM32F401RE wiring patterns and have **not** been verified against the real PCB.

Before flashing, trace the PCB with a multimeter (continuity from each switch pad to the MCU pin) and update `matrix_pins.rows` and `matrix_pins.cols` in `keyboard.json` accordingly. Flashing with the placeholder pins will produce a device that enumerates over USB but does not register keypresses; it will not damage the board and remains recoverable via DFU.
