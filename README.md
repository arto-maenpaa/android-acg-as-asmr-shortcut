# android-acg-as-asmr-shortcut

A production blueprint for leveraging the Android core OS automatic gain control (AGC) as an instant, zero-latency "ASMR engine." 

By purposefully exploiting the phone's native audio processing instead of trying to fight it, you can capture ultra-intimate whispers, intense proximity effects, and hyper-detailed mouth sounds straight to your stock camera roll—completely eliminating the need for post-production editing, digital compressors, or desktop DAWs.

## 🎙️ The Hack: The OS is Your Compressor

In standard audio engineering, Android's internal Automatic Gain Control (AGC) is usually treated as something to disable. However, for ASMR video production, it does exactly what an expensive boutique vocal chain is supposed to do:

* **Massive Upward Compression:** The moment you whisper quietly or create silence, the Android AGC aggressively pumps the gain up to maximum. It actively pulls up faint details, mouth clicks, tongue textures, and quiet breath sounds, making them sound massive, crisp, and incredibly close to the listener's ear.
* **Instant Brick-Wall Limiting:** When you make a sudden loud sound (like a sharp finger snap, tapping trigger, or object scrape), the hardware limits the volume instantly, preventing ear-piercing digital clipping (0 dBFS) and immediately ducking the signal back down cleanly.
* **Zero Post-Processing:** Because the processing happens live inside the OS stack, the output video file out of your stock camera roll is pre-compressed, pre-limited, and ready for direct upload to YouTube or TikTok.

### 🌿 The "Macro-Audio" Nature Hack
This identical AGC behavior explains why stock phone recordings of nature sounds (like rain, wind, or forest ambiance) often sound shockingly detailed. During quiet gaps in the environment, the OS aggressively scans for signal, pulling microscopic background textures—like distant bird chirps or individual leaves rustling—straight to the front of the audio mix while instantly protecting the file from sudden loud transient spikes.


## 🎛️ The Setup

You don't need custom recording software or specialized raw audio apps. You can use your phone's **built-in stock camera application**.

### 1. Hardware Path

```text
🎤 Mic ➔ 🎛️ Pre-amp/Mixer ➔ 🌉 iRig 2 Bridge ➔ 🔌 3.5mm Phone Jack
```

You feed your microphones through an analog interface bridge (like an IK Multimedia iRig 2) directly into the phone’s physical 3.5mm TRRS jack. This feeds a clean, high-quality mic signal directly into the phone's built-in motherboard preamp.

### 2. Software Configuration
* Open your phone's **Stock Camera App**.
* Switch to **Video Mode** and press record. 
* Do **not** use apps that bypass the system audio (like raw API hooks). The native OS *needs* to manage the audio stream for the AGC hack to work.

## 🔗 Technical Underpinnings

This repository focuses strictly on the ASMR application and gain staging of this hack. For the deep technical details on the Android USB stack limitations, TRRS impedance matching, and the underlying circuit physics, please refer to the core framework repository:

👉 **[non-clipping-realtime-recording-pipeline](https://github.com)**

## ⚖️ License

This documentation and setup blueprint are licensed under the **CERN Open Hardware License – Strongly Reciprocal (CERN-OHL-S v2)**.
