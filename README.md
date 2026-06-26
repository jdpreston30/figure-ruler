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

No build step, no dependencies beyond a browser and `python3`.

## Use

**Easiest:** double-click **`Figure Ruler.app`**. It serves the tool locally and opens
it in your default browser, then you click **Open PNG…** and pick a figure.

Why a local server? Browsers block reading image pixels on `file://`, which would
disable edge-snap — serving over `http://localhost` avoids that.

**Controls:** scroll = zoom (at cursor) · Space + drag = pan · click = drop point A
then B · a 3rd click starts over. Copy any value with its **copy** button, or grab
A/B straight as `x=, y=`.

> You can also open `figure_ruler.html` directly, but snapping may be disabled by the
> browser's `file://` restriction unless you load via **Open PNG…**.

## Install on another Mac

```bash
git clone https://github.com/jdpreston30/figure-ruler.git
cd figure-ruler
```

Then double-click `Figure Ruler.app`. Requires `python3` (ships with the macOS
Command Line Tools). The `.app` is an unsigned local launcher (a shell script) — if
macOS blocks the first launch, right-click it → **Open** once.
