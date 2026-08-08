# tectdist

[tectdist](https://github.com/tmonk/tectdist) is a Standard-TeX-compatible
TeX distribution backed by [Tectonic](https://tectonic-typesetting.github.io/).

This tap (`tmonk/brew` → [github.com/tmonk/homebrew-brew](https://github.com/tmonk/homebrew-brew))
ships the `tectdist` formula: it installs the built single-file zipapp, a
symlink farm of the classic TeX tool names (`pdflatex`, `latexmk`,
`kpsewhich`, …) dispatching to the single `tectdist` executable, and the
**real bundled `biber` 2.17 binary** (official prebuilt binary, self-hosted
release asset) — so biblatex works out of the box, with no extra packages.
It declares `tectonic`, `ghostscript`, `poppler` and `qpdf` as dependencies
and never shadows their binaries.

## Version pairing

Each tectdist release is one matched unit and REQUIRES a specific tectonic
version at install time (asserted by the formula; a mismatched pair breaks
biblatex).  This release: **tectonic 0.17.x → biblatex 3.17 → biber 2.17**.
Homebrew's core `biber` (2.21) is NOT compatible with that biblatex — the
bundled one is the one to use.  A weekly GitHub Actions watcher opens an
issue when brew's tectonic moves, so the matched next release ships before
users hit a mismatch on `brew upgrade`.

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
