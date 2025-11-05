<img alt="resounder-logo" src="./assets/images/logo.png" style="margin-left:auto; margin-right:auto; display:block; width:200px;"/>

# ReSounder

**ReSounder** is a lightweight, browser-based spectrogram inverter that reconstructs audio from visual spectral data. It performs complete **phase reconstruction** using multiple algorithms, allowing you to transform spectrogram images back into intelligible, realistic sound — all locally in your browser.

[**View Live Demo**](https://nqrlabs.com/ReSounder/)

## Overview

ReSounder interprets spectrogram images across a range of color maps and frequency scales, then rebuilds the underlying waveform through deterministic, sample-accurate synthesis.  
It supports **linear**, **logarithmic**, **mel**, and **bark** scaling, as well as **Griffin–Lim**, **PGHI**, and **running-sine** reconstruction methods.

Every step runs client-side with no uploads or network activity.  
All computation happens using browser-native APIs for file handling, pixel processing, and audio encoding, ensuring full privacy and reproducibility.

## Features

- **True phase reconstruction:** Choose between Griffin–Lim, PGHI, or running-sine methods.  
- **Flexible frequency scaling:** Linear, log, mel, and bark modes for matching spectrogram exports.  
- **Multiple colormaps:** Supports grayscale, viridis, plasma, inferno, magma, jet, hot, cool, and parula.  
- **Dynamic range and noise control:** Adjust floor, range, and smoothing parameters to fine-tune results.  
- **Real-time preview:** View reconstructed waveform playback immediately in the browser.  
- **Offline operation:** Everything runs locally using Canvas and Web Audio APIs.  
- **Metadata-aware:** Automatically reads `tEXt` fields from PNG spectrograms exported by compatible tools (such as SpectroGhost).

## Technical Notes

### Phase Reconstruction

ReSounder provides multiple phase estimation methods:

- **Griffin–Lim:** Iterative STFT-based phase refinement with controllable iteration count.  
- **PGHI (True/Approximate):** Phase Gradient Heap Integration for accurate analytic phase estimation.  
- **Running-Sine:** Simple forward-synthesis model for fast and approximate reconstructions.

### Frequency Mapping

- Linear mapping matches raw FFT outputs.  
- Log, Mel, and Bark scales are supported for perceptual spectrograms.  
- Automatic bin-to-frequency conversion ensures accurate pitch and tone recovery.

### Color Interpretation

- Built-in support for common colormaps (grayscale, viridis, jet, etc.).  
- Optional **invert colors** toggle for spectrograms with reversed intensity.  
- Custom luminance mapping converts color pixels to magnitude estimates before FFT reconstruction.

### Audio Handling

- Uses native **Canvas** APIs for image processing.  
- Custom **Radix-2 FFT** and **iSTFT** implementations written in JavaScript.  
- Encodes output to **16-bit PCM WAV** entirely in memory via **DataView** and **Blob** APIs.  
- Playback through the built-in HTML5 `<audio>` element.  

## Intended Users

ReSounder was designed for sound designers, ARG creators, and researchers exploring the intersection of vision and audio.  
It serves equally well as an educational tool for students studying Fourier analysis, a reconstruction utility for creative technologists, or a forensics tool for decoding image-based audio.

## Usage

1. Open the app in your browser.  
2. Load or paste a spectrogram image (PNG, JPG, etc.).  
3. Adjust **FFT size**, **sample rate**, and **frequency scale**.  
4. Select the desired **phase reconstruction** algorithm.  
5. Set **dynamic range**, **noise floor**, and **color map** options.  
6. Click **Invert Spectrogram** to begin reconstruction.  
7. Preview or download the generated WAV audio file.  

Everything runs locally — no data leaves your system.

## License

MIT License — free for modification and use. Attribution appreciated if used publicly.  

## Credit

Created by **NQR** for audio explorers, puzzle designers, and creative technologists who enjoy exploring the mysteries of the seen but unheard.
If you use *ReSounder* in a project or ARG, I’d love to hear about it.