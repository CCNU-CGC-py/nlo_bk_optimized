# nlobk-gpu

**GPU-accelerated solver for the NLO + NLL Balitsky–Kovchegov equation and NLO DIS cross sections**

[![arXiv](https://img.shields.io/badge/arXiv-2604.22332-b31b1b.svg)](https://arxiv.org/abs/2604.22332)
[![License](https://img.shields.io/badge/license-<LICENSE>-blue.svg)](LICENSE)
![CUDA](https://img.shields.io/badge/CUDA-<version>%2B-76B900.svg)

---

## Overview

`nlobk-gpu` is a high-performance GPU implementation of the next-to-leading order (NLO)
Balitsky–Kovchegov (BK) evolution equation with next-to-leading logarithmic (NLL)
resummations, together with the NLO computation of deep inelastic scattering (DIS)
structure functions and reduced cross sections.

The physics follows the formulation in
[arXiv:2604.22332](https://arxiv.org/abs/2604.22332). The numerical implementation is
derived from, and validated against, the original C++ code
[**hejajama/nlobk**](https://github.com/hejajama/nlobk).

The NLO BK kernel requires high-dimensional transverse-coordinate integrals at every
evolution step. That is the main computational bottleneck of the CPU implementation,
and this code moves those integrals onto the GPU.

Full NLO bk done under 30 s
