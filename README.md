# Bandgap References 

## Description
-   The performance of analog circuits, parameters such as gain and bandwidth, depends on accurate bias volatges and currents.
-   These bias currents and voltages will vary again by the PVT(Process , Voltage , Tempurature) variations .
-   Bandgap reference circuits are essential in integrated citcuits to generate stable and precise voltage and current references, independent of PVT changes.

## Table of Contents
- [Requirements of a Reference](#requirements-of-a-reference)
- [Temperature-Independent References](#temperature-independent-references)
- [Negative TC Voltage](#negative-tc-voltage)
- [Positive TC Voltage](#positive-tc-voltage)
- [Bandgap Reference](#bandgap-reference)
- [Bipolar Bandgap Reference](#bipolar-bandgap-reference)
- [CMOS Bandgap Reference](#cmos-bandgap-reference)
- [Low-Voltage Bandgap Reference](#low-voltage-bandgap-reference)
- [PVT-Tolerant Bandgap Reference](#pvt-tolerant-bandgap-reference)
- [Compatibility with CMOS Technology](#compatibility-with-cmos-technology)
- [Current Reference](#current-reference)
- [Current Reference with SC Resistor](#current-reference-with-sc-resistor)
- [References](#references)

## Requirements of a Reference
A reference must provide a DC voltage or current that is:
- **Independent of Supply Variation**: E.g., V_CC: 2.7V → 3.0V
- **Independent of Temperature Variation**: E.g., T: -45 °C → 120 °C
- **Independent of Process Variation**: E.g., β of BJTs: ±30%

## Temperature-Independent References
- The reference voltage can be expressed as:
V_REF = α1 * V1 + α2 * V2
  where V1 is Proportional To Absolute Temperature (PTAT) and V2 is Complementary TAT (CTAT).


![Temperature-Independent References](pat<img width="791" height="427" alt="Screenshot 2025-08-02 193345" src="https://github.com/user-attachments/assets/1ac4ecb0-1b02-4ce8-9bb3-b8b1b82839be" />
h_to_image_1) <!-- Replace with actual image path -->

## Negative TC Voltage
-  The base-emitter voltage of a bipolar transistor V_BE exhibits a negative temperature coefficient (TC).
- For a bipolar device:
  I_C = I_S * exp(V_BE / V_T)
  where V_T = kT/q and I_S is proportional to μkT * n_i^2.
- Temperature dependence: μ ∝ μ0 * T^m, where m ≈ -2/3 and n_i^2 ∝ T^3 * exp(-E_g / (kT)), where E_g ≈ 1.12 eV is the bandgap energy of silicon.
- Thus, I_S = b * T^(4+m) * exp(-E_g / (kT)), where b is a proportional factor.

<!-- Replace with actual image path -->

## Positive TC Voltage
- The difference between two base-emitter voltages, ΔV_BE, exhibits a positive TC.
- To compensate for -1.5 mV/K, ln(n) ≈ 17.2, hence n ≈ 2.95 x 10^7.

![Positive TC Voltage](path_to_image_<img width="842" height="295" alt="PTC" src="https://github.com/user-attachments/assets/8382e955-1589-4394-8a2c-1cd3b156bfab" />
3) <!-- Replace with actual image path -->

## Bandgap Reference
- Large n can be mitigated if ΔV_BE is “Amplified” before it is added to V_BE.

![Bandgap Reference](path_to_image<img width="965" height="389" alt="bandgapref" src="https://github.com/user-attachments/assets/01348420-be21-4b1a-9a06-433f60579705" />
_4) <!-- Replace with actual image path -->

## Bipolar Bandgap Reference
### Issues
1. Gain-power-stability trade-offs
2. NPN bipolar transistors
3. Op-amp offset

![Bipolar Bandgap Reference](path_to_ima<img width="536" height="320" alt="Bipolar bandgapref" src="https://github.com/user-attachments/assets/72b91fc1-7053-425a-98d5-00ba4b686680" />
ge_5) <!-- Replace with actual image path -->

## CMOS Bandgap Reference
-  Replace resistors with controlled current sources.
- Bipolar transistors are implemented as PNP structures.
- Large n and non-unity ratio between I_E1 and I_E2.
  
![CMOS Bandgap Reference]<img width="462" height="407" alt="cmosref" src="https://github.com/user-attachments/assets/8cbffcbe-659a-4023-9f24-60b5e9da7dda" /> <!-- Replace with actual image path -->

## Low-Voltage Bandgap Reference
- In one configuration, V_out is around 1.25V.
- In another configuration, V_out can be as low as 700-800mV.
- Use of shunt resistors.
![Low-Voltage Bandgap Reference]<img width="782" height="484" alt="lowvolbgvr" src="https://github.com/user-attachments/assets/69c59a4b-067e-48d2-9c39-3b6843093160" /> <!-- Replace with actual image path -->

## PVT-Tolerant Bandgap Reference Effect of device mismatches is reduced.
- Supply-independent biasing reduces the effect of MOSFET mismatch.
- Reduces the effect of device mismatches.

![PVT-Tolerant Bandgap Reference]<img width="752" height="534" alt="pvttolerant" src="https://github.com/user-attachments/assets/12cf007c-64a0-4121-b8d1-90b509b37a34" /> <!-- Replace with actual image path -->

## Compatibility with CMOS Technology
- p+ diffusion inside n-well → Emitter
- n-well → Base
- p-substrate → Collector

![Compatibility with CMOS Technology] <img width="563" height="298" alt="compatability" src="https://github.com/user-attachments/assets/81c20924-1801-4c04-affe-733b6c510af0" />
 <!-- Replace with actual image path -->

## Current Reference
- Utilizes a Widlar Current Mirror.
- Current  I_{out}  is independent of the supply voltage.

![Current Reference]<img width="962" height="426" alt="Currentref" src="https://github.com/user-attachments/assets/a04377a7-d080-436b-8be9-734c9d711e46" />
 <!-- Replace with actual image path -->

## Current Reference with SC Resistor
- R_s can be replaced by a switched-capacitor equivalent for temperature insensitivity:
  R_s = 1 / (f * C_s)

![Current Reference with SC Resistor]<img width="699" height="389" alt="Screenshot 2025-08-02 194307" src="https://github.com/user-attachments/assets/2cf260b5-6c2c-497a-a7d3-e32d8bf19882" /> <!-- Replace with actual image path -->

## References
- K. E. Kujik, “A precision reference voltage source,” IEEE J. Solid-State Circuits, vol. 8, pp. 222 – 226, June 1973.
- H. Banba, H. Shiga, A. Umezawa, and T. Miyaba, “A CMOS bandgap reference circuit with sub-1-V operation,” IEEE J. Solid-State Circuits.
- B. Razavi, “The bandgap reference,” IEEE Solid-State Circuits Mag., vol. 8, pp. 9 – 12, Summer 2016.
- B. Razavi, "Design of Analog CMOS Integrated Circuits", Tata McGraw Hill, 2002, pp. 509 - 533.
- T. Brooks and A. L. Westwisk, “A Low-Power Differential CMOS Bandgap Reference,” ISSCC Dig. of Tech. Papers, pp. 248 – 249, February 1994.
