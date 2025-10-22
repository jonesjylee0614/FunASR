# Repository Guidelines

## Project Structure & Module Organization
- `funasr/` holds the core Python packages (models, datasets, CLI entry points).
- `runtime/` contains deployment assets for offline/real-time services; consult its `readme.md` before packaging.
- `examples/` and `docs/` offer runnable demos and extended guides referenced from the README.
- `tests/` mirrors the package layout; add new suites alongside the code they cover.
- Shared assets live in `fun_text_processing/`, `benchmarks/`, `model_zoo/`, and `web-pages/`.

## Build, Test, and Development Commands
- `python -m venv .venv && source .venv/bin/activate` provisions an isolated Python env for reliable torch/CUDA installs.
- `pip install -e .[test]` installs FunASR in editable mode with pytest, flake8, and black.
- `pytest tests` runs the full suite; narrow scope with `pytest tests/module/test_x.py`.
- `funasr ++model=paraformer-zh ++vad_model=fsmn-vad ++punc_model=ct-punc ++input=path.wav` performs a CLI smoke inference.

## Coding Style & Naming Conventions
- Python code follows PEP 8 with 4-space indentation; group imports as standard, third-party, local.
- Modules and functions use `snake_case`; classes use `CamelCase`; align Hydra config names with existing `paraformer_*` patterns.
- Run `black path/to/file.py` and `flake8 path/to/file.py` before pushing; CI expects formatter and linter clean runs.

## Testing Guidelines
- Extend `tests/` beside your feature and prefer descriptive names such as `test_paraformer_streaming_latency`.
- Cover CPU and CUDA branches when applicable; guard GPU-only assertions with `pytest.mark.cuda`.
- Maintain coverage for touched modules, using synthetic fixtures instead of bulky audio corpora.
- Run `pytest --maxfail=1 --disable-warnings -q` before submitting to surface regressions quickly.

## Commit & Pull Request Guidelines
- Craft commits in the imperative mood (“Add streaming diarization fallback”) and keep summaries under ~72 characters.
- Reference linked issues with `Fixes #123` when relevant and squash fixup commits before raising a PR.
- PRs must include a behavioural summary, testing evidence (command output or log excerpt), and visuals for runtime UI changes.
- Update documentation touchpoints (`README.md`, `runtime/readme.md`) when behaviour or APIs shift.

## Security & Configuration Tips
- Follow `SECURITY.md` for disclosures; never commit tokens or customer audio.
- Keep credentials and endpoints in environment variables or `.env` files ignored by Git.
- Confirm third-party model changes comply with the Model License Agreement before distributing binaries or weights.
