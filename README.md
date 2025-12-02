# Underwater Communication System for Rovers (Acoustic Signalling Project)

## 1. Why it is built

Underwater communication is extremely challenging because **radio signals cannot travel well in water**—they get absorbed rapidly. ROVs (Remotely Operated Vehicles) therefore depend on **acoustic communication**, which travels long distances underwater.

This project was built to:

* Enable **reliable communication** between underwater robots and surface stations
* Understand and implement **low-frequency acoustic signalling**
* Explore real-world challenges like noise, attenuation, and multipath
* Study how underwater communication supports **defense, ocean research, and autonomous vehicles**

The aim is to create a **simple, low-frequency acoustic communication link** suitable for small underwater robots or ROVs.

---

## 2. How it is built

The system uses a combination of **analog electronics, acoustic transducers, and digital signal handling**:

* **Low-frequency transmitter**

  * A function generator or microcontroller produces a low-frequency acoustic tone
  * The signal is amplified and fed into an underwater acoustic transducer

* **Receiver front-end**

  * A hydrophone or receiving transducer captures incoming signals
  * Signal passes through:

    * Pre-amplifier
    * Band-pass filter
    * Envelope detector / rectifier
  * Output is fed to a microcontroller for decoding simple bursts or tones

* **Communication method**

  * Uses simple **tone-based signalling** or short telemetry bursts
  * Designed for small message packets (presence detection, commands, status updates)

Additionally, both the transmitter and receiver run lightweight **C firmware** on their respective microcontrollers. This firmware handles:

* Generating low-frequency acoustic bursts
* Timing and triggering of telemetry signals
* Reading filtered signals from the analog front end
* Threshold detection and basic decoding of received tones
* Synchronization between send and receive cycles

Only a **high-level description** is shared. Simulation studies and circuits (AFE, transmitter) were tested in LTspice and breadboard prototypes.

---

## 3. What it does

* Sends **acoustic signals underwater** using low-frequency sound waves

* Allows a surface station or another ROV to detect:

  * The presence of the rover
  * Basic status information
  * Simple commands or triggers

* The receiver captures the sound, filters it, and extracts the information using envelope detection or threshold-based decoding

In simple terms:

> It lets two underwater devices "talk" to each other using sound, similar to submarine communication but at a small experimental scale.
