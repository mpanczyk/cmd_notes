# `cmd_notes`
My notes about GNU/Linux CLI,
especially automating things that most people think are not automatable.

  * Running `xterm` with standard (80x24) term size
    (important when recording term)
    and favorite Terminus font.

    ```shell
    xterm -fn "-*-terminus-*-*-*-*-*-180-*-*-*-*-*-*" -geometry 80x24
    ```

## X11 stuff
There is also some hints about X11 environment making more ergonomic:

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
