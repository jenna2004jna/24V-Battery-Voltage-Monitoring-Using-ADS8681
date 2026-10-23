# 24V Battery Voltage Monitoring Using ADS8681

A high-precision 24 V battery monitoring circuit based on the Texas Instruments ADS8681 16-bit ADC. The design uses a resistor divider to scale the battery voltage into a suitable range for the ADC input and includes filtering components for reliable analog measurement.

## Overview

This project is designed to measure a 24 V battery voltage using the ADS8681, a 16-bit analog-to-digital converter (ADC) from Texas Instruments. A resistor-based voltage divider scales the battery voltage to a safe input level for the ADC, and the converted digital value is read by a microcontroller through the SPI interface.

The circuit is suitable for battery health monitoring, industrial battery systems, embedded measurement applications, and BMS prototyping.

## Schematic Diagram
<img width="902" height="243" alt="image" src="https://github.com/user-attachments/assets/e8cd5e4c-c8c1-4f11-b2e1-ef46a718ff9e" />
## Hardware Components

- ADS8681IPWR — 16-bit SAR ADC for precise voltage measurement
- R1 — 68 kΩ, upper resistor of the voltage divider
- R2 — 10 kΩ, lower resistor of the voltage divider
- C1 — 100 nF, ADC input filter capacitor
- Decoupling capacitors — for supply and reference stability
- 24 V battery input — source being monitored

## Working Principle

The voltage divider reduces the battery voltage before it is applied to the ADS8681 analog input. The ADC converts the scaled analog voltage into digital data, which can then be processed by a connected microcontroller over the SPI interface.

The battery negative terminal provides the common ground reference for the measurement circuit, ensuring a stable and consistent analog measurement.

## Voltage Divider Calculation

The ADC input voltage is calculated using:

V_ADC = V_BAT × (R2 / (R1 + R2))

For R1 = 68 kΩ and R2 = 10 kΩ:

- Battery voltage: 24 V
- ADC input voltage: approximately 3.08 V
- Divider ratio: 7.8:1

At a maximum battery voltage of 30 V, the ADC input is approximately 3.85 V.

## Key Features

- 16-bit precision ADC-based measurement
- Resistor-based voltage scaling
- Capacitor-based input noise filtering
- SPI-compatible digital interface
- Common-ground battery measurement
- Suitable for 24 V battery systems

## Applications

- 24 V battery voltage monitoring
- Embedded measurement systems
- Industrial voltage monitoring
- Battery management system (BMS) prototyping
- Automotive and power-system prototyping

## Notes

Before PCB fabrication or production use, verify the following against the ADS8681 datasheet:

- Maximum battery voltage
- ADC input range and safe operating limits
- Supply decoupling requirements
- Reference capacitor values and placement
- Grounding and routing quality
- Input protection for industrial or automotive transients

## Datasheet

Texas Instruments ADS8681:
https://www.ti.com/lit/ds/symlink/ads8681.pdf
