# Direct FM Transmitter (50 MHz)

A component-level FM transmitter designed from scratch to demonstrate RF system design and PCB layout skills for applications in low-power, narrowband wireless communication.

## Project Overview

This project showcases a custom-built direct FM transmitter operating at 50 MHz, featuring:


- A free-running VCO directly modulated with analog input (FM signal source)
- A stable PLL synthesizer locked to a crystal reference
- A mixer stage that translates the VCO signal using the PLL output to produce a frequency-offset IF
- SAW-filtered RF chain
- Mixer-based frequency translation
- Custom 3–5 pole Butterworth bandpass filter at 50 MHz
- Two-stage Low-power RF amplifier 
- RF test points and SMA-tapped outputs
- Designed entirely on a 4-layer impedance-controlled PCB

The full signal chain was analyzed, simulated, and validated using spectrum analyzer + VNA measurements.

## 🔁 Revision History

| Version | Date       | Summary of Changes |
|---------|------------|--------------------|
| **MK2** | 2025-06-XX | - Replaced 50 MHz SAW filter with custom 3rd-order Butterworth filter to reduce insertion loss (~11 dB → <1 dB)<br>- Added second-stage amplifier to boost output power into 10–20 dBm range<br>- Inserted impedance-matched Pi attenuator before PA stages to ensure operation within P1dB<br>- Removed redundant RF tap after final amplifier (will probe SMA output directly if needed) |
| **MK1** | 2025-05-XX | - Initial layout fabricated but not assembled<br>- SAW filter chain insertion loss (~15 dB) resulted in poor power budget<br>- No sufficient gain staging; final output estimated <1 mW<br>- Identified layout and topology flaws upon physical inspection<br>- Informed redesign of gain chain, filtering, and impedance matching in MK2 |


