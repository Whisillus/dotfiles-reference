# Repository Notes

## Workspace
- This is a CUDA/GPU reference workspace for locating valuable information, not one buildable project.
- `repo/` contains git submodules from `.gitmodules`; `docs/` and `article/` contain local reference material.
- Some submodules may be registered but uninitialized; check `git submodule status --recursive` before assuming sources are present.
- Use this tree for static inspection of source, docs, examples, tests, and metadata; do not build, install, test, benchmark, or run project scripts here unless explicitly asked.
- Repos, docs, PDFs, articles, and generated sources may be too large for the context window; use targeted search and read focused slices instead of loading whole files or trees.
- Follow nested agent guidance when present, especially `repo/flash-attention/AGENTS.md`.

## Local References
- `docs/`: Local documentation snapshots; inspect versioned folders before citing API, PTX, CUDA, or tuning details.
- `article/`: Papers, articles, and supporting notes; use them for background and cross-checking claims.

## Submodules
- `repo/cutlass`: Header-first CUDA templates and CuTe; inspect `include/`, examples, and docs for architecture patterns.
- `repo/flash-attention`: FA2 lives in top-level `csrc/`, FA3 in `hopper/`, and FA4 in `flash_attn/cute/`; defer to its nested `AGENTS.md` for installs, tests, and formatting.
- `repo/FlashMLA`: SM90/SM100 MLA kernels; inspect kernels, tests, and `csrc/cutlass` integration notes.
- `repo/DeepGEMM`: DeepSeek GEMM kernels; inspect generated kernels, JIT/build metadata, tests, and tuning notes for implementation details.
- `repo/DeepEP`: DeepSeek expert-parallel communication kernels; inspect runtime code, tests, and dispatch/configuration notes.
- `repo/flashinfer`: FlashInfer kernels and runtime support; inspect local files before citing APIs because the checkout may lag upstream.
- `repo/SageAttention`: SageAttention CUDA attention kernels; inspect source, kernels, setup metadata, and docs for implementation details.
- `repo/MSA`: MiniMax SM100 dense and sparse attention kernels; inspect the csrc JIT, CuTe DSL, sparse top-k, and paged low-precision paths.
- `repo/FlashKDA`: CUTLASS-based Kimi Delta Attention kernels for SM90+; inspect kernel code, architecture notes, FLA integration, and tests.
- `repo/flash-linear-attention`: Linear/sparse attention, state-space, and hybrid sequence-model kernels; follow its nested `AGENTS.md` and repo-local skills.
- `repo/TransformerEngine`: PyTorch/JAX/C++ FP8, MXFP8, and NVFP4 transformer kernels; inspect source, docs, env-var docs, and QA scripts for behavior.
- `repo/TileRT`: Public TileRT reference tree; inspect docs and examples, but do not build it in this workspace.
- `repo/CuAssembler`: Python CUDA assembly tooling; inspect parsers, assemblers, tests, and docs; `hnvcc` is Linux-only.
- `repo/sass-king`: Evidence-driven SASS research; preserve `[OBS]`, `[INF]`, `[HYP]`, `[RES]`, and `[GAP]` tags in technical claims.
- `repo/gpu-benches`: Registered benchmark submodule; may be empty until initialized.
- `repo/cuda_micro_bench`: CUDA microbenchmark reference; inspect benchmarks and scripts, but do not run them in this workspace unless asked.
- `repo/NVIDIA-Hopper-Benchmark`: Hopper benchmark reference; treat scripts as hardware-specific and inspect requirements before running.
