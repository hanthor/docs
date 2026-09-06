---
sidebar_position: 1
sidebar_label: "Ghostty"
status: stable
---

:::tip[Visual overview]
Prefer a visual tour? See the **[Ghostty overview →](/ghostty)** page.
:::

**[Ghostty](https://ghostty.org)** is a fast, feature-rich terminal by
Mitchell Hashimoto. It draws with the GPU, speaks the Kitty graphics
protocol, and ships a native GTK4 app on Linux.

TunaOS carries Ghostty on its Flatpak remote as a convenience. This is the
stock upstream terminal, with no TunaOS patches. CI rebuilds it every day
from `ghostty-org/ghostty:main`, so the remote tracks upstream within a
day.

:::info[Not a TunaOS project]
Ghostty belongs to [ghostty-org](https://github.com/ghostty-org/ghostty).
TunaOS only republishes it. Send Ghostty bugs upstream, never to the
TunaOS trackers.
:::

## ✨ Key features

* **🖥️ GPU acceleration** — the renderer draws on the GPU, with ligatures and fast scrollback.
* **🖼️ Kitty graphics protocol** — inline images in the terminal.
* **🪟 Splits and tabs** — native GTK4 and libadwaita, on Wayland and X11.
* **⌘ Command palette** — a fuzzy search over every Ghostty command.
* **🔗 OSC 8 hyperlinks** — clickable links, with no guesswork about what a link is.
* **📄 One config file** — every option lives in `~/.config/ghostty/config`.

## Installation

### Flatpak (TunaOS remote)

```bash
flatpak remote-add --if-not-exists tuna-os https://tunaos.org/flatpak/tuna-os.flatpakrepo
flatpak install tuna-os com.mitchellh.ghostty
```

Builds cover x86_64 and aarch64.

### Other sources

Ghostty also ships through its own channels. See the
[Ghostty download page](https://ghostty.org/download) for distro packages
and the macOS app.

## How the TunaOS build stays current

CI resolves the head of `ghostty-org/ghostty:main` every day at 05:00 UTC.
It then builds the app with the manifest and the package list from that
same commit. Nothing about the app comes from TunaOS, so an upstream
dependency bump needs no change here.

A run that finds no new commit stops in seconds. Each publish also pushes
a tag pinned to the upstream commit, which is how the next run knows what
it already built.

## BlueShell or Ghostty?

The remote carries both, and the app IDs differ, so you can install one or
both.

* Pick **Ghostty** for the stock terminal, exactly as upstream ships it.
* Pick **[BlueShell](/docs/blueshell)** for the same engine, with container tabs, profiles, and a preferences window on top.

## Links

* [ghostty.org](https://ghostty.org)
* [GitHub](https://github.com/ghostty-org/ghostty)
* [BlueShell](/docs/blueshell) — the TunaOS fork of this terminal
