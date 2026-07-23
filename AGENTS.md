# Repository Guidelines

## Project Structure & Module Organization

This is a CUDA/GPU reference workspace, not one buildable application. `repo/` contains independently maintained Git submodules, including CUTLASS, FlashAttention, FlashMLA, DeepGEMM, FlashInfer, TransformerEngine, and architecture or benchmark projects. `docs/` stores versioned CUDA and architecture documentation; check the versioned directory (for example, `docs/cuda-13-3/`) before citing an API or instruction. `article/` contains papers and background material. Root-level `gemm*.md` files are focused technical notes.

Some registered submodules may be uninitialized. Confirm availability before searching, and follow any nested `AGENTS.md`, README, or contribution guide within the project being inspected.

## Inspection, Build & Test Commands

There is no root build, test, or install command. This workspace is intended primarily for static inspection. Useful commands include:

```sh
git submodule status --recursive
rg -n "PipelineTmaAsync" repo/cutlass docs/
git diff --submodule=log
```

Do not build, install, benchmark, or run project scripts unless the task explicitly requires it. When execution is requested, use commands documented by the selected submodule and verify its CUDA toolkit, GPU architecture, and dependency requirements first. Treat benchmark scripts as hardware-specific.

## Coding Style & Naming Conventions

For root documentation, use concise Markdown headings, fenced code blocks with language tags, and repository-relative paths. Match nearby filename conventions and identify the CUDA, PTX, or architecture version behind technical claims. Keep changes narrowly scoped; do not reformat vendored or submodule code incidentally.

Inside a submodule, preserve project-specific language conventions, formatters, linters, and naming patterns. In `repo/sass-king`, retain evidence labels such as `[OBS]`, `[INF]`, `[HYP]`, `[RES]`, and `[GAP]`.

## Testing Guidelines

Documentation changes should be checked for valid paths, readable Markdown, and accurate code snippets or citations. Source changes must use the owning submodule test framework and naming conventions. Report any validation not run, especially when it requires NVIDIA hardware, a specific SM target, or a Linux-only tool such as CuAssembler `hnvcc`.

## Commit & Pull Request Guidelines

Root history uses short, imperative subjects such as `Add CUDA assembly submodules`, `Refresh reference submodules`, and `Ignore macOS metadata files`. Keep one logical change per commit. Pull requests should explain the reference or submodule changed, why it is useful, versions or commit pins involved, and validation performed. Link relevant issues or upstream sources; include screenshots only for rendered documentation or visual output.
