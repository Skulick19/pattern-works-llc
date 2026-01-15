# Pattern Works LLC Website

Static website for Pattern Works LLC, a software development studio.

## Local Development

Simply open `index.html` in a browser, or use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js (npx)
npx serve .

# Using PHP
php -S localhost:8000
```

Then visit `http://localhost:8000`

## Deploying to Azure Static Web Apps

### Prerequisites
- Azure account
- GitHub repository with this code

### Steps

1. **Push code to GitHub**
   ```bash
   # If creating a new repo for just this site
   cd pattern-works-llc
   git init
   git add .
   git commit -m "Initial commit - Pattern Works LLC website"
   git remote add origin https://github.com/YOUR_USERNAME/pattern-works-llc.git
   git push -u origin main
   ```

2. **Create Azure Static Web App**
   - Go to [Azure Portal](https://portal.azure.com)
   - Search for "Static Web Apps"
   - Click "Create"
   - Fill in:
     - **Subscription**: Your subscription
     - **Resource Group**: Create new or use existing
     - **Name**: `pattern-works-llc` (or your choice)
     - **Plan type**: Free
     - **Region**: Choose closest to you
   - Click "Sign in with GitHub"
   - Select your repository and branch
   - **Build Details**:
     - **Build Presets**: Custom
     - **App location**: `/` (root)
     - **Output location**: Leave empty (static files)
   - Click "Review + Create", then "Create"

3. **Automatic Deployment**
   - Azure creates a GitHub Action in your repo
   - Every push to main triggers automatic deployment
   - First deployment happens immediately

4. **Get Your URL**
   - Once deployed, go to your Static Web App in Azure Portal
   - Find the URL (e.g., `https://random-name-123.azurestaticapps.net`)
   - You can add a custom domain in Settings > Custom Domains

### Custom Domain Setup

1. In Azure Portal, go to your Static Web App
2. Click "Custom domains" in the sidebar
3. Click "Add"
4. Enter your domain (e.g., `patternworksllc.com`)
5. Follow instructions to add DNS records:
   - For apex domain: Add an ALIAS or ANAME record
   - For subdomain: Add a CNAME record
6. Azure provides free SSL certificates

## Files

- `index.html` - Main webpage
- `styles.css` - All styling
- `staticwebapp.config.json` - Azure Static Web Apps configuration

## Contact

Pattern Works LLC
Email: patternworksllc@gmail.com
