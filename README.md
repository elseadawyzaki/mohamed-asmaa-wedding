# Mohamed & Asmaa Wedding Invitation

A bilingual Arabic/English wedding invitation for Sunday, 16 August 2026 at 5:00 PM at Al Damatti Mosque. The couple’s engagement date, Friday 11 October 2024, is included in the story and date details. The site uses plain HTML, CSS, and JavaScript and is ready for GitHub Pages.

## Important setup before publishing

The message form can send and save responses directly without opening WhatsApp. Create a form in [Formspree](https://formspree.io/), copy its endpoint from the Integration page, then add it near the top of `script.js`:

```js
rsvpEndpoint: "https://formspree.io/f/YOUR_FORM_ID"
```

The form submits in the background, keeps the guest on the invitation page, and shows a success or error message. Responses are stored in the connected Formspree account. No private API key is placed in the website.

After publishing, add the final website address to:

```js
websiteUrl: "https://USERNAME.github.io/ma-wedding/"
```

Without an endpoint, the form stays on the page and shows a short setup message instead of sending data.

## Preview locally

Double-click `index.html`, or start any static web server in this folder. The website does not require Node.js, npm, or a build step.

## Photo files

The invitation now uses Mohamed and Asmaa's supplied personal photographs. Optimized copies are stored inside `assets/images/`. To change a photo later, replace the matching file while keeping its exact filename:

- `hero-placeholder.webp` — enhanced main image at 2508 × 2508
- `welcome-placeholder.webp` — full image at 5472 × 3648
- `gallery-1-placeholder.webp` — 960 × 884
- `gallery-2-placeholder.webp` — 689 × 919
- `gallery-3-placeholder.webp` — 128 × 170 (the resolution of the supplied source)
- `gallery-4-placeholder.webp` — 5472 × 3648
- `gallery-5-placeholder.webp` — 5472 × 3648
- `gallery-6-placeholder.webp` — 3648 × 5472
- `gallery-7-placeholder.webp` — 625 × 1280
- `gallery-8-placeholder.webp` — 720 × 720
- `gallery-9-placeholder.webp` — 1080 × 1073
- `social-preview-placeholder.jpg` — exactly 1200 × 630
- `ma-logo.svg` — scalable Arabic «ع م» Ruqaa-inspired gold and burgundy wedding monogram
- `story-2.webp` through `story-5.webp` — images for the dated story milestones; the first-meeting card is text-only

Keeping the filenames means no code changes are needed. Every gallery image keeps its full supplied dimensions and aspect ratio; WebP compression reduces transfer size without cropping.

## Customize content

The main settings are grouped at the top of `script.js` in the `invitation` object. Update the date, venue, address, maps URL, form endpoint, and website URL there.

Arabic and English interface text is stored in the `translations` object below the configuration. The story is intentionally general, so it can be personalized later without changing the layout.

## Color themes

The black-and-gold theme is currently active through `class="theme-black-gold"` on the `<body>` element in `index.html`. The original ivory, rose, and burgundy colors remain fully preserved in `style.css`. Remove only `theme-black-gold` from `<body>` to restore the original theme.

## Optional music

The entrance screen is configured to play:

```js
musicFile: "assets/audio/our-song.mp3"
```

When the visitor clicks the animated invitation envelope, the card opens and the music begins. This click is required because browsers block automatic audio with sound before user interaction. A play/pause control remains available in the header.

Replace `assets/audio/our-song.mp3` with your chosen track while keeping the same filename. Publish only music you own or have permission to use.

## Publish with GitHub Pages

1. Create a public GitHub repository named `ma-wedding`.
2. Upload the contents of this folder to the `main` branch.
3. Open the repository’s **Settings**.
4. Select **Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select the `main` branch and `/ (root)` folder.
7. Save and wait for GitHub Pages to publish.

The resulting address should look like:

```text
https://USERNAME.github.io/ma-wedding/
```

Add that exact address to `invitation.websiteUrl` in `script.js`, commit, and push once more. In GitHub Pages settings, enable **Enforce HTTPS** when the option is available.

### Command-line Git option

```bash
git init
git add .
git commit -m "Create Mohamed and Asmaa wedding invitation"
git branch -M main
git remote add origin https://github.com/USERNAME/ma-wedding.git
git push -u origin main
```

Replace `USERNAME` with the real GitHub username.

## Custom domain

Add the domain under **Settings → Pages → Custom domain**, then configure the DNS records requested by GitHub. Verify the domain in GitHub before connecting it and enable HTTPS afterward.

## Privacy and copyright

GitHub Pages sites are public. Do not publish phone numbers, private photographs, personal messages, analytics, or other sensitive information unless everyone involved agrees. Use only photographs and music you own or have permission to publish.
