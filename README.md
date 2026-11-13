# Blood Tracker

A simple phone web app that uses the rear camera to help you spot blood on leaves, grass and dirt when tracking a wounded animal. It's built for people with red-green colour deficiency.

- The live image is shown in **black and white**, and anything blood-coloured is painted in a **blinking cyan** with a ring around it. You never have to tell red from green yourself.
- **Tap the screen** and it names the colour under your finger (for example "RED", "brown", "GREEN") and says whether it matches blood.
- A beep and vibration go off when a new spot comes into view.
- It **works offline** after you've opened it once with signal, and it can be added to your home screen.

## Controls

| Control | What it does |
|---|---|
| Sensitivity | Raise it to catch faint or old blood; lower it if red leaves trigger it. |
| View | **Gray** (default), **Color** (normal image plus markers), or **Mask** (black screen with only the hits; highest contrast). |
| Dried | Widens detection toward the dark red-brown of older, dried blood. It also adds more false hits on brown leaves. |
| Mark | Highlight colour: Cyan, Yellow, Blue or White. All are easy to see with red-green colour deficiency. |
| Light | Turns on the phone's flashlight (Android Chrome; iPhones don't allow this from a web page). |
| Pause | Freezes the frame so you can tap around and check colours. |

## Tips in the field

- Hold the phone 1–2 m above the ground and sweep slowly. Small drops are only a few pixels wide at a distance.
- Check the undersides of leaves, grass stems at belly height, and logs the animal stepped over.
- At dusk or in heavy cover, turn on **Light**. Flash colour is more consistent than low light.
- Things that can trigger it: red maple, sumac or dogwood leaves, rose hips and red berries, rust, red flagging tape. Pause and tap a spot to check it, then look closer.
- Blaze orange, brown oak leaves, dry grass and dirt are filtered out at the default sensitivity.
- It's an aid, not a guarantee. Mark the last blood you found, and grid-search from there.

## Running it

Camera access needs **https**. The easiest free host is GitHub Pages:

1. In the repo on GitHub, go to **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**, pick the branch and the `/ (root)` folder, then save.
3. Open the URL it gives you on your phone, tap **Start camera**, and allow camera access.
4. Use **Add to Home Screen** (or Chrome's **Install app**) so it opens full-screen and works without signal.

Local testing on a computer: `python3 -m http.server` in this folder, then open `http://localhost:8000` (localhost counts as secure).

## Files

- `index.html`: the whole app (camera, detection, UI)
- `sw.js`: offline cache
- `manifest.json`, `icon.svg`: home-screen install
