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
| **MK4** | 2025-07-14 | - Fully redesigned PCB to prioritize affordable manufacturability, minimizing unique component count and relying solely on standard, non-exotic passive components available from major low-cost assembly houses<br>- Replaced PLL synthesizer with the TI LMK61E2 programmable oscillator, simplifying frequency generation and reducing BOM complexity |
| **MK3** | 2025-07-03 | - Replaced previous fixed-frequency SAW filter with a wideband SAW filter to support flexible carrier generation<br>- Inserted a transformer balun after the SAW filter to convert 200 Ω differential output to 50 Ω single-ended, improving impedance matching and integration with the final PA<br>- Added low-noise preamplifiers before the passive mixer stage to improve upconversion SNR and mixer drive levels<br>- Modified the power amplifier chain for improved linearity and thermal performance under increased output drive<br>- Introduced a programmable digital potentiometer in the VCO modulation path to dynamically control modulation bandwidth, allowing application-specific FM deviation tuning<br>- Narrowed and finalized the carrier frequency range to 80–115 MHz for better compatibility with existing commercial and amateur FM-band antennas<br>- Integrated a microcontroller-interfaced tuning knob (potentiometer) to set center frequency, allowing real-time adjustment of carrier offset without reprogramming<br>- Added a level shifter IC between microcontroller I/O and the PLL synthesizer’s SPI interface to ensure proper logic-level compatibility |
| **MK2** | 2025-06-13 | - Replaced 50 MHz SAW filter with custom 3rd-order Butterworth filter to reduce insertion loss (~11 dB → <1 dB)<br>- Added second-stage amplifier to boost output power into 10–20 dBm range<br>- Inserted impedance-matched Pi attenuator before PA stages to ensure operation within P1dB<br>- Removed redundant RF tap after final amplifier (will probe SMA output directly if needed)<br>- Moved PLL Synth power supply from external microcontroller to on board power plane |
| **MK1** | 2025-05-02 | - Initial layout fabricated but not assembled<br>- SAW filter chain insertion loss (~15 dB) resulted in poor power budget<br>- No sufficient gain staging; final output estimated <1 mW<br>- Identified layout and topology flaws upon physical inspection<br>- Informed redesign of gain chain, filtering, and impedance matching in MK2 |
