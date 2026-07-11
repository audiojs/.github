<h1 align="center">audiojs</h1>

<p align="center"><strong>Open Audio Stack</strong> — decode · process · analyse · synthesise · play.</p>

<p align="center">
  <a href="https://npmjs.org/package/audio-decode"><img src="https://img.shields.io/npm/dw/audio-decode?label=audio-decode&color=444" alt="audio-decode downloads"></a>
  <a href="https://npmjs.org/package/audio-buffer"><img src="https://img.shields.io/npm/dw/audio-buffer?label=audio-buffer&color=444" alt="audio-buffer downloads"></a>
  <a href="https://npmjs.org/package/audio-type"><img src="https://img.shields.io/npm/dw/audio-type?label=audio-type&color=444" alt="audio-type downloads"></a>
  <a href="https://github.com/audiojs/audio/actions/workflows/test.yml"><img src="https://github.com/audiojs/audio/actions/workflows/test.yml/badge.svg" alt="tests"></a>
  <img src="https://img.shields.io/badge/license-MIT-green" alt="MIT">
</p>

<p align="center"><a href="https://www.npmjs.com/package/audio"><img src="https://raw.githubusercontent.com/audiojs/.github/main/profile/terminal.svg" width="280" height="58" alt="npm i audio"></a></p>

```js
import audio from 'audio'

audio('raw.wav').trim(-30).normalize('podcast').fade(0.3, 0.5).save('clean.mp3')
let [lufs, bpm] = await audio('track.flac').stat(['loudness', 'bpm'])
```

```sh
audio raw.wav trim -30db normalize podcast fade 0.3s -0.5s save clean.mp3   # same engine, CLI
```

Browser, Node, Deno, Bun, workers, edge — no ffmpeg, no upload, no native deps.

## Atoms

Every algorithm is its own package — 280+ atoms across 35 families. Install one kernel (`@audio/dynamics-compressor`), one family (`@audio/dynamics`), or let [`audio`](https://github.com/audiojs/audio) host them all — batch, streaming, AudioWorklet, CLI.

| Domain | Families |
|---|---|
| **Pitch & time** | [shift](https://github.com/audiojs/shift) · [stretch](https://github.com/audiojs/stretch) · [resample](https://github.com/audiojs/resample) · [tune](https://github.com/audiojs/tune) |
| **Tone & dynamics** | [filter](https://github.com/audiojs/filter) · [eq](https://github.com/audiojs/eq) · [dynamics](https://github.com/audiojs/dynamics) · [saturate](https://github.com/audiojs/saturate) · [amp](https://github.com/audiojs/amp) · [weighting](https://github.com/audiojs/weighting) |
| **Space & effects** | [reverb](https://github.com/audiojs/reverb) · [spatial](https://github.com/audiojs/spatial) · [effect](https://github.com/audiojs/effect) |
| **Restore** | [denoise](https://github.com/audiojs/denoise) · [defeedback](https://github.com/audiojs/defeedback) · [vocals](https://github.com/audiojs/vocals) |
| **Analyse** | [pitch](https://github.com/audiojs/pitch) · [beat](https://github.com/audiojs/beat) · [loudness](https://github.com/audiojs/loudness) · [spectral](https://github.com/audiojs/spectral) · [mir](https://github.com/audiojs/mir) · [measure](https://github.com/audiojs/measure) · [auditory](https://github.com/audiojs/auditory) |
| **Synthesise** | [synth](https://github.com/audiojs/synth) · [voice](https://github.com/audiojs/voice) · [midi](https://github.com/audiojs/midi) · [note](https://github.com/audiojs/note) |
| **Codec & I/O** | [decode](https://github.com/audiojs/decode) · [encode](https://github.com/audiojs/encode) · [mic](https://github.com/audiojs/mic) · [speaker](https://github.com/audiojs/speaker) |
| **Substrate** | [stft](https://github.com/audiojs/stft) · [window](https://github.com/audiojs/window) · [sinusoidal](https://github.com/audiojs/sinusoidal) · [neural](https://github.com/audiojs/neural) |

## Verified

Against the sources of truth, not against itself:

| Domain | Traceability |
|---|---|
| Loudness | EBU R128 · ITU-R BS.1770 test vectors |
| Filters | biquads to 1e-9 vs reference design |
| Synthesis | FM sidebands to Bessel tables |
| Resampling | measured alias floors |
| MIR | MIREX-class evaluation sets |
| Measurement | Farina ESS round-trips |

Deterministic: same input, same output, every runtime.

## Roadmap

<p align="center"><img src="https://raw.githubusercontent.com/audiojs/.github/main/profile/roadmap.svg" width="830" alt="JS → AudioWorklet / WAM (today) → WASM (jz, in flight) → VST3 · CLAP · AU · LV2 (compile, planned); host brings native plugins the other way — into JS"></p>

One contract carries atoms beyond JS: [wam](https://github.com/audiojs/wam) runs them as Web Audio Modules / AudioWorklets today · [jz](https://github.com/dy/jz) compiles the same numeric kernels to lean GC-free WASM · native plugin targets (VST3 · CLAP · AU · LV2) follow via compile · [host](https://github.com/audiojs/host) brings native plugins the other way — into JS.

## Sponsor

**[github.com/sponsors/audiojs →](https://github.com/sponsors/audiojs)** — MIT forever; sponsorship funds the maintenance that keeps the stack coherent. Shipping on these packages? Upstream is cheaper than a fork.
