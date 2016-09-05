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

  * Batch resizing all pictures in a directory with
    additional sharpening, annotating of the date a picture was taken
    (info from EXIF).
    Original pictures are untouched, the results are stored (here) in a subdirectory `small`.

    One liner:
    ```shell
    for F in *jpg; do convert $F -resize 1000x1000 -sharpen 1.2 -gravity South -background YellowGreen -splice 0x18 -annotate +0+2 "$(identify -verbose $F | grep exif | grep Original | tr -s ' ' | cut -d ' ' -f3 | tr ':' ' ' | awk '{print $3 "." $2 "." $1}')" small/$F; done
    ```

    Split lines:
    ```shell
    for F in *jpg
      do
        convert\
          $F\
          -resize 1000x1000\
          -sharpen 1.2\
          -gravity South\
          -background YellowGreen\
          -splice 0x18\
          -annotate +0+2\
          "$(\
            identify -verbose $F\
            | grep exif\
            | grep Original\
            | tr -s ' '\
            | cut -d ' ' -f3\
            | tr ':' ' '\
            | awk '{print $3 "." $2 "." $1}'\
          )"\
          small/$F
      done
    ```

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
