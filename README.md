# Multiplication Circle

An interactive visualizer of modular multiplication tables on a circle. Points are placed evenly around a circle, and each point is connected to another according to a multiplier — the same construction behind the classic "times-table cardioid" visualizations that circulate online (e.g. Mathologer's videos on the topic).

**[Live demo →](https://kathuman.github.io/multiplication-circle/)**


## How it works

- `n` points are placed evenly around a circle (the **divisions**).
- Each point `i` is connected by a straight line to point `(i × multiplier) mod n`.
- As you change `n` or the `multiplier`, the resulting web of lines forms different geometric patterns — cardioids, rose curves, moiré-like interference, and so on, depending on the relationship between `n` and the multiplier.
- The multiplier can be fractional; non-integer values interpolate between the two nearest points on the circle, producing smoother, more continuous-looking curves as you animate.

## Features

- **Divisions slider** — set `n` from 3 to 1000 (or type an exact value up to 5000).
- **Multiplier slider** — set the multiplier from 0 to 50 in steps of 0.1 (or type an exact value).
- **Auto-play** — animates the multiplier upward automatically. Adjustable speed (0.005 to 0.5 per frame), with an optional loop that wraps back to 0 once it hits the max instead of stopping.
- Line color shifts with the multiplier value for visual variety.
- Automatically thins out point markers and line opacity above 500 divisions to keep dense patterns legible instead of turning into visual noise.

## Usage

Nothing to install. Open `index.html` in any modern browser, or visit the live demo link above.

To run it locally:

```bash
git clone https://github.com/yourusername/multiplication-circle.git
cd multiplication-circle
open index.html   # or just double-click the file
```

## Tech

Single self-contained HTML file — inline CSS and vanilla JavaScript, no build step, no external dependencies. Rendering is done with the HTML5 Canvas API. Auto-play uses `requestAnimationFrame`, so animation speed is tied to your display's refresh rate rather than wall-clock time.

## Known limitations

- Canvas is a fixed 560×560px — no responsive resizing for mobile screens.
- Auto-play only moves the multiplier upward; to animate downward, type a negative value directly into the speed input (the slider itself is capped at a 0.005 minimum).
- Divisions above ~1000 will slow down rendering noticeably since every point-to-point line is recalculated and redrawn each frame.

## License

MIT — do whatever you want with it.

Daniel Sepulveda 2026 kathuman@gmail.com
