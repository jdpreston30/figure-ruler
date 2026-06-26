# Figure Ruler

A tiny, self-contained tool for measuring positions and distances on figure PNGs —
built for placing floating legends and labels in cowplot/ggplot figures without
eyeballing pixels in Preview.

- **Coordinate readout in cowplot inches** (origin bottom-left) — the exact `x=` / `y=`
  you paste into `cowplot::draw_label()` / `draw_plot()`. Toggle to raw pixels.
- **Auto-snap to the nearest content edge** — magnetizes clicks to figure elements
  (works great on white backgrounds).
- **Two-point measurement** with copy-paste-ready Δx / Δy / distance — no more `+15/300`.
- Configurable canvas size (default 8.5 × 11 in) and DPI (default 300).

No build step, no dependencies — just a browser.

## Use

**Easiest:** double-click **`Figure Ruler.app`** — it opens the tool in your default
browser. Then click **Open PNG…** and pick a figure.

> Load images through **Open PNG…** (the file picker): edge-snap reads the pixels of
> files opened that way. The auto-loaded sample is display-only — snap activates once
> you Open a PNG.

**Controls:** scroll = zoom (at cursor) · Space + drag = pan · click = drop point A
then B · a 3rd click starts over. Copy any value with its **copy** button, or grab
A/B straight as `x=, y=`.

You can also just open `figure_ruler.html` in any browser directly — the `.app` is only
a convenience launcher.

## Install on another Mac

```bash
git clone https://github.com/jdpreston30/figure-ruler.git
```

Then double-click `Figure Ruler.app` (or open `figure_ruler.html` directly). The `.app`
is an unsigned local launcher (a shell script) — if macOS blocks the first launch,
right-click it → **Open** once.
