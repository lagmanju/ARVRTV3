# Fit Check V3: Size by Product

Revised V2 interaction for the SI 559 AR/VR Redesign. The only change from V2 is how TV size is chosen.

## What changed

| V2 | V3 |
| --- | --- |
| One 55" TV, free pinch scaling (`can-scale`) | Scrollable carousel of real sizes (43" to 85"); the TV snaps to each true-scale size as you scroll |
| No measurements | Live width and height callouts pinned to the TV, plus inches, cm and a suggested seating distance |
| No way to compare | "Compare sizes" shows outlines of the next size up and down |
| No feedback on change | Size readout bumps on each step; short vibration on Android |

Pinch scaling is turned off on purpose (`ar-scale="fixed"`), so every size you see is a product you could buy.

## Upload to GitHub Pages

1. Copy `V3/index.html` into your repo (either replace the old `index.html` or add a `v3/` folder).
2. Commit and push. Pages redeploys in about a minute.
3. Open the Pages URL on your phone (add `/v3/` if you used a folder).

No other files are needed. The TV models are generated in the browser, so `Box.glb` is not used.

## How it behaves on each phone

- **Android (Chrome):** best experience. AR runs in WebXR, so the carousel, measurements and outlines stay on screen inside AR, and scrolling changes the TV live without re-placing it. Record your demo video here if you can.
- **iPhone (Safari):** Apple's Quick Look does not allow web UI in AR. You pick the size and outlines in the 3D preview first, then tap "View in your room" to place that size. Scaling is still locked.
- **Laptop:** 3D preview and carousel work; the AR button is disabled.

## Guideline mapping (for the critique slide)

Guideline focus: keep virtual objects at realistic, real-world scale when they represent real products (Google ARCore design guidelines and Apple HIG, Augmented Reality). Pull the exact line and link for your references slide.

- V2 broke it: free pinch let users view a TV size that does not exist.
- V3 follows it: size only changes by choosing a real product, and measurements make the scale explicit.

## Peer feedback addressed

- Nicholas: multiple preset sizes, snapping steps, silhouettes of other sizes, step feedback (kept the snapping, replaced pinch with scrolling)
- Sam and Kartika: live dimension callouts in the AR view
- Cody and Kartika: side by side comparison, partly, through neighbor outlines
- Not addressed (future work): rotation, height from floor, room scan suggestions

## Compromises

- Prices and specs are mock data.
- Every TV is a 16:9 screen with a fixed 0.4" bezel and 1.2" depth, not exact per-model dimensions.
- Height from floor is not shown; the web AR library does not expose the floor position while placing on a wall.
- Seating distance uses a common 4K rule of thumb (1.0 to 1.5 times the diagonal).
- The iPhone path uses a hidden second viewer to launch Quick Look; test it on your device before recording.
