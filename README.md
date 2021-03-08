# Xtrem Bots Mazzy

Mazzy is a BLE controllable robot. This is a placeholder for Xtrem Bots Mazzy mainboard circuit diagram.

Meanwhile:
- BLE chip: AC6926A (JL / Jerry)
- motor driver: MX1616L
- amplifier (for the speaker): NS8002B
- external flash: unknown (top marking removed) but pin compatible with common SOIC-8 SPI flash memories

Basically, I started to analyze the circuit as the robot designed to work with 4x alkaline batteries but I wanted to use rechargeable NiMH batteries. However, if operated from NiMH batteries, due to the voltage differences, the robot turns off quickly when the voltage of the batteries drop.

I found that there is a battery voltage divider which divides the 6V nominal voltage to GPIO-compatible 1.5V (R12/R11, 100k/300k). Replacing R11 by a 220k resistor will result in 1.5V on the GPIO if the battery voltage is 4.8V (~nominal voltage of 4x NiMH).
