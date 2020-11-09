# Akaki-Simple-Multiplexer
Simple breakout board to hook up 16 multiplexed button switch inputs to an Arduino Pro Micro's port D (pins 0-7)

With this you can use all 5 of the Arduino Pro Micro's ADC pins for analog input, and the 8 digital pins to read up to 16 digital buttons or switches. Useful for DIY multi-axis input devides. Originally designed as a build aid for a gamepad with 5 analog axes.

To read button inputs, loop through the following:

```
set pins 0 to 3 low

for row = 0 to 3
  set pin[row] high
  for column = 0 to 3
    button[row * 4 + column] = read pin[column]
  set pin[row] low
```

Also compatible with MMJoy2 https://github.com/MMjoy/mmjoy_en/wiki
