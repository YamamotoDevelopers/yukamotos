# Yukamoto's Holiday Card 2025

A single-page website showcasing the Yukamoto holiday card hosted on Vimeo.

## Overview

- **URL**: [yukamotos.go-yamamoto.com](https://yukamotos.go-yamamoto.com)
- **Hosting**: Cloudflare Pages
- **DNS**: Cloudflare
- **Video**: Vimeo embed

## Project Structure

```
├── index.html        # Main HTML file with Vimeo embed
├── styles.css        # Responsive CSS styling
├── _headers          # Cloudflare Pages security headers
├── .gitignore        # Git ignore file
└── README.md         # This file
```

## Design Specifications

### Brand Colors
- Background: `#000000` (Black)
- Text: `#FFFFFF` (White)
- Accent: `#EB4439` (Red)

### Typography
- Font Family: Oswald (Google Fonts)

### Features
- Responsive design (mobile, tablet, desktop)
- 16:9 aspect ratio video player
- Vimeo embed with optimal settings
- SEO meta tags
- Social media sharing tags (Open Graph, Twitter)
- Security headers via `_headers` file
- Loading animation for video

## Local Development

To view the site locally, simply open `index.html` in your browser:

```bash
open index.html
```

Or use a local server:

```bash
# Python 3
python -m http.server 8000

# Node.js (if you have http-server installed)
npx http-server
```

Then navigate to `http://localhost:8000`

## Deployment to Cloudflare Pages

### Step 1: Create GitHub Repository

1. Create a new repository on GitHub (e.g., `yukamotos`)
2. Push this code to the repository:

```bash
git add .
git commit -m "Initial commit: sizzle reel page"
git branch -M main
git remote add origin git@github.com:YOUR_USERNAME/yukamotos.git
git push -u origin main
```

### Step 2: Connect to Cloudflare Pages

1. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Navigate to **Pages** in the sidebar
3. Click **Create a project**
4. Select **Connect to Git**
5. Authorize GitHub and select your repository
6. Configure build settings:
   - **Project name**: `yukamotos`
   - **Production branch**: `main`
   - **Build command**: (leave empty - static site)
   - **Build output directory**: `/`
7. Click **Save and Deploy**

### Step 3: Configure Custom Domain

1. In Cloudflare Pages, go to your project
2. Navigate to **Custom domains** tab
3. Click **Set up a custom domain**
4. Enter: `yukamotos.go-yamamoto.com`
5. Cloudflare will automatically configure the DNS records
6. If prompted, add the CNAME record in your DNS settings:
   - **Type**: CNAME
   - **Name**: `yukamotos`
   - **Target**: `yukamotos.pages.dev` (or similar)
   - **Proxy status**: Proxied (orange cloud)

### Step 4: Verify Deployment

1. Wait a few minutes for DNS propagation
2. Visit `https://yukamotos.go-yamamoto.com`
3. Verify the page loads correctly and video plays

## DNS Configuration (Cloudflare)

Since your DNS is managed by Cloudflare, the custom domain setup should be automatic. If you need to manually configure:

1. Go to **DNS** tab in Cloudflare Dashboard
2. Add a CNAME record:
   ```
   Type: CNAME
   Name: yukamotos
   Target: yukamotos.pages.dev
   Proxy status: Proxied
   ```

## Updating the Site

Any changes pushed to the `main` branch will automatically trigger a new deployment on Cloudflare Pages.

```bash
# Make your changes
git add .
git commit -m "Update video or styling"
git push
```

## Video Management

To update the Vimeo video:

1. Replace the `src` attribute in the `<iframe>` tag in `index.html`
2. Update with your new Vimeo embed URL
3. Commit and push changes

## Support

For issues or questions, contact the development team.

---

**Built with**: HTML5, CSS3, Vimeo Player
**Deployed on**: Cloudflare Pages
**Last Updated**: December 2025
