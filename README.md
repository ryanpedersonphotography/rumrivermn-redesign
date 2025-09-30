# Rum River Barn & Vineyard Website - REDESIGN

## Overview
Static website redesign for Rum River Barn & Vineyard, a wedding and event venue in Milaca, Minnesota.

**Development Site**: https://rumriverredesign.netlify.app  
**Netlify Site Name**: rumriverredesign  
**GitHub Repository**: https://github.com/ryanpedersonphotography/rumrivermn-redesign  
**Production Site**: https://rumrivermn.com (original site)

## Deployment

### Automatic Deployment
- **Platform**: Netlify
- **Deploy URL**: https://rumriverredesign.netlify.app
- **Trigger**: Manual deployment or automatic on push to `master` branch (requires GitHub connection in Netlify admin)
- **Build Settings**: Static site, no build process required

### Manual Deployment
```bash
# Make changes locally
git add .
git commit -m "Your commit message"
git push redesign master  # Push to redesign remote
# OR deploy directly with Netlify CLI
netlify deploy --prod
```

### Checking Deployment Status
```bash
# Using Netlify CLI
netlify status
netlify open:admin  # Opens Netlify admin panel

# View recent deployments
netlify deploys:list
```

## Local Development

### Prerequisites
- Git
- Netlify CLI (optional): `npm install -g netlify-cli`

### Setup
```bash
git clone https://github.com/ryanpedersonphotography/rumrivermn-redesign.git
cd rumrivermn-redesign
```

### Local Preview
```bash
# Using Python
python3 -m http.server 8000

# Or using Netlify Dev
netlify dev
```

## Site Structure

### Main Pages
- Home (`index.html`)
- Wedding/Event Venues (various event type pages)
- Photo Gallery (`photo-gallery.html`)
- Individual wedding galleries (e.g., `allison-and-will.html`)
- Contact forms (Netlify Forms integration)

### Assets
- `/files/` - Images and media files
- `/cms_websites/` - CSS and JavaScript files
- `/wp-content/` - Legacy WordPress assets

## Known Issues & Fixes

### Gallery Images
- **Issue**: Images previously used lazy loading which broke when original WordPress site went offline
- **Partial Fix Applied**: 
  - Fixed jQuery loading order in all gallery subpages (moved to head section)
  - Gallery pages now display images correctly
  - Main photo-gallery.html still has lazy loading issues (thumbnails may not display)

### Form Submissions
- Contact forms use Netlify Forms
- Form submissions are handled by Netlify's built-in form handling

## Recent Fixes (November 11, 2024)

### Completed
- ✅ Fixed JavaScript execution order in 14 gallery pages
- ✅ Removed `target="_blank"` from photo gallery navigation
- ✅ Synced local repository with GitHub
- ✅ Verified deployment pipeline to Netlify

### Pending Issues
- Photo gallery page thumbnails not loading (lazy loading still active)
- Some root-level HTML pages may have path issues

## Configuration

### Netlify Configuration (`netlify.toml`)
```toml
[build]
  publish = "."

[build.processing.forms]
  enable = true

[build.processing.html]
  pretty_urls = false
```

## Maintenance

### Adding New Content
1. Add HTML files to appropriate directories
2. Update navigation in relevant pages
3. Commit and push changes

### Updating Images
1. Add images to `/files/` directory with appropriate year/month subdirectory
2. Reference in HTML files
3. Commit and push changes

## Support

For deployment issues, check:
1. Netlify dashboard: https://app.netlify.com/sites/rumriverredesign
2. GitHub repository: https://github.com/ryanpedersonphotography/rumrivermn-redesign
3. Development site: https://rumriverredesign.netlify.app
4. Production site (original): https://rumrivermn.com

## Last Updated
September 30, 2025 - Created redesign repository and Netlify site