![Palnagotchi](https://github.com/sduenasg/pio_palnagotchi/blob/main/palstick.gif?raw=true)
# PIO Palnagotchi for M5 Cardputer and M5Stick C 2 Plus (Find it on M5Burner)

This is the Palnagotchi program with some customizations I made for myself to tinker and learn about m5 development. Credit goes to the original Palnagotchi by **viniciusbo**, repo here: https://github.com/viniciusbo/m5-palnagotchi

Some of the changes on this version include:
- Make it compile on VSCode's Platform IO exension
- Make it run on my M5Cardputer
- Make it run on my M5Stick C Plus 2 (haven't tested other sticks)
- Fixes and library updates
- Change mood more frequently
- New moods
- Complains about their current hardware and not being able to PWN like a Pwnagotchi

Ideas to implement:
- Ability to change palnagotchi's name through the menu
- ...

# Palnagotchi

This unit works as a friend for a Pwnagotchi. Your Pwnagotchis will see palnagotchi as a friend, and palnagotchi will se your pwnagotchis too! Palnagotchi can't PWN though, and he complains about it all the time.

## Environment setup

- Install VScode
- Install platformIO extension
- Pick your environment before compiling (m5stick or cardputer, which is stamps3)
- Compile the code pressing the ✔ icon on the bottom
- Make sure you have access to the device's port. In my case it's ttyACM0
- Upload it by pressing → on the bottom of vscode
- If you need the firmware.bin you just compiled, it is located in the .pio/build folder


### Compiling a combined binary for M5burner (combining fimware.bin, partitions.bin and bootloader.bin)

After building using platform IO, you need esptool to combine the threee .bin that platform.io outputs.

Install esptool if you don't have it.
```shell
pip install esptool
```

Through terminal, go into the builds folder for the platform you chose, where firmware.bin, bootloader.bin and partitions.bin are.

``` shell
esptool.py --chip esp32 merge_bin -o combined_firmware.bin --flash_mode dio --flash_freq 80m --flash_size 8MB 0x1000 ./bootloader.bin 0x8000 ./partitions.bin 0x10000 ./firmware.bin
```

To test burning with esptool:

``` shell
   esptool.py --chip esp32 --port /dev/ttyACM0 --baud 1500000 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0x0 combined_firmware.bin
```
## Usage
- Run the app to start advertisement.
- On M5Cardputer: ESC or m toggles the menu. Use arrow keys or tab to navigate and OK to select option. Esc or m to go back to main menu.
- Top bar shows UPS level and uptime.
- Bottom bar shows total friends made in this run, all time total friends between parenthesis (needs EEPROM) and signal strengh indicator of closest friend.
- Nearby pwnagotchis show all nearby units and its signal strength.
- Palnagotchi randomly changes mood.

![Palnagotchi](https://github.com/sduenasg/pio_palnagotchi/blob/main/pwns2.jpg?raw=true)