# ZypherTech Setup Guide

## Quick Setup (5 Minutes)

### Step 1: Open the Website
Simply open `index.html` in your browser. That's it! The website is fully functional.

### Step 2: Customize Content
Edit `index.html` to update:
- Company information
- Service descriptions
- Pricing packages
- Contact details
- Social media links

### Step 3: Customize Branding
Edit `style.css` to change:
- Colors (CSS variables at the top)
- Fonts
- Spacing
- Animations

## Advanced Setup

### Add Favicon
1. Create your favicon using [favicon.io](https://favicon.io/) or [realfavicongenerator.net](https://realfavicongenerator.net/)
2. Download the generated files
3. Place them in the root directory
4. Add these lines to the `<head>` section of `index.html`:

```html
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
<link rel="manifest" href="/manifest.json">
```

### Add PWA Support
The website is PWA-ready! To enable it:

1. Create an `/icons` folder
2. Generate app icons (72x72 to 512x512)
3. Update `manifest.json` paths
4. Add to `index.html` head:
```html
<link rel="manifest" href="/manifest.json">
```

5. Create a service worker (optional for offline support)

### Connect Contact Form
To make the contact form functional:

1. **Option A: Use a Form Service**
   - [Formspree](https://formspree.io/)
   - [Netlify Forms](https://www.netlify.com/products/forms/)
   - [Getform](https://getform.io/)

2. **Option B: Custom Backend**
   Edit `script.js`, function `handleFormSubmission()`:
   ```javascript
   fetch('https://your-api.com/contact', {
       method: 'POST',
       headers: {
           'Content-Type': 'application/json',
       },
       body: JSON.stringify({
           name: formData.get('name'),
           email: formData.get('email'),
           // ... other fields
       })
   })
   ```

3. **Option C: Email Service (EmailJS)**
   ```html
   <!-- Add to HTML head -->
   <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
   ```
   
   ```javascript
   // Initialize in script.js
   emailjs.init("YOUR_PUBLIC_KEY");
   ```

### Add Analytics

**Google Analytics:**
```html
<!-- Add before </head> -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

**Google Tag Manager:**
```html
<!-- Add after opening <head> -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-XXXX');</script>

<!-- Add after opening <body> -->
<noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-XXXX"
height="0" width="0" style="display:none;visibility:hidden"></iframe></noscript>
```

### Update SEO
1. Replace placeholder URLs in meta tags
2. Add your actual domain name
3. Update sitemap.xml with your domain
4. Submit sitemap to Google Search Console
5. Add schema.org structured data

### Domain Setup
1. **Update sitemap.xml**: Replace `www.zyphertech.com` with your domain
2. **Update manifest.json**: Update `start_url` if needed
3. **Update robots.txt**: Update sitemap URL
4. **Update meta tags**: Change all URLs to your domain

## Deployment Options

### Option 1: GitHub Pages (Free)
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/username/repo.git
git push -u origin main
```
Then enable GitHub Pages in repository settings.

### Option 2: Netlify (Free)
1. Sign up at [netlify.com](https://www.netlify.com/)
2. Drag and drop your project folder
3. Done! Site is live.

### Option 3: Vercel (Free)
```bash
npm i -g vercel
vercel
```

### Option 4: Traditional Hosting
1. Upload files via FTP/SFTP
2. Ensure `index.html` is in the web root
3. Configure SSL certificate

## Performance Checklist

- ✅ Minify CSS and JS (use online tools or build process)
- ✅ Optimize images (when you add them)
- ✅ Enable GZIP compression on server
- ✅ Set up caching headers
- ✅ Use a CDN for static assets
- ✅ Test with Google PageSpeed Insights
- ✅ Test with GTmetrix

## Security Checklist

- ✅ Enable HTTPS
- ✅ Add Content Security Policy headers
- ✅ Implement form validation on backend
- ✅ Use environment variables for sensitive data
- ✅ Keep dependencies updated
- ✅ Add rate limiting to forms
- ✅ Sanitize all user inputs

## Testing Checklist

- ✅ Test on multiple browsers (Chrome, Firefox, Safari, Edge)
- ✅ Test on mobile devices (iOS and Android)
- ✅ Test form submissions
- ✅ Test all navigation links
- ✅ Check responsiveness at different screen sizes
- ✅ Validate HTML (W3C Validator)
- ✅ Validate CSS
- ✅ Check for console errors
- ✅ Test with screen readers (accessibility)
- ✅ Test page load speed

## Maintenance

### Regular Updates
- Update content as needed
- Check and fix broken links
- Update prices and packages
- Refresh testimonials and case studies
- Update blog/news section

### Monthly Tasks
- Review analytics data
- Check form submissions
- Update SEO content
- Monitor site performance
- Check for security updates

### Quarterly Tasks
- Review and update service offerings
- Refresh images and graphics
- Update FAQs
- Review and improve SEO
- Check mobile experience

## Troubleshooting

### Smooth Scrolling Not Working
- Check if `scroll-behavior: smooth` is supported
- Verify navigation links have correct `#` format
- Clear browser cache

### Animations Not Playing
- Check browser compatibility
- Verify Intersection Observer support
- Test without ad blockers
- Check console for JavaScript errors

### Form Not Submitting
- Check browser console for errors
- Verify form action/endpoint is configured
- Test network connection
- Check CORS settings if using external API

### Mobile Menu Not Closing
- Verify Bootstrap JS is loaded
- Check for JavaScript conflicts
- Clear browser cache

## Support Resources

- [Bootstrap Documentation](https://getbootstrap.com/docs/5.3/)
- [MDN Web Docs](https://developer.mozilla.org/)
- [CSS-Tricks](https://css-tricks.com/)
- [Web.dev](https://web.dev/)
- [Can I Use](https://caniuse.com/) - Browser compatibility

## Getting Help

If you encounter issues:
1. Check browser console for errors
2. Validate your HTML/CSS
3. Test in different browsers
4. Check this documentation
5. Search for solutions online
6. Contact support: info@zyphertech.com

---

**Need professional help?** Contact ZypherTech for customization and support services!

