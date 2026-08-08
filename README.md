# tectdist

[tectdist](https://github.com/tmonk/tectdist) is a Standard-TeX-compatible
TeX distribution backed by [Tectonic](https://tectonic-typesetting.github.io/).

This tap (`tmonk/brew` → [github.com/tmonk/homebrew-brew](https://github.com/tmonk/homebrew-brew))
ships the `tectdist` formula: it installs the built single-file zipapp, a
symlink farm of the classic TeX tool names (`pdflatex`, `latexmk`,
`kpsewhich`, …) dispatching to the single `tectdist` executable, and the
**real `biber` 2.17 built from source** (the plk/biber v2.17 source + 119
sha256-pinned CPAN module resources, mirroring homebrew-core's own biber
formula) — so biblatex works out of the box on every platform, with no extra
packages and no prebuilt binaries.  It declares `tectonic`, `ghostscript`,
`poppler`, `qpdf`, `perl`, `libxml2`, `libxslt` and `openssl@3` as
dependencies and never shadows their binaries.  **Prebuilt bottles** are
published (see the project README, "Installation"): installs pour in
seconds; from-source builds are the fallback (measured 2m43s cold on an
M-class Mac).

## Version pairing

Each tectdist release is one matched unit and declares a specific tectonic
pairing (enforced at RUNTIME by the software itself — every `tectdist`
invocation fails fast with instructions if brew's tectonic moves, and
`tectdist doctor` prints the full report).  This release: **tectonic 0.17.x
→ biblatex 3.17 → biber 2.17**.  Homebrew's core `biber` (2.21) is NOT
compatible with that biblatex — the bundled one is the one to use.  A weekly
GitHub Actions watcher opens an issue when brew's tectonic moves, so the
matched next release ships before users hit a mismatch on `brew upgrade`.

## How do I install?

Tap and install:

```sh
brew tap tmonk/brew
brew install tectdist
```

Or install directly without a separate `brew tap` step:

```sh
brew install tmonk/brew/tectdist
```

Or, in a `brew bundle` `Brewfile`:

```ruby
tap "tmonk/brew"
brew "tectdist"
```

If another TeX installation already provides some of the farm names, run
`brew link --overwrite tectdist`.  If this is your first time using a
non-official tap and Homebrew asks for explicit trust:

```sh
brew trust --formula tmonk/brew/tectdist
```

## Documentation

`brew help`, `man brew` or check [Homebrew's documentation](https://docs.brew.sh).
