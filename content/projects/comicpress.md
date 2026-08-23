---
title: "Comicpress"
summary: "Cross-platform C++ application that converts and compresses digital comics for e-readers."
---

A cross-platform C++ GUI application that compresses and reformats digital
comics so they read well on e-readers and take up less storage. It reduces file
sizes by up to 80% while improving visual fidelity, and is built with Qt,
libVIPS, PDFium, and libarchive.

[Source on GitHub](https://github.com/amarz45/comicpress)

I started it to solve a problem I had: comic files were too large for my
e-reader and looked worse than they needed to. Finishing it meant learning image
processing I hadn't set out to learn, because the project required it.

{{< localvideo src="videos/demo.mp4" >}}

Official digital comic book files are designed for LCD displays: full colour,
arbitrary resolution. E-ink is the opposite: usually greyscale, often only 16
shades, fixed panel size. I realized those constraints are actually
opportunities. If a device's display is 1440×1920, every page can be downscaled
to exactly that ahead of time and quantized to a palette the screen can actually
render, with no visible quality loss. The pipeline I designed rotates two-page
spreads, removes page spines, scales, quantizes with Floyd–Steinberg dithering,
stretches contrast to span the full range, and re-encodes losslessly, since
quantization has already done the lossy work. The result is up to 80% smaller
files that also look better on an e-reader than the originals do.

There already existed a similar application called
[Kindle Comic Converter](https://github.com/ciromattia/kcc) (KCC). I designed
Comicpress to fix the flaws KCC has:

- Like KCC, Comicpress uses multiple processes to achieve parallelism. However,
  Comicpress uses several times less memory per job. On systems with low RAM (I
  used to have a laptop with only 8 GiB), this matters.
- KCC's graphical user interface is complex and very difficult to use. Comicpress
  is explicitly designed with a user-friendly interface from the beginning,
  despite how complex the underlying logic is.
- Comicpress has overall better quality, especially when converting from PDF.

The hardest part of writing Comicpress was parallelism. PDFium isn't
thread-safe, so I used separate worker processes instead of threads, which gave
me isolation without locking overhead and throughput that scales linearly with
worker count. I'm the sole developer: I designed the pipeline, wrote the
application, packaged it, and maintain it. It's published on Flathub and
available on Linux, with Windows support working and packaging in progress.

## What I'd do differently

Comicpress has no automated test suite. As the sole developer I checked output by
eye across a sample of files, which caught obvious regressions but would not
catch a subtle quality change in the quantization step. If I started again I'd
build a small corpus of reference pages and assert against expected properties in the output, because retrofitting tests onto a pipeline this
stateful is harder than writing them alongside it. Windows packaging is also
still unfinished: the application runs there, but I underestimated how much of
the remaining work is distribution rather than code.
