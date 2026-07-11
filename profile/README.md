<h1 align="center">audiojs</h1>

<p align="center"><em>Sound, engineered — decode · process · analyse · synthesise.</em><br>
JavaScript today, WASM underway, and the same atoms compiling toward native plugin targets<br>(VST3 · CLAP · AU · LV2 · WAM) via the <a href="https://github.com/audiojs/compile/blob/main/CONTRACT.md">audio.js contract</a>.</p>

<p align="center">
  <a href="https://npmjs.org/package/audio-decode"><img src="https://img.shields.io/npm/dw/audio-decode?label=audio-decode&color=444" alt="audio-decode downloads"></a>
  <a href="https://npmjs.org/package/audio-buffer"><img src="https://img.shields.io/npm/dw/audio-buffer?label=audio-buffer&color=444" alt="audio-buffer downloads"></a>
  <a href="https://npmjs.org/package/audio-type"><img src="https://img.shields.io/npm/dw/audio-type?label=audio-type&color=444" alt="audio-type downloads"></a>
  <a href="https://github.com/audiojs/audio/actions/workflows/test.yml"><img src="https://github.com/audiojs/audio/actions/workflows/test.yml/badge.svg" alt="tests"></a>
  <img src="https://img.shields.io/badge/license-MIT-green" alt="MIT">
</p>

```js
import audio from 'audio'
audio('raw.wav').trim(-30).normalize('podcast').fade(0.3, 0.5).save('clean.mp3')
```

Every algorithm is an installable atom (`@audio/*`), every family an umbrella, and the [`audio`](https://github.com/audiojs/audio) engine hosts them all — batch, streaming, AudioWorklet, CLI.

| | |
|---|---|
| **decode / encode** | [decode](https://github.com/audiojs/decode) · [encode](https://github.com/audiojs/encode) · [pcm-convert](https://github.com/audiojs/pcm-convert) · [audio-buffer](https://github.com/audiojs/audio-buffer) |
| **process** | [dynamics](https://github.com/audiojs/dynamics) · [denoise](https://github.com/audiojs/denoise) · [eq](https://github.com/audiojs/eq) · [filter](https://github.com/audiojs/filter) · [reverb](https://github.com/audiojs/reverb) · [effect](https://github.com/audiojs/effect) · [shift](https://github.com/audiojs/shift) · [stretch](https://github.com/audiojs/stretch) · [spatial](https://github.com/audiojs/spatial) · [saturate](https://github.com/audiojs/saturate) · [resample](https://github.com/audiojs/resample) · [defeedback](https://github.com/audiojs/defeedback) |
| **analyse** | [loudness](https://github.com/audiojs/loudness) · [pitch](https://github.com/audiojs/pitch) · [beat](https://github.com/audiojs/beat) · [mir](https://github.com/audiojs/mir) · [spectral](https://github.com/audiojs/spectral) · [measure](https://github.com/audiojs/measure) |
| **synthesise** | [synth](https://github.com/audiojs/synth) · [voice](https://github.com/audiojs/voice) · [midi](https://github.com/audiojs/midi) · [sinusoidal](https://github.com/audiojs/sinusoidal) |
| **plug** | [compile](https://github.com/audiojs/compile) · [wam](https://github.com/audiojs/wam) · [host](https://github.com/audiojs/host) — JS in both directions: atoms out to plugin hosts, native plugins in |

**Verified, not vibed** — atoms are paper-cited and differential-tested against the source of truth: loudness to EBU/BS.1770 test vectors, biquads to 1e-9 against reference design, FM sidebands to Bessel tables, resamplers to measured alias floors. Deterministic: same input, same output, every runtime.

**[Sponsor audiojs →](https://github.com/sponsors/audiojs)** — algorithms stay MIT; sponsorship funds the maintenance that keeps them coherent. Shipping on these packages? Sponsoring the upstream is cheaper than owning a fork.
