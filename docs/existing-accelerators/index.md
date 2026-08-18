---
layout: page
title: Existing Accelerators
parent: Documentation
nav_order: 4
has_children: true
---

# Existing Accelerators

{: .warning-title}
> Work in Progress
>
> This page is still a work in progress. More to come soon.

## Accelerator Tiles

| Tile | Type | Notes |
| --- | --- | --- |
| [ASA]({{ '/docs/existing-accelerators/asa' | relative_url }}) | Key/data associative accelerator | NoC glue is in-repo; the ASA compute core itself is an external black box |
| [Cache]({{ '/docs/existing-accelerators/cache' | relative_url }}) | Direct-mapped, write-back DRAM cache | Backs the mesh's shared-memory (`mPut`/`mGet`/`mLoad`/`mStore`) address space |
| [FFT]({{ '/docs/existing-accelerators/fft' | relative_url }}) | Fast Fourier Transform | Chisel-generated, single-precision floating point, multiple size/width configs |
| [FP]({{ '/docs/existing-accelerators/fp' | relative_url }}) | Floating point ALU | Adder, multiplier, divider, square root — one tile type each |
| [TSQR]({{ '/docs/existing-accelerators/tsqr' | relative_url }}) | Tall-Skinny QR decomposition | Chisel-generated Householder-QR pipeline; typically paired with FFT |
| [MoDIN]({{ '/docs/existing-accelerators/modin' | relative_url }}) | Spiking neuromorphic processor | Lives on the `modin` git branch, not `main` |

## Example Testcases

A few pages in this section document **testcases** rather than standalone accelerator hardware — they combine or stress-test the tiles above:

| Testcase | Demonstrates |
| --- | --- |
| [SCF]({{ '/docs/existing-accelerators/scf' | relative_url }}) | Combined FFT + TSQR pipeline across a 3x3 mesh |
| [Sweep]({{ '/docs/existing-accelerators/sweep' | relative_url }}) | FP adder tile inside a larger 8x8 mesh |
| [Demo]({{ '/docs/existing-accelerators/demo' | relative_url }}) | Software-only asynchronous triangular solver using the cache tile |
| [SNE]({{ '/docs/existing-accelerators/sne' | relative_url }}) | |

See the sub-pages for detailed specifications, NoC protocol details, and worked software examples for each.

<div style="display: flex; justify-content: space-between;">
  <a href="{{ '/docs/using-mosaic/adding-accelerators' | relative_url }}" class="btn btn-light mr-2"><i class="fa-solid fa-arrow-left-long"></i> Go back</a>
  <a href="{{ '/docs/existing-accelerators/asa' | relative_url }}" class="btn btn-light mr-2"><i class="fa-solid fa-arrow-right-long"></i> Continue</a>
</div>
