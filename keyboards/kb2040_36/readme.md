# kb2040_36

![kb2040_36](imgur.com image replace me!)

_A short description of the keyboard/project_

-   Keyboard Maintainer: [Scott Buetow](https://github.com/spoxxter2)
-   Hardware Supported: _The PCBs, controllers supported_
-   Hardware Availability: _Links to where you can find this hardware_

Make example for this keyboard (after setting up your build environment):

    make kb2040_36:default

Flashing example for this keyboard:

    make kb2040_36:default:flash

See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

## Bootloader

Enter the bootloader:

-   **Physical reset button**: Hold the Boot button, while holding, press the reset button until the uf2 folder appears

## data driven config

`info.json` is where most of the data lives. It will generate the appropriate lower level files, but `rules.mk` and `config.h` can still be used when required.

### The matrix config

This was super confusing at first. For split keyboards, two matrices are specified. The "normal" (left) one under "matrix_pins" and the second one which must be nested under "split" -> "matrix_pins" -> "right". But how do you reference the left vs right matrix in the layout portion? This was the most confusing part which does not seem to be documented anywhere:

** The rows of the right side are under the left side **

So, if I have a split keyboard with 4x5 on each half (and each with its own 4x5 matrix defined as per above), the layout must be indexed as though it is an 8x5 (8 rows and 5 columns). I couldn't find where this was documented and only figured it out by looking at several other split combinations.

[This](https://docs.qmk.fm/#/feature_split_keyboard?id=layout-macro) is the closest I could get to documentation but it still isn't super clear in regards to the json file.
