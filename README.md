# THE BRAZILS CAVE — Windows app

Audiobook player with exact-to-the-second memory, genre shelves, an Acrobat-style PDF reader
with page-turn animation, and a theme studio (rain, storms, wallpapers, GIFs).

## Get the .exe from GitHub (nothing to install on your PC)

1. Create a new repository on github.com (for example `brazils-cave`).
2. Upload **everything in this folder** — keep the hidden `.github/workflows` folder! Or use git:
   ```
   git init
   git add .
   git commit -m "THE BRAZILS CAVE"
   git branch -M main
   git remote add origin https://github.com/YOUR-NAME/brazils-cave.git
   git push -u origin main
   ```
3. Open the **Actions** tab -> *Build Windows app*. It starts by itself (about 3-5 minutes).
   You can also press **Run workflow**.
4. When it turns green, open the run and download **BrazilsCave-Windows** under *Artifacts*.
   Inside: `BrazilsCave-Setup-1.0.0.exe` (installer) and `BrazilsCave-Portable-1.0.0.exe` (no install).

### Optional: permanent download page
Push a tag and GitHub publishes the files under **Releases**:
```
git tag v1.0.0
git push origin v1.0.0
```

## Run it on your own PC instead
Install Node.js 20+, then in this folder:
```
npm install
npm start          # opens the app
npm run dist       # builds the .exe into /dist
```

## Notes
- Your listening memory, books and settings live in the app's own storage
  (`%APPDATA%\THE BRAZILS CAVE`). Use the gear -> *Export memory backup* now and then.
- Windows SmartScreen may say "unknown publisher" because the app isn't code-signed:
  choose *More info -> Run anyway*.
- The PDF engine downloads once from the internet the first time you open a PDF.
- To update the app: replace `app/index.html`, raise `"version"` in `package.json`, push.
