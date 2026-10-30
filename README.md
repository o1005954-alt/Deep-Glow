[github_readme (1).md](https://github.com/user-attachments/files/34183649/github_readme.1.md)
# Deep Glow (Open) for EffectCraft

An original multi-scale glow plug-in for **EffectCraft** (WebAssembly, plug-in API v1).
It is inspired by the look of premium glow plug-ins, but shares no code with them.

## 🖼️ Preview

| Before | After (Deep Glow) |
| :---: | :---: |
| <img width="1286" height="737" alt="Screenshot 1448-05-19 at 3 39 45 PM" src="https://github.com/user-attachments/assets/bb1c7bbd-f0cd-4807-b198-fd225823d365" /> | <img width="1278" height="716" alt="Screenshot 1448-05-19 at 3 48 45 PM" src="https://github.com/user-attachments/assets/aac6ba26-84f5-4c61-8e37-47d53fd3213e" /> |

*Comparison showing standard input vs. multi-scale glow output with chromatic spread enabled.*

## 💾 Installation

1. Download the compiled `deep_glow.wasm` file from the [Releases page](../../releases).

2. Install the plug-in using one of the following methods:

   * **Directly in EffectCraft:** Go to `Effect` ▸ `Load Effect Plug-in…` and select the `.wasm` file.

   * **Manual Installation:** Move `deep_glow.wasm` to your platform's Plug-ins directory:

     * 🐧 **Linux:** `~/.config/effectcraft/Plug-ins/`

     * 🍎 **macOS:** `~/Library/Application Support/EffectCraft/Plug-ins/`

     * 🪟 **Windows:** `%APPDATA%\EffectCraft\Plug-ins\`

## 🎛️ Controls

| Control | Type | Description | 
| ----- | ----- | ----- | 
| **Threshold** | Slider | Luminance (%) a pixel must reach before it glows. Values above 100% work in 32-bpc projects. | 
| **Threshold Softness** | Slider | Soft knee around the threshold to prevent harsh cutoffs. | 
| **Radius** | Slider | Glow size in pixels (automatically scales with preview resolution). | 
| **Intensity** | Slider | Overall glow strength (%). Recommended to raise for very wide radii. | 
| **Falloff** | Slider | Controls energy distribution. Low = wide, hazy halo. High = tight, hot core. | 
| **Tint Hue / Amount** | Sliders | Colorizes the glow output. Set `Tint Amount` to `0` to preserve original source colors. | 
| **Chromatic Spread** | Slider | Simulates lens fringe dispersion by glowing red wider than blue. | 
| **Glow Only** | Checkbox | Outputs strictly the isolated glow pass without the underlying source layer. | 

## ⚡ Performance & Compatibility

* **Rendering:** Because plug-ins run within a sandboxed interpreter, processing large frames may be slower than native built-in effects.

* **Workflow Tip:** It is recommended to set preview resolution to half or quarter while fine-tuning heavy glow parameters.
