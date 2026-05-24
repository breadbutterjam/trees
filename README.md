# Tree Marker App - Phase 1

A mobile-optimized web application for recording and tracking trees in urban areas.

## Current Features (Phase 1)

✅ Interactive map with location selection
✅ Visual grid selection for tree types
✅ Dropdown view toggle
✅ Optional details expansion
✅ GPS location support
✅ Form validation
✅ Mobile-responsive design

## Folder Structure

```
tree-marker/
├── index.html              # Main application file (rename tree-marker-app.html to this)
├── img/                    # Tree reference images
│   ├── default.jpg         # Fallback image (required)
│   ├── banyan.jpg
│   ├── peltophorum.jpg
│   ├── gulmohar.jpg
│   ├── rain-tree.jpg
│   ├── peepal.jpg
│   ├── mango.jpg
│   ├── pink-trumpet.jpg
│   ├── devil-tree.jpg
│   ├── golden-shower.jpg
│   ├── frangipani.jpg
│   ├── indian-almond.jpg
│   └── ashoka.jpg
└── README.md               # This file
```

## Setup Instructions

### 1. Create Folder Structure

```bash
mkdir tree-marker
cd tree-marker
mkdir img
```

### 2. Add the HTML File

- Rename `tree-marker-app.html` to `index.html`
- Place it in the `tree-marker/` folder

### 3. Add Tree Reference Images

You need to add images to the `img/` folder. Each tree type needs a corresponding image:

**Required:**
- `default.jpg` - This is used as fallback when specific tree image is not available

**Tree Type Images:**
- `banyan.jpg`
- `peltophorum.jpg`
- `gulmohar.jpg`
- `rain-tree.jpg`
- `peepal.jpg`
- `mango.jpg`
- `pink-trumpet.jpg`
- `devil-tree.jpg`
- `golden-shower.jpg`
- `frangipani.jpg`
- `indian-almond.jpg`
- `ashoka.jpg`

**Image Guidelines:**
- Format: JPG or PNG
- Recommended size: 400x300px (will be displayed at 100px height)
- Keep file sizes small (<200KB each) for faster loading
- Clear, representative photos of each tree type

**Where to get images:**
- Your own photos
- Wikipedia (check license)
- iNaturalist (Creative Commons)
- Wikimedia Commons

### 4. Testing Locally

#### Option A: Simple Python Server
```bash
cd tree-marker
python3 -m http.server 8000
```
Then open: `http://localhost:8000`

#### Option B: VS Code Live Server
- Install "Live Server" extension
- Right-click `index.html` → "Open with Live Server"

#### Option C: Just open the file
- Double-click `index.html`
- Works, but geolocation might not work due to browser security

### 5. Testing on Mobile

#### Option A: Same WiFi Network
```bash
# Find your computer's IP address
# On Mac/Linux:
ifconfig | grep "inet "
# On Windows:
ipconfig

# Start server
python3 -m http.server 8000

# On your phone's browser, visit:
http://YOUR_IP_ADDRESS:8000
# Example: http://192.168.1.5:8000
```

#### Option B: Deploy to GitHub Pages (Recommended)
See deployment section below.

## Tree Types Included

The app comes pre-configured with 12 common Mumbai urban trees:

1. **Banyan** - _Ficus benghalensis_
2. **Yellow Gulmohar** - _Peltophorum pterocarpum_
3. **Gulmohar** - _Delonix regia_
4. **Rain Tree** - _Samanea saman_
5. **Peepal** - _Ficus religiosa_
6. **Mango** - _Mangifera indica_
7. **Pink Trumpet** - _Tabebuia rosea_
8. **Devil Tree** - _Alstonia scholaris_
9. **Golden Shower** - _Cassia fistula_
10. **Frangipani** - _Plumeria_
11. **Indian Almond** - _Terminalia catappa_
12. **Ashoka** - _Polyalthia longifolia_

### Adding More Tree Types

Edit the `treeTypes` array in the JavaScript section (around line 370):

```javascript
const treeTypes = [
    { id: 'your-tree-id', commonName: 'Your Tree', scientificName: 'Scientific name', image: 'your-tree.jpg' },
    // ... existing trees
];
```

Then add the corresponding image to `img/your-tree.jpg`

## Deployment Options

### GitHub Pages (Recommended)

1. Create a GitHub repository named `tree-marker`
2. Upload all files (index.html + img folder)
3. Go to Settings → Pages
4. Select "Deploy from main branch"
5. Your site will be at: `https://your-username.github.io/tree-marker`

**Pros:**
- Free
- Simple
- Auto-deploys on push
- Works well with this static app

### Vercel (Alternative)

1. Install Vercel CLI: `npm install -g vercel`
2. Run: `vercel` in your project folder
3. Follow prompts

**Pros:**
- Faster deploys
- Better dashboard
- Custom domains easier

### Netlify (Alternative)

1. Drag and drop your folder to [Netlify Drop](https://app.netlify.com/drop)
2. Or connect your GitHub repo

**Pros:**
- Similar to Vercel
- Good form handling (for future features)

## How to Use

1. **Open the app** on your mobile browser
2. **Locate yourself** - Tap "locate me" or manually tap the map
3. **Select tree type** - Use visual grid or dropdown
4. **Add details** (optional) - Tap "Add optional details"
   - Common name
   - Scientific name
   - Description/notes
5. **Save** - Tap "Add Tree"

## Current Limitations (Phase 1)

- ❌ Data is not saved (only logged to console)
- ❌ No photo upload yet
- ❌ No database integration
- ❌ No list view of saved trees
- ❌ No edit functionality (yet)

These will be added in subsequent phases.

## Next Phases

### Phase 2: Supabase Integration
- Set up Supabase project
- Create database schema
- Save/retrieve tree data
- List view of trees
- Edit existing trees

### Phase 3: Photo Upload
- Camera integration
- Gallery upload
- Client-side compression
- Supabase Storage integration

### Phase 4: Google Sheets Backup
- Google Sheets API integration
- Dual-write functionality
- Export capability

## Browser Requirements

- Modern mobile browser (Chrome, Safari, Firefox)
- JavaScript enabled
- Geolocation permission (for GPS features)

## Troubleshooting

**Images not loading:**
- Check that `img/` folder is in the same directory as `index.html`
- Ensure `default.jpg` exists as fallback
- Check browser console for errors

**Geolocation not working:**
- Grant location permission when prompted
- Must be served over HTTPS (or localhost)
- Won't work if you just open the HTML file directly

**Map not loading:**
- Check internet connection (Leaflet + OpenStreetMap require online access)
- Check browser console for errors

**Form not working:**
- Must select both location and tree type before "Add Tree" enables
- Check browser console for errors

## Support

For issues or questions, check the browser console (F12 → Console tab) for error messages.

## License

[Add your license here]

## Credits

- Maps: OpenStreetMap + Leaflet.js
- Tree icons: Unicode emoji
- Design: Custom
