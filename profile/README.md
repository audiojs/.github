# audiojs

**Audio DSP for JavaScript — decode, process, analyse, synthesise. Everywhere JS runs.**

~330 packages, one convention: every algorithm is an installable atom (`@audio/*`), every family has an umbrella, and the [`audio`](https://github.com/audiojs/audio) engine hosts them all — batch, streaming, AudioWorklet, or compiled out to native plugin targets via the [audio.js contract](https://github.com/audiojs/compile/blob/main/CONTRACT.md).

- **2M+ installs a week** — [`audio-decode`](https://github.com/audiojs/decode), [`audio-buffer`](https://github.com/audiojs/audio-buffer), [`audio-type`](https://github.com/audiojs/audio-type) parse untrusted audio in production pipelines everywhere.
- **Reference implementations, verified** — BS.1770/EBU loudness, RBJ biquads differential-tested to 1e-9, Chowning FM matching Bessel tables, Farina ESS measurement, MIREX-class MIR. Paper-cited, deterministic, cross-runtime.
- **One maintainer, MIT forever.** Algorithms stay open; sponsorship funds the maintenance that keeps 330 packages coherent.

**[Sponsor audiojs →](https://github.com/sponsors/audiojs)** — or reach out for corporate support: you already depend on this; $2k/mo costs less than a week of building it in-house.
