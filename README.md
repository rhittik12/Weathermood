# Moodscape

A quiet weather player for the browser.

Moodscape turns a blank browser tab into a small place to slow down. Choose rain, snow, or sun, then let the matching sound and atmosphere run in the background.

## What it does

- Rain on glass rendered with `raindrop-fx`
- Snowfall with adjustable flake count, size, and wind
- A sunny mode with warmth, light rays, and drifting particles
- Separate soundtracks for rain, snow, and sun
- Play/pause and volume controls
- A button for loading your own audio file
- Small controls for tuning each weather mode
- No build step and no app framework

## Run it locally

The page uses browser APIs and local audio files, so it is best opened through a small local server instead of double-clicking the HTML file.

With Python:

```bash
python -m http.server 8000
```

Then open <http://localhost:8000>.

You can also use the Live Server extension in VS Code.

## Deploy to Vercel

1. Rename `weather.html` to `index.html`.
2. Push `index.html` and the `audio` folder to GitHub.
3. Import the repository into Vercel.
4. Leave the framework preset as **Other**.
5. Leave the build command empty.
6. Deploy.

The site is static, so Vercel does not need a build process or server function.

## Project layout

```text
.
├── index.html
└── audio/
    ├── rain.mp3
    ├── snow.mp3
    └── sunny.mp3
```

The repository currently contains `weather.html`; the layout above shows the name it should have for deployment.

## Changing the page

Most of the experience lives in one file, `index.html` after renaming it.

- Change the visible title and subtitle near the center of the page.
- Change the weather labels in the `weatherText` object.
- Replace the files in `audio/` to use different sounds.
- Adjust the default weather settings in the controls near the top of the script.

The built-in background image is embedded directly in the HTML, so it does not need a separate image file.

## Notes

The rain effect loads `raindrop-fx` from jsDelivr and the page loads the Marcellus font from Google Fonts. The rain mode needs WebGL2; snow and sunny mode use regular canvas animation.

Browsers do not allow websites to start audio automatically. Visitors need to press the play button first.

Only publish audio you created yourself or have permission to distribute.

## License

No license has been chosen for this project yet. Add a license before inviting others to reuse the code or audio assets.
