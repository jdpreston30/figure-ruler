# Figure Ruler

A tiny, self-contained tool for measuring positions and distances on figure PNGs —
built for placing floating legends and labels in cowplot/ggplot figures without
eyeballing pixels in Preview.

- **Coordinate readout in cowplot inches** (origin bottom-left) — the exact `x=` / `y=`
  you paste into `cowplot::draw_label()` / `draw_plot()`. Toggle to raw pixels.
- **Auto-snap to the nearest content edge** — magnetizes clicks to figure elements
  (works great on white backgrounds).
- **Two-point measurement** with copy-paste-ready Δx / Δy / distance — no more `+15/300`.
- Configurable canvas size (default 8.5 × 11 in). Coordinates are DPI-independent —
  derived from the canvas size and image pixels — so any render DPI (300, 600, …) gives
  the same inches; the effective DPI is shown for reference.

No build step, no dependencies — just a browser.

## Use

**Easiest:** double-click **`Figure Ruler.app`** — it opens the tool in your default
browser. Then click **Open PNG…** and pick a figure.

> Load images through **Open PNG…** (the file picker): edge-snap reads the pixels of
> files opened that way. The auto-loaded sample is display-only — snap activates once
> you Open a PNG.

**Measure:** click point A then click point B — or drag from A to B in one motion — to
draw a measured line. You get a dark-grey right triangle showing the **distance**
(hypotenuse) and the **Δx / Δy** legs, each labelled in your units; the sidebar has a
**copy** button for every value (and "copy A/B as `x=, y=`"). Drag an existing A or B to
re-adjust it; a third click starts a fresh measurement.

**Snapping:** points magnetise to the nearest figure edge ("snap to edges" on). If a
dragged point has nothing to snap to, it aligns horizontally/vertically with its partner
(Δx→0 or Δy→0). Uncheck **snap to edges** for fully freehand placement. Tune the radius /
white-threshold sliders if snapping feels too eager or too weak.

**Navigate:** scroll (or the **+ / −** buttons) = zoom at the cursor · **right-drag** =
pan · the **✋ Hand** button (or double-click the figure) toggles a pan mode · **Fit**
resets the view.

You can also just open `figure_ruler.html` in any browser directly — the `.app` is only a
convenience launcher.

## Install on a new Mac

Recommended (this preserves the launcher's executable bit):

```bash
git clone https://github.com/jdpreston30/figure-ruler.git
```

Then double-click **`Figure Ruler.app`**. It's an unsigned local launcher (a shell
script), so the first time macOS may say it's from an unidentified developer — just
**right-click it → Open → Open** once, and it launches normally after that. No
dependencies, no build step.

> Prefer not to use git? Download the repo as a ZIP from GitHub instead — but a ZIP can
> strip the launcher's executable bit, so if double-clicking the app does nothing, run
> this once:
> ```bash
> chmod +x "figure-ruler/Figure Ruler.app/Contents/MacOS/launch"
> ```
> (Or skip the `.app` entirely and just open `figure_ruler.html` in your browser.)
