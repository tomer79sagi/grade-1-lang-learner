# Grade 1 Language Learner

A simple, mobile-friendly web app for first graders to learn words in Hebrew/English using the device camera and speech.

## Features
- Object detection to suggest Hebrew words and first letters
- Snapshot + quiz flow
- Text-to-speech (he-IL)
- Runs fully client-side (static `index.html`)

## Requirements
- Modern browser (mobile Safari/Chrome)
- HTTPS required for camera access on mobile (except localhost)

## Quick Start (Local)
```bash
# From repo root
python -m http.server 8000
# Then open in desktop browser:
#   http://localhost:8000/index.html
```

## Test on Mobile (Fastest)
Same Wi‑Fi, no HTTPS (camera may be blocked by browser policies):
```bash
hostname -I          # get your LAN IP, e.g. 192.168.1.50
python -m http.server 8000
# On phone: http://<LAN-IP>:8000/index.html
```

## Mobile over HTTPS (Recommended for camera)
Option A: Cloudflared
```bash
python -m http.server 8000
cloudflared tunnel --url http://localhost:8000
# Open the https URL printed by cloudflared on your phone
```

Option B: Ngrok
```bash
python -m http.server 8000
ngrok http 8000
# Open the https URL printed by ngrok on your phone
```

## Virtual Environment Tips
```bash
# Create venv with pip included
uv venv --seed
source .venv/bin/activate

# Always safe to use python -m pip
python -m pip install -U pip
python -m pip install -r requirements.txt  # if you add one later
```

## Deploy (Static Hosting)
- GitHub Pages: push this repo, enable Pages (main branch / root), visit the Pages URL.
- Netlify/Vercel: drag-and-drop or connect repo and deploy as a static site.

## Development Notes
- Main file: `index.html`
- No backend required
- If adding JS/CSS assets, reference them relative to project root so Pages/Netlify works

## License
MIT (update as desired)
