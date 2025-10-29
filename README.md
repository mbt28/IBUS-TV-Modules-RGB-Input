
# RGB Input Hack BMW IBUS Equipped Cars

IBUS BMW Video modules have RGB analog inputs via the so called jungle chip(TDA8376). RGB inputs are only visible when the TV is activated. Composite input of Rearview Camera or TV Tuner is used as Composite Sync signal. On motherboard blinded pin headers; only RGBIN2 input is available for external input, RGBIN1 is dedicated to OSD MCU and only available on "vias". According to TDA8376 datasheet: The RGB1 inputs have priority over the RGB2 inputs. Due to that it is not possible to make OSD overlay on RGBIN2. Only way to show OSD is disabling RGBIN2 insertation.

Also it is possible to use onboard monitor without video or Navi module, On board monitor uses Sync on Green so simply tapping the sync generated from composite sync(0.3VPP logic level) to green will work.


## Documentation

[TDA8376 Jungle Chip Datasheet](https://github.com/mbt28/IBUS-TV-Modules-RGB-Input/blob/main/docs/TDA8376.PDF)


## Roadmap

- Blocking rotary input for OSD screen in TV mode. I couldnt find a way to block rotary inputs to OSD Menu. I sniffed I2C lines but there is no message indicates the rotary input or OSD activity. If anyone know how to do it please let me know.

- Document TV RF Tuner module I2C communication.
- Make stereo audio possible for TV input.


## I2C Address List

``` 
I2C Address Scan: I2C address search: 0x38 (0x70 W) (0x71 R) // PCF8574AP (Estimation) 
0x39 (0x72 W) (0x73 R) // PCF8574AP (Estimation) 
0x45 (0x8A W) (0x8B R) // TDA8376 Jungle Chip 
0x4C (0x98 W) // TEA6420 Audio Muxer 
0x50 (0xA0 W) (0xA1 R) 
0x51 (0xA2 W) (0xA3 R) 
0x52 (0xA4 W) (0xA5 R) 
0x53 (0xA6 W) (0xA7 R) 
0x60 (0xC0 W) (0xC1 R) // TV tuner 
0x63 (0xC6 W) (0xC7 R) // TV tuner
```

