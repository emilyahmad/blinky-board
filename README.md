# snoopy-board

This snoopy inspired 555 LED chaser board contains 2 IC's: CD4017 to control LED's flashing and get input from NE555P, 2 header pins to power the circuit, standard capacitors and resistors, and of course LEDs. Made with help from @Tanishq Goyal qnd @CAN's guides on stasis.

```
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡜⠀⠑⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠇⠑⢄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⡾⠀⠀⠀⠈⢂⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡌⠀⠀⠀⠑⢆⡀⠀⠀⠀⠀⠀⠀⠀⠀⠺⠄⣀⠀⠀⠀⠀⠑⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡘⠀⠀⠀⠀⣀⠜⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠑⠀⠤⣀⠈⢆⠀⠀⠀⠀⠀⠀⠀⢀⡸⠄⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⠃⠀⢀⠤⠊⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠁⠀⠑⠄⠀⠀⠀⠀⣀⡞⠁⠀⠀⢀⡀⠀⠀⠀⠀
⠀⠀⠀⠀⣤⠄⠀⠀⠀⠀⠀⢀⠋⡠⠔⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣤⠶⠒⠛⠉⠉⠈⢂⠀⠀⠀⠛⠀⣀⣤⠾⠛⠁⠀⠀⠀⠀
⠀⠀⠀⠀⠈⠳⣤⡀⠀⠀⠀⡎⠉⣀⣀⣀⣠⣄⣀⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣶⣿⣿⠶⠶⠶⠶⠶⠶⢤⣀⠱⠀⠀⠀⠀⠉⠈⠀⠀⠀⠀⠀⠀⠀
⠀⠺⢦⣄⡠⠀⠉⠁⠀⠀⠸⠐⠋⠁⠀⢀⣀⣤⣽⣿⠿⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠉⠛⠷⣦⣄⡀⠀⠀⠁⠀⠱⡀⠀⠀⠐⠓⠚⠛⠛⠀⠀⠀⠀
⠀⠀⠀⠀⠉⠛⠀⠀⠀⢀⠇⣠⠴⠶⠛⠉⣡⡾⠟⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠀⠈⠙⠷⢦⡀⠀⠀⢠⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠠⡤⠤⠤⠼⠀⠀⠀⠀⢸⠀⠀⠀⢀⣤⡾⠋⠀⠀⠀⠀⠀⣀⣀⣤⣤⣶⡶⠶⠶⠿⢿⣷⠀⡐⠁⠀⠀⠀⠀⠀⠈⠒⠤⡀⠆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⠀⢀⣴⠿⠩⠤⠄⣀⠀⠀⠀⣿⡟⠋⠉⠀⠀⠀⠀⠀⠀⠀⣿⠀⢇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢾⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠄⠀⡸⠁⠀⠀⠀⠀⠀⠙⢄⠀⢻⣇⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⠀⠈⠢⠄⣀⠀⠀⠀⠀⠀⢀⡠⠜⢣⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠂⠰⠁⠀⠀⠀⠀⠀⠀⠀⢸⠄⠘⣿⡄⠀⠀⠀⠀⠀⠀⠀⠀⣿⠀⠀⠀⠀⠀⠈⠁⠀⠈⠉⠁⠀⠀⠀⠆⠀⠀⠀⢀⠀⠀⠄⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠁⢇⠀⠀⠀⠀⠀⢀⡠⠔⠁⠀⠀⠹⣿⣄⠀⠀⠀⠀⠀⠀⢰⡿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡰⠀⡠⠐⠁⠀⠀⠀⡆
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠓⠂⠒⠊⠉⠀⠀⠀⠀⠀⠀⠀⠘⢿⣧⣄⠀⠀⠀⢀⣾⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⠇⠊⠀⠀⠀⢀⠄⠊⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠛⠷⣦⣤⡾⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⡴⠚⠁⠀⠀⠀⡠⠂⠁⠀⠀⠀
⠀⠀⠀⠂⠤⠀⣀⠀⠀⢳⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠈⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⠴⠊⠁⠀⠀⠀⡠⠔⠁⠀⠀⠀⠀⠀⠀
⡀⠀⠀⠀⠀⠀⠀⠈⠑⠂⠙⠢⠤⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠇⢀⡠⠔⠋⠀⠀⠀⠀⡠⠐⠉⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠈⠀⠐⠂⠤⢀⡀⠀⠀⠀⠀⠀⠀⠀⠉⠉⠀⠐⠒⠂⠀⠤⢤⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠞⠁⠀⠀⠀⣀⠄⠂⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠉⠀⠒⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⠠⠒⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢨⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠐⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
```



sdafasdfasdf

### Blinky Board

## trying to brainstorm shapes while hackatime works

on recognizing this as a hackatime project LOL
either:

- graduation present for my sister
- some kind of gift
- maybe for clark?
- maybe I can do better if it's for clark

something that lights up
maybe shows secret messages?

or has like a disco
or maybe adjusts to the colors arounds it/camoflage
or does like a color theory thing based on surrounding

or maybe adjusts frequency and color based on input
honestly that would be really cool
maybe like a mood ring

or like based on your heart rate

i kind of like the heart rate thing
but i might just make it a graduation present
bc i feel like the secret messages will be too hard
unless i do morse code
omg i should do I love you in morse code
and give it to my sister
and make it a graduation cap

or mayb
