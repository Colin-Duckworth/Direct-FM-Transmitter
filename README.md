# Direct FM Transmitter (50 MHz)

A component-level FM transmitter designed from scratch to demonstrate RF system design and PCB layout skills for applications in low-power, narrowband wireless communication.

## 🎯 Project Overview

This project showcases a custom-built direct FM transmitter operating at 50 MHz, featuring:


- A free-running VCO directly modulated with analog input (FM signal source)
- A stable PLL synthesizer locked to a crystal reference
- A mixer stage that translates the VCO signal using the PLL output to produce a frequency-offset IF
- SAW-filtered RF chain
- Mixer-based frequency translation
- Custom 3–5 pole Butterworth bandpass filter at 50 MHz
- Low-power RF amplifier stage
- RF test points and SMA-tapped outputs
- Designed entirely on a 4-layer impedance-controlled PCB

The full signal chain was analyzed, simulated, and validated using spectrum analyzer + VNA measurements.
