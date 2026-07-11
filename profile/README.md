<h1 align="center">audiojs</h1>

<p align="center"><strong>Open Audio Stack</strong> — decode · process · analyse · synthesise · play.</p>

<p align="center"><a href="https://www.npmjs.com/package/audio"><img src="https://raw.githubusercontent.com/audiojs/.github/main/profile/terminal.svg" alt="npm install audio"></a></p>

```js
import audio from 'audio'

audio('raw.wav').trim(-30).normalize('podcast').fade(0.3, 0.5).save('clean.mp3')
let [lufs, bpm] = await audio('track.flac').stat(['loudness', 'bpm'])
```

```sh
audio raw.wav trim -30db normalize podcast fade 0.3s -0.5s save clean.mp3   # same engine, CLI
```

Browser, Node, Deno, Bun, workers, edge — no ffmpeg, no upload, no native deps.

## Stack

| Layer | Packages |
|---|---|
| **Engine** | [audio](https://github.com/audiojs/audio) — one import: batch · streaming · AudioWorklet · CLI |
| **Atoms** | 280+ algorithms in 35 families — the catalog below |
| **Platform** | [web-audio-api](https://github.com/audiojs/web-audio-api) · [audio-buffer](https://github.com/audiojs/audio-buffer) — W3C Web Audio outside the browser, WPT-verified |
| **Utilities** | [audio-type](https://github.com/audiojs/audio-type) · [pcm-convert](https://github.com/audiojs/pcm-convert) · [decibels](https://github.com/audiojs/decibels) · [audio-extensions](https://github.com/audiojs/audio-extensions) |
| **Bridges** | [wam](https://github.com/audiojs/wam) · compile · [host](https://github.com/audiojs/host) — atoms out as plugins, native plugins in; the roadmap below |

## Atoms

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

| Domain | Traceability |
|---|---|
| Loudness | EBU R128 · ITU-R BS.1770 test vectors |
| Filters | biquads to 1e-9 vs reference design |
| Synthesis | FM sidebands to Bessel tables |
| Resampling | measured alias floors |
| MIR | MIREX-class evaluation sets |
| Measurement | Farina ESS round-trips |

## Roadmap

One contract, every target:

1. [x] **JS** — every runtime
2. [x] **AudioWorklet** — [wam](https://github.com/audiojs/wam) wraps any atom as a Web Audio Module
3. [ ] **WASM** — [jz](https://github.com/dy/jz) compiles the same numeric kernels, GC-free
4. [ ] **VST3 · CLAP · AU · LV2** — native plugin targets via compile
5. [ ] **Native → JS** — [host](https://github.com/audiojs/host) loads AU / VST / CLAP plugins into the JS pipeline

## Sponsor

Run `npm fund` — this stack is probably already in your tree: 2M+ installs a week, parsing untrusted audio in production.

<p align="center">
  <a href="https://npmjs.org/package/audio-decode"><img src="https://img.shields.io/npm/dw/audio-decode?label=audio-decode&color=444" alt="audio-decode downloads"></a>
  <a href="https://npmjs.org/package/audio-buffer"><img src="https://img.shields.io/npm/dw/audio-buffer?label=audio-buffer&color=444" alt="audio-buffer downloads"></a>
  <a href="https://npmjs.org/package/audio-type"><img src="https://img.shields.io/npm/dw/audio-type?label=audio-type&color=444" alt="audio-type downloads"></a>
</p>

Sponsorship buys what a dependency needs: security response, new-runtime compat, verification kept current against the specs. Upstream is cheaper than a fork.

**[github.com/sponsors/audiojs →](https://github.com/sponsors/audiojs)**

<p align="center"><em>MIT keeps it free. Sponsors keep it alive.</em></p>
<p align="center"><img src="https://img.shields.io/badge/license-MIT-00a4b8" alt="MIT"></p>
