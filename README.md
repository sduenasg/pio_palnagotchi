![Palnagotchi](https://github.com/sduenasg/pio_palnagotchi/blob/main/pwns2.jpg?raw=true)

# PIO Palnagotchi for M5 Cardputer and M5Stick C 2 Plus

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

## Usage

- Run the app to start advertisement.
- On M5Cardputer: ESC or m toggles the menu. Use arrow keys or tab to navigate and OK to select option. Esc or m to go back to main menu.
- Top bar shows UPS level and uptime.
- Bottom bar shows total friends made in this run, all time total friends between parenthesis (needs EEPROM) and signal strengh indicator of closest friend.
- Nearby pwnagotchis show all nearby units and its signal strength.
- Palnagotchi randomly changes mood.

