# RX 2ch (mix tank-arcade motor driver, telemetry)

Many thanks to Stanek for the receiver code

https://github.com/stanekTM/RX_nRF24L01_Telemetry_Motor_Servo/tree/master/RX_nRF24L01_2ch_A1_Motor_Mix_Tank


RC receiver nRF24L01 with ATmega328P/16Mhz, Arduino Nano or Pro Mini.
Telemetry sends the monitored voltage RX to TX.
The motor driver IC is based on MX1208, MX1508, MX1515, MX1616, MX1919 and others similar, using 4x PWM input control signals.
The possibility of setting the brake is in the code.
The firmware will be used for micro boats, tanks and robots.

This RC receiver works with RC transmitters [TX_nRF24L01_4ch_Telemetry_LCD](https://github.com/stanekTM/TX_nRF24L01_4ch_Telemetry_LCD) or
[TX_nRF24L01_5ch_Telemetry_LED](https://github.com/stanekTM/TX_nRF24L01_5ch_Telemetry_LED) or with [TX_nRF24L01_4ch_Telemetry_LCD_ttp224](https://github.com/HNeumeier/TX_nRF24L01_4ch_Telemetry_LCD_ttp224) from my fork.

Note: I use (Arduino Nano)

## Function
* MotorA = adjustable pwm/ch1 - mix tank-arcade
* MotorB = adjustable pwm/ch2 - mix tank-arcade
* Brake = on, off or adjustable effect
* Normal mode = LED RX is lit
* Battery voltage 1S LiPo (4.2V) < monitored voltage = RX LED flash at a interval of 0.5s
* TX transmitter off or signal loss = RX LED flash at a interval of 0.1s
* Fail-safe = MotorA and MotorB stopped

## Arduino pins
```
D9  - pwm1/MotorA
D10 - pwm2/MotorA
D3  - pwm3/MotorB
D11 - pwm4/MotorB

D2  - LED
A7  - telemetry analog input RX battery

nRF24L01:
A0  - CE
A1  - CSN
A2  - SCK
A3  - MOSI
A4  - MISO
```

## Used libraries
* <RF24.h>      https://github.com/nRF24/RF24
* <DigitalIO.h> https://github.com/greiman/DigitalIO
