# How To

Additional notes.

## Configuration

```
get_idf
idf.py set-target esp32s3
```

## Building

## Debugging

Taken from [Espressif docs](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-guides/jtag-debugging/using-debugger.html#jtag-debugging-using-debugger-command-line).

On the ESP32-S3-DevKitC-1 v1.0, connect to the port labeled `USB` on the board.

Open a terminal window and launch a console monitor:

```
idf.py monitor
```

Open another terminal and launch OpenOCD:

```
get_idf
openocd -f board/esp32s3-builtin.cfg
```

"Getting" (exporting) the IDF will:

* add the correct version of `openocd` to `PATH`
* set the environment variable [OPENOCD\_SCRIPTS](https://openocd.org/doc/html/Running.html)

For example:

* `PATH` will contain `$HOME/.espressif/tools/openocd-esp32/v0.11.0-esp32-20211220/openocd-esp32/bin/`
* `OPENOCD_SCRIPTS` is set to `~/.espressif/tools/openocd-esp32/v0.11.0-esp32-20211220/openocd-esp32/share/openocd/scripts/`

Open a new terminal window and launch gdb:

```
get_idf
xtensa-esp32-elf-gdb -x gdbinit build/hello_world.elf
```

"Getting" (exporting) the IDF will:

* add the correct implementation of `gdb` to `PATH`

## TODO 

* Learn to use `idf.py gdb`.
