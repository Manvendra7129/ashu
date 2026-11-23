# Ashutosh & Pratiksha — Wedding Invitation

A responsive, single-page wedding invitation for Ashutosh and Pratiksha.

## Project structure

```text
ashu/
├── index.html       # Main wedding invitation page
├── netlify.toml     # Netlify static-site configuration
└── README.md        # Project and deployment instructions
```

## Run locally

Open `index.html` in a browser. The page loads Google Fonts, the YouTube IFrame API, and the background music from online services, so those features need an internet connection.

## Add the couple's photos

The invitation currently has empty photo slots. To add photos:

1. Create an `assets` folder beside `index.html`.
2. Copy the groom's photo, bride's photo, and up to five gallery photos into `assets/`.
3. Open `index.html` and find the `PHOTOS` object near the start of the JavaScript section.
4. Set the paths, for example:

```js
var PHOTOS = {
  groom: 'assets/groom.jpg',
  bride: 'assets/bride.jpg',
  gallery: [
    'assets/gallery-1.jpg',
    'assets/gallery-2.jpg',
    'assets/gallery-3.jpg',
    'assets/gallery-4.jpg',
    'assets/gallery-5.jpg'
  ]
};
```

Use the actual filenames and keep the paths relative to `index.html`. If you do not want a gallery image, leave that entry as an empty string.

## Deploy to Netlify using GitHub

This is a static website. No build command or framework installation is required.

1. Push this project to the GitHub repository:
   `https://github.com/Manvendrapratapsingh1/ashu`
2. Sign in to [Netlify](https://app.netlify.com/).
3. Select **Add new site → Import an existing project**.
4. Choose **GitHub**, authorize Netlify if prompted, and select `Manvendrapratapsingh1/ashu`.
5. Configure the deployment:
   - **Production branch:** `main`
   - **Build command:** leave empty
   - **Publish directory:** `.`
6. Select **Deploy site**.

The included `netlify.toml` already sets the publish directory to the project root. Netlify will automatically redeploy whenever you push changes to `main`.

## Use a bride-and-groom URL

When creating the Netlify site, choose this suggested site name:

`ashutosh-pratiksha-wedding`

If Netlify says that name is unavailable, try a variation such as:

- `ashutosh-pratiksha-invitation`
- `ashutosh-weds-pratiksha-2026`
- `ashutosh-pratiksha-raipur`

After deployment, the address will be:

`https://YOUR-AVAILABLE-SITE-NAME.netlify.app`

To change it later, open the site in Netlify and go to **Site configuration → General → Site details → Change site name**. Netlify site names are globally unique, so the exact suggested name is not guaranteed to be available.

## Update the live website

After connecting GitHub to Netlify, edit the files locally and run:

```powershell
git add .
git commit -m "Update wedding invitation"
git push
```

Netlify will build and publish the update automatically.

## Important checks before sharing

- Add and test the groom, bride, and gallery photos.
- Open the deployed URL on a phone and desktop.
- Test the invitation book opening, countdown, event cards, map links, address-copy button, and music toggle.
- Background music depends on YouTube availability and browser autoplay restrictions; guests may need to tap the invitation before audio starts.
- Confirm the event details and venue address before distributing the link.
