# GLB Annotation Pro - Deployment Guide

**Created by:** Shahmir Khowaja  
**Version:** 1.0.0

## 📦 What's Included

This folder contains the production-ready build of GLB Annotation Pro:

- `index.html` - Main HTML file
- `assets/` - JavaScript and CSS files
  - `index-DuHjXsKk.js` - Application JavaScript (minified)
  - `index-C4XmwKhf.css` - Application styles

## 🚀 Deployment Instructions

### Option 1: Simple Web Server

Copy all files from this `dist` folder to your web server's public directory.

**Example structure on server:**

```
/var/www/html/
├── index.html
└── assets/
    ├── index-DuHjXsKk.js
    └── index-C4XmwKhf.css
```

### Option 2: Apache Server

1. Copy all files to your Apache document root (e.g., `/var/www/html/`)
2. Ensure `.htaccess` allows file access
3. No additional configuration needed

### Option 3: Nginx Server

1. Copy all files to your Nginx root directory (e.g., `/usr/share/nginx/html/`)
2. Nginx configuration example:

```nginx
server {
    listen 80;
    server_name your-domain.com;
    root /usr/share/nginx/html;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

### Option 4: Static Hosting Services

Upload the entire `dist` folder contents to:

- **Netlify**: Drag and drop the dist folder
- **Vercel**: Deploy via CLI or GitHub integration
- **GitHub Pages**: Push to gh-pages branch
- **AWS S3**: Upload to S3 bucket with static hosting enabled

## 🌐 CDN Dependencies

The application uses these external CDN resources:

- Tailwind CSS: `https://cdn.tailwindcss.com`
- Font Awesome: `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css`
- React & Three.js: Loaded via ESM from `https://esm.sh/`

**Note:** Ensure your server allows external CDN connections.

## ✅ Testing Your Deployment

1. Open your deployed URL in a browser
2. You should see the GLB Annotation Pro interface
3. Try uploading a .glb file to test functionality
4. Check browser console for any errors

## 📝 Requirements

- Modern web browser with WebGL support
- Internet connection (for CDN resources)
- HTTPS recommended for production

## 🔧 Troubleshooting

**Issue:** Blank white screen

- Check browser console for errors
- Verify all files are uploaded correctly
- Ensure CDN resources are accessible

**Issue:** 404 errors for assets

- Verify the `assets/` folder structure is intact
- Check file paths in index.html match your server structure

**Issue:** GLB files won't load

- Ensure CORS is properly configured on your server
- Check file size limits on your hosting

## 📧 Support

Created by: Shahmir Khowaja

For issues or questions, please refer to the project repository.

---

**Last Updated:** March 6, 2026
