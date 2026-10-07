# Is It Worth Automating?

An interactive calculator inspired by [xkcd #1205 "Is It Worth the Time?"](https://xkcd.com/1205/). It helps you decide whether automating or optimizing a task will actually pay off.

The whole app is a single static file, [`index.html`](index.html), with inline HTML, CSS and vanilla JavaScript. There is no build step and no dependencies.

## Features

- **Interactive xkcd-style table:** how much time you can spend automating a task, based on how often you do it (50×/day to 1×/year) and how much time each run saves (1 second to 1 day). Time values are editable, and rows can be added or removed.
- **Time horizon:** choose how many years to project (default: 5).
- **Calendar vs. workdays:** switch between calendar days (24h, 365 days/year) and workdays (default 8h, 220 days/year, both editable) for more realistic numbers.
- **Simulator:** enter your own case (frequency, current time per run, time after automating or time saved, time to build the automation) and get a clear verdict, plus time saved, net balance, break-even point and ROI.
- **Human-readable times:** results are shown as seconds, minutes, hours, days, weeks, months or years (e.g. "3.5 hours", "1.2 years").
- **Languages:** English and Portuguese (PT-PT), with a selector in the top-right corner.
- **Themes:** dark (default) and light, responsive down to mobile widths.

Settings are saved in your browser's `localStorage`; nothing is sent anywhere.

## Usage

Open `index.html` in a browser, or serve the folder locally:

```sh
python3 -m http.server 8000
```

then visit <http://localhost:8000>.

## Deploying to GitHub Pages

1. Push the repository to GitHub.
2. Go to **Settings → Pages**.
3. Select the `main` branch and the root folder, then save.

## How the numbers work

Time saved over the horizon is:

```
seconds saved per run × runs per year × years
```

In workday mode, a "day" is the configured number of hours, and runs per year use the configured days per year. The break-even point is always shown in calendar time.
