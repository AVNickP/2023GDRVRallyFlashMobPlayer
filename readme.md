# Grand Design National Rally 2023 Flash Mob Player

This a the Q-SYS design an L-Acoustics Network Manager files for the Grand Design National Rally 2023 Flash Mob Player.

## Signal Flow
Software Dante was used as the primary transport of audio in this system. Thr core handled all mixing and playback functionality, while all system tuning and calibration was done in Network Manager and run on the LA4X Amplified Controller.

`
                                         QSC-NV-32-H
                                       _______________
UHF/UHF ANtenna ----> Icom IC-705 ---->| USB         |
                                       |             |
                 Shure ULX-P  -------->| Analog IN   |
                                       |             |
                                -------| LAN A       |
                                |      |_____________|
                                |
                                |      Network Switch
                                |      _______________
                                |______|             |
                                       |             |
Playback iPad ----> Dante AVIO USB --->|             |
             ------------------------->|             |
            |                          |_____________|
            |
            |
            |                          L'Acoustics LA4X
            |                          _______________
             --->Dante AVIO AES3 ----->| AES A/B   1 | ----> SYVA SUB
                                       |           2 | ----> SYVA SUB
                                       |           3 | ----> SYVA SUB
                                       |           4 | ----> X8 ---> X8
                                       |_____________|

`

## Flash Mob Playback
We need a way to trigger the playback of the track for the flash mob without depending on internet connectivity, as connectivity was unreliable at the fairgrounds. To overcome this I ended up doing a couple things:

- An audio player was used inside the Q-SYS core so that no external devices were required to play the track.
- A Ham radio transceiver was connected to the USB port of the Core and then tuned to a simplex frequency on the 2M band, the core then used the incoming audio to listen to DTMF tones and trigger the playback of the track.


## License
The MIT License (MIT)

Copyright 2023 Nick Paton

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.