# Vectron AI

## Description

Vectron AI interfaces with the Vectron 64 breadboard computer (6502 CPU @ 1MHz, 32KB RAM, 32KB ROM) to provide gesture detecting artificial intelligence. The gesture detection is used to control an Atari 2600 emulator.
Images are captured, downscaled, and converted to an integer vector by a Raspberry Pi 3 B+. The vector is then transferred, one byte at a time, to a shift register in Vectron AI. After each byte is loaded, an interrupt is sent to the Vectron 64 computer.

The Vectron 64 retrieves each byte and stores it in RAM. When a full image has been received, it runs a k-nearest neighbor algorithm to classify the current image against 50 known images that are stored in the ROM. The class of the best match (minimum sum of all pixel distances) determines the predicted class of the current image. 
The Vectron 64 then puts an address on the address bus that Vectron AI interprets and in turn sends a signal to a GPIO pin on another Raspberry Pi 3 B+. This Raspberry Pi is running a script that converts the GPIO signal to a simulated keypress. The simulated keypress controls a Stella Atari 2600 emulator.

When this is all put together, you can place your hand in front of the camera with any of the known gestures (e.g. "up", "down", "left", "right"), and the game will be controlled accordingly.

## Vectron 64 
Vectron 64 is a custom-built general-purpose, programmable, 6502-based computer and operating system. The MOS Technology 6502 (typically "sixty-five-oh-two" or "six-five-oh-two") is an 8-bit microprocessor that was designed by a small team led by Chuck Peddle for MOS Technology. The design team had formerly worked at Motorola on the Motorola 6800 project; the 6502 is essentially a simplified, less expensive and faster version of that design.

When it was introduced in 1975, the 6502 was, by a considerable margin, the least expensive microprocessor on the market. It initially sold for less than one-sixth the cost of competing designs from larger companies, such as the 6800 or Intel 8080. Its introduction caused rapid decreases in pricing across the entire processor market. Along with the Zilog Z80, it sparked a series of projects that resulted in the home computer revolution of the early 1980s.

## Project Image

![](https://hackster.imgix.net/uploads/attachments/1104547/ai_module_sm.jpg?auto=compress%2Cformat&w=740&h=555&fit=max)




