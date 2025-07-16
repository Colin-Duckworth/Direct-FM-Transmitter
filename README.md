# Direct FM Transmitter (80-115 MHz)

A component-level FM transmitter designed from scratch to demonstrate RF system design and PCB layout skills for applications in low-power, narrowband wireless communication.

## Project Overview

As of revision MK4, the system has been fully re-engineered to prioritize **manufacturability, affordability, and modular signal control**. The transmitter features:

- A **free-running VCO** directly modulated with an analog signal to produce wideband FM
- A **TI LMK61E2 programmable oscillator** used in place of a PLL synthesizer, simplifying the frequency control architecture while maintaining tunability and spectral stability
- A **mixer stage** that upconverts the modulated VCO signal using the oscillator output, enabling frequency offset generation
- A flexible **filtering stage**, configurable between a custom-designed 3–5 pole Butterworth bandpass filter and a wideband SAW filter depending on use case
- A **transformer balun** to convert 200 Ω differential signals to 50 Ω single-ended, improving impedance matching for the final power amplifier
- A two-stage **low-power RF amplifier chain** redesigned for improved linearity and thermal stability under higher output drive
- A **programmable digital potentiometer** in the VCO modulation path to dynamically adjust FM deviation and bandwidth
- An **on-board microcontroller interface** with tuning knob for real-time center frequency control
- Full **impedance matching** between all major blocks using standard-value passives and Pi attenuators to ensure operation within amplifier P1dB
- A layout optimized for **low-cost 4-layer PCB fabrication**, using only **common, non-exotic components** to minimize BOM cost and unique part count for low-volume assembly services like JLCPCB
- RF test points and SMA-tapped outputs for validation and debugging

The complete signal chain was simulated, measured, and iteratively refined based on real VNA and spectrum analyzer results, making this project both a learning platform and a functional RF transmitter.


## 🔁 Revision History

| Version | Date       | Summary of Changes |
|---------|------------|--------------------|
| **MK4** | 2025-07-14 | - Fully redesigned PCB to prioritize affordable manufacturability, minimizing unique component count and relying solely on standard, non-exotic passive components available from major low-cost assembly houses<br>- Replaced PLL synthesizer with the TI LMK61E2 programmable oscillator, simplifying frequency generation and reducing BOM complexity |
| **MK3** | 2025-07-03 | - Replaced previous fixed-frequency SAW filter with a wideband SAW filter to support flexible carrier generation<br>- Inserted a transformer balun after the SAW filter to convert 200 Ω differential output to 50 Ω single-ended, improving impedance matching and integration with the final PA<br>- Added low-noise preamplifiers before the passive mixer stage to improve upconversion SNR and mixer drive levels<br>- Modified the power amplifier chain for improved linearity and thermal performance under increased output drive<br>- Introduced a programmable digital potentiometer in the VCO modulation path to dynamically control modulation bandwidth, allowing application-specific FM deviation tuning<br>- Narrowed and finalized the carrier frequency range to 80–115 MHz for better compatibility with existing commercial and amateur FM-band antennas<br>- Integrated a microcontroller-interfaced tuning knob (potentiometer) to set center frequency, allowing real-time adjustment of carrier offset without reprogramming<br>- Added a level shifter IC between microcontroller I/O and the PLL synthesizer’s SPI interface to ensure proper logic-level compatibility |
| **MK2** | 2025-06-13 | - Replaced 50 MHz SAW filter with custom 3rd-order Butterworth filter to reduce insertion loss (~11 dB → <1 dB)<br>- Added second-stage amplifier to boost output power into 10–20 dBm range<br>- Inserted impedance-matched Pi attenuator before PA stages to ensure operation within P1dB<br>- Removed redundant RF tap after final amplifier (will probe SMA output directly if needed)<br>- Moved PLL Synth power supply from external microcontroller to on board power plane |
| **MK1** | 2025-05-02 | - Initial layout fabricated but not assembled<br>- SAW filter chain insertion loss (~15 dB) resulted in poor power budget<br>- No sufficient gain staging; final output estimated <1 mW<br>- Identified layout and topology flaws upon physical inspection<br>- Informed redesign of gain chain, filtering, and impedance matching in MK2 |
