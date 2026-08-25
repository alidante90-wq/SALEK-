# SALEK // HYPERCORE 1.0 — Advanced Architecture

This is an expanded JUCE/C++ VST3 architecture for a signature Hi-Tech synthesizer.

## Engine
- 16 voice polyphony
- dual oscillator hybrid waveform architecture
- morph + mutation + chaos
- ADSR amplitude envelope
- per-voice LFO
- filter and resonance
- nonlinear drive
- stereo delay
- macro parameters
- host automation/state support

## Next production layer
Real wavetable loading, MSEG, modulation matrix routing, granular oscillator,
advanced oversampled distortion, convolution/algorithmic reverb and preset browser.

Build:
cmake -B build -S . -DJUCE_DIR="C:/JUCE"
cmake --build build --config Release
