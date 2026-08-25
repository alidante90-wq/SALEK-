# Build Status

The project source and automated Windows build pipeline are prepared.

This environment has:
- C++ compiler
- CMake

This environment does not currently have:
- JUCE
- VST3 SDK/framework files
- outbound network access to retrieve JUCE

Therefore a genuine compiled `.vst3` binary cannot be produced inside this runtime without inventing a fake binary.

The included CMake project automatically fetches JUCE where network access exists.
The included GitHub Actions workflow builds on `windows-latest` and uploads the resulting VST3 as an artifact.
