# Tmonk Tectdist Tap -> tectdist

Homebrew tap for [tectdist](https://github.com/tmonk/tectdist) — a
Standard-TeX-compatible TeX distribution backed by
[Tectonic](https://tectonic-typesetting.github.io/).

| Tap | Formula |
|-----|---------|
| `tmonk/tectdist` | `tectdist` |

The `tectdist` formula installs the built single-file zipapp plus a symlink
farm of the classic TeX tool names (`pdflatex`, `latexmk`, `kpsewhich`,
`biber`, …), all dispatching to the single `tectdist` executable.  It
declares `tectonic`, `ghostscript`, `poppler` and `qpdf` as dependencies and
never shadows their binaries.

## How do I install?

Tap and install:

```sh
brew tap tmonk/tectdist
brew install tectdist
```

Or install directly without a separate `brew tap` step:

```sh
brew install tmonk/tectdist/tectdist
```

Or, in a `brew bundle` `Brewfile`:

```ruby
tap "tmonk/tectdist"
brew "tectdist"
```

If another TeX installation already provides some of the farm names, run
`brew link --overwrite tectdist`.  If this is your first time using a
non-official tap and Homebrew asks for explicit trust:

```sh
brew trust --formula tmonk/tectdist/tectdist
```

## Documentation

`brew help`, `man brew` or check [Homebrew's documentation](https://docs.brew.sh).
