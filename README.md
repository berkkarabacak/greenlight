# GreenLight — test your mic, speaker & camera

A tiny, self-contained web app to check that your **microphone, speakers and
camera** work — right in the browser, before a call. No install, no accounts,
nothing leaves your device: all capture and playback happen locally in the page.

**Live:** https://berkkarabacak.com/greenlight/

## What it does

- **Microphone** — shows a live input meter, records a short clip and plays it
  back so you can hear yourself (mic "repeater").
- **Speakers** — plays a test tone so you can confirm output.
- **Camera** — shows a live preview to confirm the right camera is selected.
- **Compare devices** (`compare.html`) — record from two different
  microphones/speakers side by side and A/B them.

It ends on a plain-language verdict ("You're good to go" / "A couple of things
need a look") instead of raw technical output.

## Tech

Two static HTML files, each with inline CSS + JS — no build step, no
dependencies, no network calls. Uses the standard browser media APIs
(`getUserMedia`, `AudioContext`/`AnalyserNode`, `MediaRecorder`).

- `index.html` — the main mic / speaker / camera test.
- `compare.html` — the two-device comparison tool.

Because it uses camera/microphone capture, browsers require a **secure context**
(HTTPS or `localhost`).

## Run locally

```bash
python -m http.server 8091
# then open http://localhost:8091
```

## License

MIT
