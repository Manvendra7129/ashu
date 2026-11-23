# Ashutosh & Pratiksha — Wedding Invitation

A responsive, single-page wedding invitation for Ashutosh and Pratiksha. This is a static HTML, CSS, and JavaScript site; no build step or framework installation is required.

## Project layout

```text
ashu/
├── index.html
│   Main invitation page and Netlify entry point
├── assets/
│   └── audio/
│       └── music-trimmed.mp3
│           Background music used by the invitation
├── standalone/
│   └── Ashutosh_Pratiksha_Wedding_Invitation_with_Music.html
│       Alternate HTML export; loads the shared audio from ../assets/audio/
├── netlify.toml
│   Netlify publish configuration
├── .gitignore
└── README.md
```

## Run locally

1. Keep the folder structure intact.
2. Open `index.html` in a modern browser.

The invitation loads Google Fonts and Google Maps content from the internet. Background music is bundled locally in `assets/audio/`. Browsers may restrict autoplay, so music starts after a guest taps to open the invitation. Guests can use the music toggle to pause or resume it.

To test the alternate HTML export, open the file inside `standalone/`. Keep the `assets/` folder at the project root so its relative audio path works.

## Replace the background music

1. Replace `assets/audio/music-trimmed.mp3` with your new audio file.
2. Keep the filename `music-trimmed.mp3`, or update the audio `src` path in `index.html` and in the alternate file under `standalone/`.
3. Test playback on desktop and mobile. Browsers may require a guest interaction before playing audio.

## Add the couple's photos

The invitation currently has empty photo slots. To add photos:

1. Create an `assets/images/` folder.
2. Copy the groom's photo, bride's photo, and up to five gallery photos into it.
3. Open `index.html` and find the `PHOTOS` object in the JavaScript section.
4. Set the paths, for example:

```js
var PHOTOS = {
  groom: 'assets/images/groom.jpg',
  bride: 'assets/images/bride.jpg',
  gallery: [
    'assets/images/gallery-1.jpg',
    'assets/images/gallery-2.jpg',
    'assets/images/gallery-3.jpg',
    'assets/images/gallery-4.jpg',
    'assets/images/gallery-5.jpg'
  ]
};
```

Use your actual filenames and keep paths relative to `index.html`. Leave an entry as an empty string if you do not want to show that gallery image.

## Deploy to Netlify using GitHub

No build command is required.

1. Push this project to the GitHub repository: `https://github.com/Manvendrapratapsingh1/ashu`.
2. Sign in to [Netlify](https://app.netlify.com/).
3. Select **Add new site → Import an existing project**.
4. Choose **GitHub**, authorize Netlify if prompted, and select `Manvendrapratapsingh1/ashu`.
5. Configure the deployment:
   - **Production branch:** `main`
   - **Build command:** leave empty
   - **Publish directory:** `.`
6. Select **Deploy site**.

The included `netlify.toml` sets the publish directory to the project root. Netlify will redeploy when you push changes to the connected production branch.

## Suggested Netlify site name

Try `ashutosh-pratiksha-wedding`. If unavailable, try `ashutosh-pratiksha-invitation` or another unique variation. Site names are globally unique, so availability is not guaranteed.

After deployment, the URL will look like `https://YOUR-AVAILABLE-SITE-NAME.netlify.app`.

## Update the live website

After connecting GitHub to Netlify, make changes locally and run:

```powershell
git add .
git commit -m "Update wedding invitation"
git push
```

Netlify will automatically deploy the new version.

## Pre-share checklist

- [ ] Confirm the couple's names, event details, dates, and venue address.
- [ ] Add and test the groom, bride, and gallery photos if desired.
- [ ] Test the invitation on a phone and desktop.
- [ ] Test the book-opening interaction, countdown, event cards, map links, and address-copy button.
- [ ] Test the music toggle and confirm the MP3 loads from `assets/audio/music-trimmed.mp3`.
- [ ] Confirm the deployed Netlify URL before sharing it with guests.
