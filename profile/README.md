<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Braveheart-Chess/braveheart-branding/main/banner-dark.png">
    <img src="https://raw.githubusercontent.com/Braveheart-Chess/braveheart-branding/main/banner-light.png" alt="Braveheart" width="640">
  </picture><br>
  <sub>Logo © the artist, used under licence. All rights reserved; not covered by this repository's licence (<a href="https://github.com/Braveheart-Chess/braveheart-branding#licence">details</a>).</sub>
</p>

<p align="center">
  <a href="https://github.com/Braveheart-Chess/braveheart/releases/latest"><img src="https://img.shields.io/github/v/release/Braveheart-Chess/braveheart?label=engine&color=cf9031" alt="Latest engine release"></a>
  <a href="https://lichess.org/@/jwallace145"><img src="https://img.shields.io/badge/play%20it-on%20Lichess-3981ef" alt="Play it on Lichess"></a>
  <a href="https://github.com/Braveheart-Chess/braveheart/blob/main/LICENSE"><img src="https://img.shields.io/badge/code-MIT-c0281b" alt="Code: MIT"></a>
</p>

**Braveheart** is a single-threaded UCI chess engine in Rust: alpha-beta search
and an NNUE trained on its own self-play. Every change is justified by a
number: perft for correctness, bench for speed, stats for search efficiency,
and SPRT for Elo.

The name is the film about William Wallace, and Scotland's own chess opening
is the Scotch: open and aggressive. The mascot follows suit.

## Repositories

| Repository | What it is |
| --- | --- |
| [**braveheart**](https://github.com/Braveheart-Chess/braveheart) | The engine: search, evaluation, the embedded NNUE net, and the perft, bench and SPRT tooling that measures every change. **Start here.** |
| [braveheart-selfplay](https://github.com/Braveheart-Chess/braveheart-selfplay) | The self-play dataset: billions of positions labelled by the engine itself, and how they are generated, relabelled and audited. |
| [braveheart-trainer](https://github.com/Braveheart-Chess/braveheart-trainer) | Trains the NNUE nets on those positions, and records every net it has made. |
| [braveheart-lichess-bot](https://github.com/Braveheart-Chess/braveheart-lichess-bot) | The Lichess bot: play the engine, or watch it play. |
| [homebrew-tap](https://github.com/Braveheart-Chess/homebrew-tap) | The Homebrew tap: install the engine on macOS or Linux with one command. |
| [braveheart-databricks](https://github.com/Braveheart-Chess/braveheart-databricks) | A Databricks workspace for exploring the training data. |
| [braveheart-branding](https://github.com/Braveheart-Chess/braveheart-branding) | The logo, the avatar, the favicons, this banner, and the scripts that make them. |

## Quickstart

On macOS or Linux, one command installs the engine from the
[Homebrew tap](https://github.com/Braveheart-Chess/homebrew-tap), with its
NNUE net built in:

```sh
brew install braveheart-chess/tap/braveheart
```

Then try it from the terminal:

```sh
braveheart --version          # the release you installed
braveheart perft --depth 5    # 4,865,609: every position five half-moves from the start

# Ask for its reply to the Scotch (1. e4 e5 2. Nf3 Nc6 3. d4), with two seconds to think
printf 'position startpos moves e2e4 e7e5 g1f3 b8c6 d2d4\ngo movetime 2000\n' | braveheart
```

The last command prints the engine's search as it deepens and ends with its
choice, such as `bestmove e5d4`. To play against it, add `braveheart` as a
UCI engine in a GUI such as [Cute Chess](https://github.com/cutechess/cutechess)
or [En Croissant](https://encroissant.org/), using the path `which braveheart`
prints. The [tap's README](https://github.com/Braveheart-Chess/homebrew-tap#try-it)
explains each command, the engine's options and the supported platforms. No
Homebrew? Download a binary (macOS or x86-64 Linux) from the
[latest release](https://github.com/Braveheart-Chess/braveheart/releases/latest).

## Play it on Lichess

Challenge [jwallace145](https://lichess.org/@/jwallace145), online 08:00 to
20:00 UTC every day, or watch its games live on its profile.
