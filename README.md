# Resounder

Resounder is a robust spectrogram inverter focused on **phase reconstruction** and **broad format compatibility**. It can analyze visual spectrogram data across multiple colormaps and frequency scales, then rebuild the corresponding audio signal.

## Key Features
- Converts spectrogram images back into audio
- Supports linear, logarithmic, mel, and bark frequency scaling
- Handles multiple colormaps and dynamic ranges
- Reconstructs phase rather than relying on magnitude-only estimates
- Useful for audio forensics, sonification, machine learning, and creative sound design workflows

## Why It Matters
Spectrograms often throw away phase information or hide it inside an image. Resounder works to recover that data and rebuild sound that is more faithful and intelligible than basic inversion approaches.

## Goals
- Make spectrogram-to-audio conversion more accessible
- Offer modular tools for experimentation with color, scaling, and phase algorithms
- Support research and creative communities working with audio in visual form
