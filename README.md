# Flappy Bird -- 8-Bit Arcade Edition

A retro-styled Flappy Bird clone built entirely with vanilla HTML, CSS, and JavaScript. The game runs in any modern browser with no external dependencies, frameworks, or build tools required. Everything lives in a single self-contained HTML file.

---

## Description

This is a browser-based arcade game inspired by the original Flappy Bird. The player controls a pixel-art bird that must navigate through an endless series of pipes by tapping or pressing a key to flap. The game features a hand-drawn pixel aesthetic, synthesized 8-bit sound effects, and adaptive layouts that work across desktop monitors and mobile phones.

The project was built as a single-file web application to demonstrate what can be achieved with the HTML5 Canvas API, the Web Audio API, and plain JavaScript -- no libraries, no bundlers, no package managers.

---

## Features

- **Retro Pixel-Art Visuals** -- Custom 5x5 bitmap font, hand-coded bird and pipe sprites, parallax scrolling backgrounds, animated bushes, clouds, and ground textures. All graphics are drawn programmatically using `fillRect` calls on a canvas.

- **Day and Night Mode** -- A toggle button switches between a bright daytime palette and a dark nighttime palette with twinkling stars and a crescent moon. The transition is smooth (colors interpolate across frames). The user's preference is saved to `localStorage` and restored on reload.

- **Adaptive Resolution** -- The game detects screen orientation and switches between a landscape layout (480x270, optimized for desktop) and a portrait layout (216x384, optimized for phones). All game constants (gravity, jump velocity, pipe dimensions, gap size) are tuned separately for each mode.

- **Mobile Support** -- Touch input is fully supported. The viewport is locked to prevent pinch-zoom and pull-to-refresh. A touch guard prevents the common mobile bug where `touchstart` and `click` both fire from a single tap.

- **8-Bit Sound Effects** -- Jump chirps, score dings, collision noise, and a game-over melody are all synthesized at runtime using the Web Audio API with square-wave oscillators. No audio files are loaded.

- **Score Tracking** -- The current score is displayed during gameplay. The best score is persisted to `localStorage` and shown on the start and game over screens.

- **Rank System** -- After each game, the player receives a letter rank (S, A, B, C, or D) based on their score.

- **Grace Period** -- A brief invincibility window at the start of each round prevents unfair instant deaths. The first pipe spawn is also delayed to give the player time to orient.

- **Screen Shake** -- A short camera shake effect fires on collision for tactile feedback.

- **Particle Trail** -- Small golden particles trail behind the bird during flight.

---

## Demo

> Live demo link: `https://your-username.github.io/flappy-bird/`

*(Replace with your actual deployment URL after hosting.)*

---

## Screenshots

### Start Screen

```
[ placeholder -- add a screenshot of the start screen here ]
```

### Gameplay (Day Mode)

```
[ placeholder -- add a screenshot or GIF of active gameplay in day mode ]
```

### Gameplay (Night Mode)

```
[ placeholder -- add a screenshot or GIF of active gameplay in night mode ]
```

### Game Over Screen

```
[ placeholder -- add a screenshot of the game over screen with score and rank ]
```

### Mobile (Portrait)

```
[ placeholder -- add a screenshot of the game running on a phone in portrait ]
```

---

## Controls

| Platform | Action         | Input                        |
|----------|----------------|------------------------------|
| Desktop  | Flap / Jump    | `Spacebar` or `Arrow Up`     |
| Desktop  | Flap / Jump    | Left-click anywhere          |
| Mobile   | Flap / Jump    | Tap anywhere on screen       |
| Any      | Toggle Theme   | Click/tap the icon (top-right corner) |
| Any      | Restart        | Tap or press Space on the game over screen |

---

## Technologies Used

| Technology             | Purpose                                      |
|------------------------|----------------------------------------------|
| HTML5                  | Document structure, single-file container     |
| CSS                    | Canvas positioning, theme button styling      |
| JavaScript (ES6+)     | All game logic, rendering, input handling     |
| Canvas API             | 2D rendering of all sprites, backgrounds, UI  |
| Web Audio API          | Runtime synthesis of 8-bit sound effects      |
| localStorage           | Persisting best score and theme preference    |

No external libraries, frameworks, CDNs, or images are used.

---

## How to Run

1. **Download** the project:

   ```bash
   git clone https://github.com/your-username/flappy-bird.git
   cd flappy-bird
   ```

2. **Open** the game in any modern browser:

   ```bash
   open index.html
   ```

   Or simply double-click `index.html` in your file manager.

3. **Play.** No server, no build step, no installation required.

> **Note:** Audio requires a user interaction (click or tap) before the browser will allow sound playback. This is handled automatically on the first flap.

---

## Project Structure

```
flappy-bird/
    index.html      # The entire game -- markup, styles, and logic in one file
    README.md        # This file
    LICENSE          # MIT License
```

The single-file architecture is intentional. All CSS is inlined in a `<style>` block and all JavaScript is inlined in a `<script>` block. This makes the project trivially portable: copy one file and it works anywhere.

### Code Organization (inside index.html)

The JavaScript is organized into clearly commented sections:

| Section                | Description                                        |
|------------------------|----------------------------------------------------|
| Adaptive Resolution    | Detects portrait vs landscape, sets game constants  |
| Palettes               | Day and night color definitions, interpolation      |
| Pixel Font             | 5x5 bitmap glyph definitions and text renderer      |
| Audio Engine           | Web Audio synthesis for jump, score, hit, game over  |
| Game Constants         | Physics, pipe dimensions, spawn rates per layout     |
| Bird                   | Sprite drawing, physics update, flap mechanics       |
| Pipes                  | Spawning, drawing with caps and rivets, collision    |
| Background             | Sky, stars, sun/moon, clouds, parallax hills, bushes |
| Ground                 | Scrolling grass and dirt with texture details         |
| Screens                | Start screen, game over screen with rank system      |
| Main Loop              | `requestAnimationFrame` loop tying everything together |

---

## Future Improvements

The following features could be added to extend the project:

- **Difficulty Progression** -- Gradually increase pipe speed and reduce gap size as the score climbs, using asymptotic curves so difficulty never spikes.

- **Leaderboard** -- Store top scores with player initials, displayed on the start screen. Could use `localStorage` for local play or a simple backend for global scores.

- **Additional Themes** -- Sunset, underwater, space, or seasonal palettes beyond the current day/night toggle.

- **Power-Ups** -- Temporary slow-motion, shield, or score multiplier items that appear between pipes.

- **Pause Menu** -- Allow pausing mid-game with a resume option.

- **Accessibility** -- Keyboard-only navigation for menus, screen reader announcements for score changes, reduced-motion option to disable particles and screen shake.

- **PWA Support** -- Add a service worker and manifest to make the game installable as a standalone app on mobile home screens.

- **Multiplayer** -- Split-screen or networked two-player mode where both players navigate the same pipe sequence.

---

## Author

**Your Name**

- GitHub: [github.com/your-username](https://github.com/your-username)
- Website: [your-website.com](https://your-website.com)

*(Replace with your actual information.)*

---

## License

This project is licensed under the **MIT License**.

```
MIT License

Copyright (c) 2025 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

Built with plain HTML, CSS, and JavaScript. No dependencies. Just open and play.
