# 🌊 Fluid Simulation PWA

An interactive, real-time fluid dynamics simulation with stunning visual effects. Works offline as a Progressive Web App and can be installed on any device!

![Fluid Simulation](https://img.shields.io/badge/PWA-Ready-green) ![WebGL](https://img.shields.io/badge/WebGL-2.0-blue)

## ✨ Features

- 🌊 **Real-time Fluid Dynamics** - Advanced Navier-Stokes simulation
- 🎨 **Beautiful Visual Effects** - Bloom, sunrays, and dynamic colors
- 📱 **Mobile Optimized** - Full touch support with multi-finger gestures
- 🔄 **Works Offline** - PWA with service worker caching
- 💾 **Installable** - Add to home screen on mobile/desktop
- 🎮 **Interactive Controls** - Customizable physics parameters
- 📸 **Screenshot Capture** - Save your fluid art
- 🚀 **High Performance** - Optimized WebGL shaders

## 🎮 Controls

| Action | Control |
|--------|---------|
| Create splash | Click/Tap anywhere |
| Multi-touch | Use multiple fingers |
| Random splashes | Press **Space** |
| Pause/Resume | Press **P** |
| Open settings | Tap top-right corner |
| Screenshot | Settings → Snapshot |

## 🚀 Deployment

### Deploy to Vercel (Recommended)

**Method 1: Using Vercel Website (Easiest)**

1. Go to [vercel.com](https://vercel.com)
2. Sign in with GitHub/GitLab/Bitbucket
3. Click **"Add New..."** → **"Project"**
4. Import your repository or drag-drop folder
5. Click **"Deploy"**
6. Done! 🎉

**Method 2: Using Vercel CLI**

```bash
# Install Vercel CLI globally
npm i -g vercel

# Navigate to your project folder
cd your-project-folder

# Deploy
vercel

# Follow the prompts, then your app is live!
```

**Method 3: Git Integration (Auto-Deploy)**

1. Push code to GitHub:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

2. Go to [vercel.com](https://vercel.com) → Import repository
3. Every push will auto-deploy! 🔄

---

### Deploy to GitHub Pages

1. **Create repository** on GitHub (if not already done)

2. **Push your code:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Fluid Simulation PWA"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Click **Settings** tab
   - Scroll to **"Pages"** section (left sidebar)
   - Under **"Source"**, select **"main"** branch
   - Select **"/ (root)"** folder
   - Click **"Save"**

4. **Access your app:**
   - Wait 1-2 minutes for deployment
   - Visit: `https://YOUR_USERNAME.github.io/YOUR_REPO/`

---

### Deploy to Netlify

1. Drag-drop your folder to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Or connect your GitHub repo for continuous deployment
3. Done! ✨

## 📁 Project Structure

```
fluid-simulation/
├── index.html          # Main application file
├── manifest.json       # PWA manifest configuration
├── sw.js              # Service worker for offline support
├── vercel.json        # Vercel deployment config
├── icon-192.png       # App icon 192x192px
├── icon-512.png       # App icon 512x512px
├── .gitignore         # Git ignore rules
└── README.md          # This file
```

## 🎨 Creating App Icons

You need two icon files: `icon-192.png` (192×192) and `icon-512.png` (512×512)

### Option 1: Online Icon Generator (Easiest)

1. Visit [favicon.io/favicon-generator](https://favicon.io/favicon-generator/)
2. Choose settings:
   - Text: **"F"** or **"~"**
   - Background: **Gradient** (Blue: #1e3a8a to #3b82f6)
   - Font: **Bold**
3. Click **"Download"**
4. Extract and rename to `icon-192.png` and `icon-512.png`

### Option 2: Use Canva (Free)

1. Go to [canva.com](https://canva.com)
2. Create custom size: 512×512
3. Add gradient background (blue theme)
4. Add wave icon or letter "F"
5. Download as PNG
6. Resize to 192×192 for second icon

### Option 3: Quick HTML Canvas Method

Create `generate-icons.html`:

```html
<!DOCTYPE html>
<html>
<head><title>Icon Generator</title></head>
<body>
<canvas id="c" width="512" height="512"></canvas>
<script>
const canvas = document.getElementById('c');
const ctx = canvas.getContext('2d');

// Create gradient
const gradient = ctx.createRadialGradient(256, 256, 50, 256, 256, 300);
gradient.addColorStop(0, '#60a5fa');
gradient.addColorStop(1, '#1e3a8a');

ctx.fillStyle = gradient;
ctx.fillRect(0, 0, 512, 512);

// Add wave pattern
ctx.strokeStyle = 'rgba(255,255,255,0.3)';
ctx.lineWidth = 4;
for(let i = 0; i < 5; i++) {
  ctx.beginPath();
  for(let x = 0; x < 512; x += 10) {
    const y = 256 + Math.sin((x + i * 100) * 0.02) * 80;
    ctx.lineTo(x, y);
  }
  ctx.stroke();
}

alert('Right-click the canvas below and "Save Image As..." → icon-512.png');
</script>
</body>
</html>
```

Open in browser, save as `icon-512.png`, then resize to 192×192 for `icon-192.png`.

## ⚙️ Configuration Options

Access settings panel by tapping the top-right corner:

### Simulation Settings
- **Sim Resolution** (32-256): Affects physics quality
- **Dye Resolution** (128-1024): Color detail level

### Physics Parameters
- **Dissipation** (0-4): How fast colors fade
- **Velocity Loss** (0-4): Fluid friction/drag
- **Curl** (0-50): Vorticity strength (swirls)
- **Radius** (0.01-1.0): Splash size

### Visual Effects
- **Bloom**: Glow effect toggle + intensity
- **Sunrays**: God rays effect toggle

## 🖥️ Local Development

### Simple Method (No Server)
Just open `index.html` in your browser!

### With Local Server (Recommended for testing PWA)

**Python:**
```bash
python -m http.server 8000
```

**Node.js:**
```bash
npx serve
# or
npm install -g http-server
http-server
```

**PHP:**
```bash
php -S localhost:8000
```

Then visit: `http://localhost:8000`

## 🌐 Browser Support

| Browser | Desktop | Mobile |
|---------|---------|--------|
| Chrome | ✅ | ✅ |
| Firefox | ✅ | ✅ |
| Safari | ✅ | ✅ |
| Edge | ✅ | ✅ |
| Opera | ✅ | ✅ |

**Requirements:** WebGL 2.0 or WebGL 1.0 with extensions

## 📱 Installing as App

### On Mobile (iOS/Android)
1. Open the website in browser
2. **iOS**: Tap Share → "Add to Home Screen"
3. **Android**: Tap Menu (⋮) → "Install app" or "Add to Home Screen"

### On Desktop (Chrome/Edge)
1. Look for install icon in address bar
2. Or: Menu → "Install Fluid Simulation..."
3. App opens in its own window!

## 🛠️ Troubleshooting

**Service Worker not updating?**
- Hard refresh: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)
- Or clear cache in browser settings

**Icons not showing?**
- Make sure `icon-192.png` and `icon-512.png` exist
- Check browser console for errors
- Icons should be exactly 192×192 and 512×512 pixels

**App not working offline?**
- Visit the app online first to cache assets
- Check service worker is registered (DevTools → Application → Service Workers)

**Performance issues?**
- Lower "Sim Resolution" in settings
- Lower "Dye Resolution" for mobile
- Disable Bloom/Sunrays on older devices

## 🎯 Performance Tips

- **Mobile**: Use Sim Resolution 64-128, Dye Resolution 512
- **Desktop**: Use Sim Resolution 128-256, Dye Resolution 1024
- **Low-end devices**: Disable Bloom and Sunrays
- **High-end devices**: Max out all settings for best visuals!

## 📄 License

MIT License - Free to use, modify, and distribute!

## 🙏 Credits

Based on WebGL fluid simulation techniques:
- Navier-Stokes equations for fluid dynamics
- GPU-accelerated using WebGL shaders
- Inspired by PavelDoGreat's WebGL Fluid Simulation

## 🐛 Found a Bug?

Open an issue on GitHub or submit a pull request!

## ⭐ Like this project?

Give it a star on GitHub and share it with friends!

---

Made with 💙 by [Your Name]

**Live Demo:** [Your deployed URL here]