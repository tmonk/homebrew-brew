# tectdist

[tectdist](https://github.com/tmonk/tectdist) is a Standard-TeX-compatible
TeX distribution backed by [Tectonic](https://tectonic-typesetting.github.io/).

This tap (`tmonk/brew`) ships the `tectdist` formula — the classic TeX tool
names (`pdflatex`, `latexmk`, `kpsewhich`, `biber`, …) backed by Tectonic,
with biblatex working out of the box.

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
