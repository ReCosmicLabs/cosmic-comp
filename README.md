# cosmic-comp (fork)

> **This is a fork of [pop-os/cosmic-comp](https://github.com/pop-os/cosmic-comp)**, the compositor of the
> COSMIC desktop by [System76](https://system76.com). All credit for the compositor itself goes to
> System76 and the upstream contributors. The license is unchanged: **GPL-3.0-only** (see `LICENSE`).

## Changes in this fork

Maintained by [ReCosmicLabs](https://github.com/ReCosmicLabs) for the
[dotfiles](https://github.com/eualexandrerrr/dotfiles) setup. Everything below is a modification of the
original work, as required by section 5 of the GPL.

- **No resize border on maximized windows.** The 10 px invisible resize border around a window
  (`RESIZE_BORDER`) is skipped while the window is maximized, so the pointer no longer turns into a
  resize arrow in the gap between a maximized window and the panel or the screen edge, and no resize
  grab can start from there. Server-side headers keep working. Files touched:
  `src/shell/element/window.rs` (`Focus::under`, `focus_under`) and `src/shell/element/stack.rs`
  (`focus_under`).

Build: `cargo build --release -p cosmic-comp`; the binary is `target/release/cosmic-comp`.
The dotfiles install it to `~/.local/bin`, ahead of the distro package; `cosmic-session` picks it up
on the next login.
