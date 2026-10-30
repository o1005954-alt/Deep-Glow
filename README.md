
# Deep Glow (Open) for EffectCraft

An original multi-scale glow plug-in for **EffectCraft** (WebAssembly, plug-in API v1).
It is inspired by the look of premium glow plug-ins, but shares no code with them.

## 🖼️ Preview

| Before | After (Deep Glow) |
| :---: | :---: |
| <img width="2408" height="1506" alt="image" src="https://github.com/user-attachments/assets/858d701c-78b5-4de8-aacb-b0c332f7c105" />
 | <img width="2408" height="1506" alt="image" src="https://github.com/user-attachments/assets/5d26722b-68e5-4b72-878a-4c0ceafcc9f3" />
 |

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
