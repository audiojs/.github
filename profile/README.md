<h1 align="center">audiojs</h1>

<p align="center"><strong>Open Audio Stack</strong> — decode · process · analyse · synthesise, where your code runs.</p>

<p align="center">
  <a href="https://npmjs.org/package/audio-decode"><img src="https://img.shields.io/npm/dw/audio-decode?label=audio-decode&color=444" alt="audio-decode downloads"></a>
  <a href="https://npmjs.org/package/audio-buffer"><img src="https://img.shields.io/npm/dw/audio-buffer?label=audio-buffer&color=444" alt="audio-buffer downloads"></a>
  <a href="https://npmjs.org/package/audio-type"><img src="https://img.shields.io/npm/dw/audio-type?label=audio-type&color=444" alt="audio-type downloads"></a>
  <a href="https://github.com/audiojs/audio/actions/workflows/test.yml"><img src="https://github.com/audiojs/audio/actions/workflows/test.yml/badge.svg" alt="tests"></a>
  <img src="https://img.shields.io/badge/license-MIT-green" alt="MIT">
</p>

```js
import audio from 'audio'                                   // npm i audio

audio('raw.wav').trim(-30).normalize('podcast').fade(0.3, 0.5).save('clean.mp3')
let [lufs, bpm] = await audio('track.flac').stat(['loudness', 'bpm'])
```

```sh
audio raw.wav trim -30db normalize podcast fade 0.3s -0.5s save clean.mp3   # same engine, CLI
```

Browser, Node, workers, edge — no ffmpeg, no upload, no native deps.

## Atoms

Every algorithm is its own package: install one kernel (`@audio/dynamics-compressor`), a family ([dynamics](https://github.com/audiojs/dynamics) · [denoise](https://github.com/audiojs/denoise) · [eq](https://github.com/audiojs/eq) · [filter](https://github.com/audiojs/filter) · [reverb](https://github.com/audiojs/reverb) · [effect](https://github.com/audiojs/effect) · [shift](https://github.com/audiojs/shift) · [stretch](https://github.com/audiojs/stretch) · [spatial](https://github.com/audiojs/spatial) · [loudness](https://github.com/audiojs/loudness) · [pitch](https://github.com/audiojs/pitch) · [beat](https://github.com/audiojs/beat) · [mir](https://github.com/audiojs/mir) · [spectral](https://github.com/audiojs/spectral) · [synth](https://github.com/audiojs/synth) · [voice](https://github.com/audiojs/voice) · …), or let [`audio`](https://github.com/audiojs/audio) host them all — batch, streaming, AudioWorklet, CLI.

## Verified

Against the sources of truth, not against itself: loudness to EBU/BS.1770 test vectors · biquads to 1e-9 vs reference design · FM sidebands to Bessel tables · resamplers to measured alias floors · MIR to MIREX-class sets · measurement to Farina ESS round-trips. Deterministic: same input, same output, every runtime.

## Roadmap

The [audio.js contract](https://github.com/audiojs/compile/blob/main/CONTRACT.md) carries atoms beyond JS: [wam](https://github.com/audiojs/wam) runs them as Web Audio Modules / AudioWorklets today; [jz](https://github.com/dy/jz) compiles the same numeric kernels to lean GC-free WASM; native plugin targets (VST3 · CLAP · AU · LV2) follow via [compile](https://github.com/audiojs/compile), with [host](https://github.com/audiojs/host) bringing native plugins the other way — into JS.

## Sponsor

**[github.com/sponsors/audiojs →](https://github.com/sponsors/audiojs)** — MIT forever; sponsorship funds the maintenance that keeps the stack coherent. Shipping on these packages? Upstream is cheaper than a fork.
