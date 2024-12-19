# uwiegand
A micropython library for using Wiegand RFID / NFC card readers on ESP32 devices.

# Installation

Download the `uwiegand` folder and upload it to your micropython board. You can download this entire repository [here](https://github.com/membermatters/uwiegand/archive/refs/heads/main.zip).

# Examples

Using the default UART config (`machine.UART(1, baudrate=9600, timeout=2, timeout_char=10, tx=19, rx=18)`).

```python
import uwiegand

wiegand_pin_zero = 19
wiegand_pin_one = 18

rfid_reader = uwiegand.Wiegand(
    wiegand_pin_zero,
    wiegand_pin_one,
    uid_32bit_mode=True,
    timer_id=0,
)

# note that this is not blocking and needs to be called as often as possible to check for new card scans
card_id = rfid_reader.read_card()
```

You can also add this repo as a git sub module to your project to make keeping it up to date easier.

```bash
git submodule add https://github.com/membermatters/uwiegand.git
```
