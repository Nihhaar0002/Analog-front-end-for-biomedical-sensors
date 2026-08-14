# Design Specifications

## 1. Project Scope

Design a **low-noise, low-power Analog Front-End (AFE)** for EEG signal acquisition.

### Signal Chain

**EEG Electrodes → LNA → Programmable Gain → Analog Filters → Conditioned Analog Output**

ADC and digital signal processing are outside the scope of this project.

---

## 2. EEG Signal Specifications

| Parameter        | Initial Target |
| ---------------- | -------------: |
| Signal           |            EEG |
| Input amplitude  |       5–100 µV |
| Signal bandwidth |      0.5–50 Hz |
| Input type       |   Differential |
| Input impedance  |         ≥ 1 GΩ |

The amplitude and bandwidth ranges are selected from published EEG and biopotential-AFE literature.

### References for EEG Parameters

* **"Highly Configurable 100 Channel Recording and Stimulating Integrated Circuit for Biomedical Experiments"** — EEG amplitude/frequency characteristics.
* **"Multi-Channel Neural Recording Implants: A Review"** — neural-signal amplitude and bandwidth ranges.
* **"A 0.6-µW Chopper Amplifier Using a Noise-Efficient DC Servo Loop and Squeezed-Inverter Stage for Power-Efficient Biopotential Sensing"** — low-power biopotential amplification.
* **"Improvement of EEG Signal Acquisition: An Electrical Aspect for State of the Art of Front End"** — EEG amplitude, noise, and input-impedance considerations.

The exact values will be refined during the design process.

---

## 3. LNA

| Parameter            |                    Target |
| -------------------- | ------------------------: |
| Gain                 |                  20–40 dB |
| Input impedance      |                    ≥ 1 GΩ |
| Input-referred noise |                ≤ 1 µV RMS |
| Input                |          Differential EEG |
| Power                | Within total power budget |

Primary objectives:

* Low input-referred noise
* High input impedance
* Low power consumption
* Adequate gain
* High CMRR

---

## 4. Programmable Gain Stage

| Parameter       |                     Target |
| --------------- | -------------------------: |
| Additional gain |                    0–40 dB |
| Gain control    | Multiple selectable levels |
| Noise           |                  Minimized |
| Power           |        Within total budget |

Exact gain settings will be determined after LNA and output-swing analysis.

---

## 5. Analog Filters

| Parameter        |   Initial Target |
| ---------------- | ---------------: |
| High-pass cutoff |          ~0.5 Hz |
| Low-pass cutoff  |           ~50 Hz |
| Passband         |       ~0.5–50 Hz |
| Filter order     | To be determined |
| 50-Hz notch      |  To be evaluated |

The filter stage will suppress unwanted low- and high-frequency components and evaluate rejection of power-line interference.

---

## 6. Overall AFE Targets

| Parameter            |                 Target |
| -------------------- | ---------------------: |
| Input signal         |               5–100 µV |
| Bandwidth            |              0.5–50 Hz |
| LNA gain             |               20–40 dB |
| Programmable gain    |                0–40 dB |
| Input impedance      |                 ≥ 1 GΩ |
| Input-referred noise |             ≤ 1 µV RMS |
| Total power          |         < 5 µW/channel |
| Output               | Conditioned analog EEG |

---

## 7. Verification

The design will be evaluated using transistor-level simulations:

* DC operating point
* AC gain and bandwidth
* Noise
* Transient response
* Power consumption
* Input impedance
* CMRR
* Filter response
* Output swing

---

## 8. Parameters To Be Finalized

* LNA topology
* Exact gain
* Programmable gain levels
* Filter topology and order
* Cutoff frequencies
* Supply voltage
* CMOS technology
* Bias currents
* Transistor dimensions
* Final noise and power targets

Specifications will be updated as the design progresses.
