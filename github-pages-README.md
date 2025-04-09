# GitHub Pages Website for Wizarding Bank & Shop Discord Bot

This directory contains the website files for the Wizarding Bank & Shop Discord Bot. The website is designed to be hosted on GitHub Pages.

## Hosting on GitHub Pages

To host this website on GitHub Pages:

1. Ensure your repository has GitHub Pages enabled:
   - Go to your repository settings
   - Scroll down to the "GitHub Pages" section
   - Select the branch you want to deploy from (typically `main` or `gh-pages`)
   - Choose the folder (either root `/` or `/docs`) where your website files are located

2. If you want to use a custom domain:
   - In the GitHub Pages settings, enter your custom domain
   - Create a CNAME file in your repository with your domain name

3. Update placeholder images:
   - Add your actual logo and preview images to the images folder

## Website Content

The website features:
- An overview of the bot's features
- A showcase of the technology stack used to develop the bot
- A comprehensive command reference
- Responsive design for mobile and desktop viewing

## File Structure

- `index.html` - The main landing page
- `commands.html` - Complete list of bot commands
- `styles.css` - CSS styles for all pages
- `images/` - Directory containing all images used on the website
  - `logo.png` - Your bot's logo
  - `preview.png` - Screenshot of your bot in action
  - `parchment-bg.jpg` - Background image (you'll need to add this)

## Adding Images

For the website to display correctly, you need to add the following images:

1. **Logo**: Create a square logo image (recommended size: 200x200px) and save it as `images/logo.png`
2. **Preview**: Take a screenshot of your bot in action and save it as `images/preview.png`
3. **Background**: Find or create a parchment-style background and save it as `images/parchment-bg.jpg`

## Testing Locally

You can test the website locally by opening the HTML files directly in your browser, or by using a local server:

```bash
# Using Python 3
python -m http.server

# Using Python 2
python -m SimpleHTTPServer
```

Then visit `http://localhost:8000` in your browser.

## Customization

Feel free to customize the website to better match your bot's branding:

- Change the color scheme in `styles.css` (look for the `:root` variables at the top)
- Add additional pages as needed
- Customize the content to highlight your bot's unique features
- Update the Technology Stack section if you've used additional technologies 