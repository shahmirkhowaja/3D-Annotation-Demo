# 🚀 Server Deployment Guide

**GLB Annotation Pro v1.0.0**  
**Created by:** Shahmir Khowaja

## 📦 Files to Deploy

Upload ALL files from this folder to your web server:

```
dist/
├── index.html          (Main HTML file)
├── assets/
│   ├── index-C4XmwKhf.css    (Styles)
│   └── index-BPTbxxBc.js     (Application code)
└── SERVER_DEPLOYMENT_GUIDE.md (This file)
```

## 🌐 Server Requirements

- **Web Server**: Apache, Nginx, IIS, or any static file server
- **HTTPS**: Recommended for production
- **CORS**: Must allow external CDN resources

## 📋 Deployment Steps

### For Apache Server:

1. Copy all files to your document root:

   ```bash
   /var/www/html/
   ```

2. Ensure `.htaccess` allows file access (if using)

3. No additional configuration needed!

### For Nginx Server:

1. Copy all files to your root directory:

   ```bash
   /usr/share/nginx/html/
   ```

2. Nginx config example:

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

### For Windows IIS:

1. Copy all files to your IIS website folder:

   ```
   C:\inetpub\wwwroot\
   ```

2. Ensure MIME types are configured for:
   - `.js` → `application/javascript`
   - `.css` → `text/css`

### For cPanel/Shared Hosting:

1. Upload all files to `public_html/` folder
2. Access via your domain: `https://yourdomain.com/`

## ✅ Testing Your Deployment

1. Open your domain in a browser
2. You should see the GLB Annotation Pro interface
3. Try uploading a .glb file
4. Check browser console (F12) for any errors

## 🌐 External Dependencies (CDN)

The application uses these CDN resources:

- Tailwind CSS: `https://cdn.tailwindcss.com`
- Font Awesome: `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css`
- React & Three.js: `https://esm.sh/`

**Important:** Ensure your server/firewall allows connections to these CDNs.

## 🔧 Troubleshooting

**Issue: Blank white screen**

- Check browser console for errors
- Verify all files uploaded correctly
- Check CDN accessibility

**Issue: 404 for assets**

- Verify `assets/` folder structure is intact
- Check file permissions (755 for folders, 644 for files)

**Issue: GLB files won't load**

- Check CORS configuration
- Verify file size limits on your server

## 📊 File Sizes

- Total size: ~1.3 MB
- Main JS: ~1.3 MB (gzipped: ~368 KB)
- CSS: ~0.45 KB
- HTML: ~1.4 KB

## 🔐 Security Notes

- All code is minified and production-ready
- No sensitive data or API keys included
- External dependencies loaded from trusted CDNs

## 📧 Support

**Created by:** Shahmir Khowaja

For issues or questions, refer to the project documentation.

---

**Deployment Date:** March 6, 2026  
**Version:** 1.0.0
