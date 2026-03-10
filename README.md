<p align="center">
  <img src="https://avatars.githubusercontent.com/u/209633456?v=4" width="160" alt="RedTail Indicators Logo"/>
</p>

<h1 align="center">Sessions VP with Previous Session VP & Opens</h1>

<p align="center">
  <b>A dual-session volume profile indicator for NinjaTrader 8.</b><br>
  Builds volume profiles for the current and previous session, overlays them for comparison, and plots daily/weekly open levels.
</p>

---

## Credit

Original TradingView Pine Script by **[@notprofessorgreen](https://twitter.com/notprofgreen)** (lucymatos). NinjaTrader 8 conversion by **[@_hawkeye_13](https://twitter.com/_hawkeye_13)** (RedTail Indicators).

---

## Overview

This indicator runs two independent volume profile engines side by side — one for the current session and one for the previous session. When a session completes, its volume profile is snapshotted and overlaid onto the next session's price range so you can visually compare the current session's developing volume distribution against where volume concentrated in the prior session. On top of the dual profiles, it plots 6 PM ET daily open and weekly open levels, and can draw forex session range boxes for Tokyo, London, and New York.

---

## Session Types

Both the current and previous session types are independently configurable. You can mix and match — for example, a Daily current profile with a Weekly previous profile.

- **Tokyo** — Forex session (UTC-based detection)
- **London** — Forex session (7:00–16:00 UTC)
- **New York** — Forex session (13:00–22:00 UTC)
- **Daily** — Resets on each new trading day
- **Weekly** — Resets on each new week
- **Monthly** — Resets on each new month
- **Quarterly** — Resets at the start of each quarter
- **Yearly** — Resets on each new year

---

## Current Session Profile

A live-updating volume profile that builds as the session progresses.

- **Volume Profile Histogram** — Configurable resolution (5–100 rows), with up/down volume separation
- **POC (Point of Control)** — Highest volume row, drawn as a horizontal line across the session
- **VAH/VAL (Value Area High/Low)** — Configurable Value Area percentage (default: 70%)
- **Value Area Box** — Optional filled rectangle between VAH and VAL
- **Session Box** — Dashed boundary rectangle around the session's full high/low range with background fill
- **Session Label** — Session type name displayed above the box
- **Live Zone** — Updates in real time on each bar close

---

## Previous Session Profile

When the previous session type's period completes, its volume profile is snapshotted and preserved.

**Overlay Mode** — The snapshotted previous session's volume profile is redrawn within the current session's time range, allowing you to see where last session's volume concentrated relative to where today's price is trading. The previous profile renders with independent colors and opacity so you can distinguish it from the current session's profile.

**Extended Levels** — The previous session's POC, VAH, and VAL extend forward as dashed lines to the current bar, acting as reference levels throughout the current session.

---

## Volume Bar Modes

Three rendering modes for the volume histogram bars, independently configurable for current and previous sessions:

- **Mode 1** — Up volume (green) only
- **Mode 2** — Up + down volume stacked side by side (default)
- **Mode 3** — Up volume extends right, down volume extends left

---

## Forex Session Boxes

Optional session range boxes for Tokyo, London, and New York forex sessions. Each box draws the session's high/low range as a dashed rectangle with fill and a centered label. Useful for forex and futures traders who track global session ranges.

---

## Open Levels

**6 PM ET Daily Open** — The opening price of the first bar at or after 6:00 PM Eastern Time, drawn as a horizontal line extending to the current bar. Marks the start of the futures daily session.

**Weekly Open** — The opening price of the first bar at or after 6:00 PM ET on Sunday, drawn as a horizontal line extending to the current bar. Marks the weekly session start.

Both levels have configurable color, width, line style (Solid/Dashed/Dotted), and optional text labels.

---

## Visual Settings

Every element has fully independent appearance controls across both current and previous sessions:

- Up/down volume colors and opacity
- POC color, width, and opacity
- VAH/VAL colors, widths, and opacity
- Value Area box color and opacity
- Session box color, width, and background opacity
- Customizable POC/VAH/VAL label text (prefixed "C:" for current, "P:" for previous)
- Label color

All rendering via SharpDX for performance.

---

## Installation

1. Download the `.cs` file from this repository
2. Copy the `.cs` to `Documents\NinjaTrader 8\bin\Custom\Indicators`
3. Open NinjaTrader (if not already open)
4. In Control Center, go to **New → NinjaScript Editor**
5. Expand the Indicator tree, find your new indicator, double-click to open it
6. At the top of the Editor window, click the **Compile** button
7. That's it!

---

## Part of the RedTail Indicators Suite

This indicator is part of the [RedTail Indicators](https://github.com/3astbeast/RedTailIndicators) collection — free NinjaTrader 8 tools built for futures traders who demand precision.

---

<p align="center">
  <a href="https://buymeacoffee.com/dmwyzlxstj">
    <img src="https://img.shields.io/badge/☕_Buy_Me_a_Coffee-Support_My_Work-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me a Coffee"/>
  </a>
</p>
