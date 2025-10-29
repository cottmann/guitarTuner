# Guitar Tuner PWA

A chromatic guitar tuner that runs locally in your mobile browser as a Progressive Web App (PWA). No internet connection required after installation!

## Features

- **Real-time pitch detection** using the Web Audio API and auto-correlation algorithm
- **Visual feedback** with color-coded tuning indicator (green = in tune, yellow = close, red = needs adjustment)
- **Cents display** showing how many cents sharp or flat you are
- **Standard tuning reference** for all 6 guitar strings (E2, A2, D3, G3, B3, E4)
- **Works offline** once installed
- **Mobile-optimized** interface
- **Installable** as a native-like app on iOS and Android

## Live Demo

Visit the live app at: `https://[your-username].github.io/guitarTuner/`

## Deployment to GitHub Pages

### Automatic Deployment (Recommended)

1. **Merge your branch to main:**
   ```bash
   git checkout main
   git merge claude/guitar-tuner-pwa-011CUc1gtehuMJmp9MnDm3eF
   git push origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Click **Settings** → **Pages**
   - Under "Build and deployment":
     - Source: **GitHub Actions**
   - The workflow will automatically deploy on push to main

3. **Access your app:**
   - After deployment completes, visit: `https://[your-username].github.io/guitarTuner/`

### Manual Deployment (Alternative)

1. Go to repository **Settings** → **Pages**
2. Under "Source", select **Deploy from a branch**
3. Select branch: **main** and folder: **/ (root)**
4. Click **Save**

## Installation

### Desktop Testing
1. Open a web browser and navigate to the hosted URL or run a local server:
   ```bash
   python3 -m http.server 8000
   ```
2. Visit `http://localhost:8000`

### Mobile Installation

#### Android (Chrome)
1. Visit the app URL in Chrome
2. Tap the "Install" prompt or menu → "Add to Home Screen"
3. The app will be installed like a native app

#### iOS (Safari)
1. Visit the app URL in Safari
2. Tap the Share button
3. Scroll down and tap "Add to Home Screen"
4. Tap "Add" to install

## How to Use

1. **Allow microphone access** when prompted
2. **Tap the microphone button** to start tuning
3. **Play a string** on your guitar
4. **Watch the display** for:
   - The detected note and frequency
   - Cents offset (how far sharp or flat you are)
   - Visual tuning indicator
   - Status text (In Tune! / Too Sharp ↑ / Too Flat ↓)
5. **Adjust your string** until you see "In Tune!" in green

## Technical Details

### Technologies Used
- **Web Audio API** for microphone access and audio processing
- **Auto-correlation algorithm** for accurate pitch detection
- **Service Worker** for offline functionality
- **Web App Manifest** for installability
- **Tailwind CSS** for responsive styling

### Browser Support
- Chrome/Edge 89+
- Safari 14.5+
- Firefox 90+

Requires:
- HTTPS (or localhost for testing)
- Microphone permission
- Web Audio API support

## File Structure

```
guitarTuner/
├── index.html          # Main application (HTML + JavaScript)
├── manifest.json       # PWA manifest
├── sw.js              # Service worker for offline support
├── icon.png           # App icon (512x512)
└── README.md          # This file
```

## Development

The app is built with vanilla JavaScript (no frameworks) for minimal size and maximum compatibility. The React code was converted to vanilla JS to create a standalone PWA.

### Local Development
```bash
# Run a local server
python3 -m http.server 8000

# Or use Node.js
npx serve
```

### Customization
- Modify tuning frequencies in `index.html` (look for the standard tuning section)
- Adjust sensitivity by changing the RMS threshold in `autoCorrelate()`
- Customize colors and styling in the Tailwind classes

## Credits

Based on:
- Guitar tuner code from Claude AI
- Minimal PWA structure from [chr15m/minimal-pwa](https://github.com/chr15m/minimal-pwa)

## License

Open source - feel free to use and modify!
