# Xtrem Bots Mazzy

Mazzy is a BLE controllable robot.

I started to analyze the circuit as the robot was designed to work with 4x alkaline batteries but I wanted to use rechargeable NiMH batteries. However, if operated from NiMH batteries, due to the voltage differences, the robot turns off quickly when the voltage of the batteries drops.

I found that there is a battery voltage divider that divides the 6V nominal voltage to GPIO-compatible 1.5V (R12/R11, 100k/300k). Replacing R11 with a 220k resistor will result in 1.5V on the GPIO if the battery voltage is 4.8V (~nominal voltage of 4x NiMH).

Meanwhile, I studied the other parts of the board then finally, I reverse engineered the whole circuit.

Main parts:
- BLE chip: AC6926A (JL / Jerry)
- motor driver: MX1616L
- amplifier (for the speaker): NS8002B
- external flash: unknown (top marking removed) but pin-compatible with common SOIC-8 SPI flash memories

I captured the schematic by Kicad but exported the result to .pdf for convenience.

Note, the circuit was reverse-engineered based on the existing PCB so, it may not 100% complete. Additionally, expect inaccuracies.