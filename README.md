# FELA / erhcetua

`FELA` is a JUCE MIDI FX plugin for Logic Pro that generates mathematically shaped bell cycles, cross-rhythms, and pulse variations inspired by several West African rhythmic families. It outputs MIDI notes only and renders the pattern in a custom visual orbit/timeline display.

`erhcetua` is a second JUCE MIDI FX plugin in the same project, focused on reset-driven generative grammar and lane mutation.

## Features

- AU MIDI FX target for Logic Pro, with `VST3` and `Standalone` targets also generated for development.
- Six rhythm families: `Ewe Bell`, `Bembe`, `Kpanlogo`, `Gahu`, `Sikyi`, and `Cross-Rhythm`.
- Pattern generation via modular arithmetic, Euclidean pulse distribution, rotation, symmetry, swing, and probabilistic triggering.
- Four MIDI output lanes: `Bell`, `Support`, `Bass`, and `Shaker`, each with its own target note.
- Preset banks with named variations for each rhythm family.
- Visual editor with a circular rhythm wheel and per-lane timeline display.
- User controls for preset, family, density, complexity, rotation, swing, probability, lane notes, channel, and gate length.

## Build

You need a local JUCE checkout.

```bash
cmake -B build -S . -DJUCE_DIR=/absolute/path/to/JUCE
cmake --build build --config Release
```

For Logic Pro, use the generated AU target. Both plugins are configured as MIDI effects (`IS_MIDI_EFFECT TRUE`) so they can be inserted in Logic's MIDI FX slot.

## Notes

- The rhythm labels identify the family that seeds each algorithm. The plugin does not attempt to be a scholarly transcription engine; it uses those timelines as mathematical starting points for generative variation.
- The processor depends on host transport and tempo information for sample-accurate scheduling.
- Presets are designed as performance starting points. You can load a preset bank variation, then retune the four lane notes to match any drum rack or sampler.
