# `cmd_notes`
My notes about GNU/Linux CLI,
especially automating things that most people think are not automatable.

  * Running `xterm` with standard (80x24) term size
    (important when recording term)
    and favorite Terminus font.

    ```shell
    xterm -fn "-*-terminus-*-*-*-*-*-180-*-*-*-*-*-*" -geometry 80x24
    ```

  * Composing multiple PDF docs into one

    ```shell
    pdftk A=bigpdf.pdf B=insert.pdf cat A1-180 B A181-end output output.pdf
    ```

    Also `PDFsam` is useful for splitting and merging.

## X11 stuff
There are also some hints about making X11 environment more ergonomic:

  * [console fonts](./fonts.md)
  * controlling screen:
      - turn off/on:
      ```
      xset dpms force off/on
      ```
      - query the state of the screen:
      ```
      xset -q
      ```
