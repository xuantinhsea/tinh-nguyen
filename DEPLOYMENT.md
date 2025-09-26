# 🚀 Deployment Guide

This guide will help you deploy your portfolio website to various platforms.

## 📋 Prerequisites

- GitHub account
- Git installed on your local machine
- Basic knowledge of Git commands

## 🌐 GitHub Pages Deployment

### Method 1: Repository Name (Recommended)

1. **Fork this repository** to your GitHub account
2. **Rename the repository** to `yourusername.github.io` (replace `yourusername` with your GitHub username)
3. **Clone the repository** to your local machine:
   ```bash
   git clone https://github.com/yourusername/yourusername.github.io.git
   cd yourusername.github.io
   ```
4. **Customize the content** (see README.md for customization guide)
5. **Commit and push your changes**:
   ```bash
   git add .
   git commit -m "Initial portfolio setup"
   git push origin main
   ```
6. **Enable GitHub Pages**:
   - Go to your repository settings
   - Scroll down to "Pages" section
   - Select "Deploy from a branch"
   - Choose "main" branch and "/ (root)" folder
   - Click "Save"
7. **Your site will be live** at `https://yourusername.github.io`

### Method 2: Custom Repository Name

1. **Fork this repository** with any name
2. **Update `_config.yml`**:
   ```yaml
   baseurl: "/your-repository-name"
   url: "https://yourusername.github.io"
   ```
3. **Enable GitHub Pages** in repository settings
4. **Your site will be live** at `https://yourusername.github.io/your-repository-name`

## 🔧 Custom Domain Setup

1. **Add your domain** to the `CNAME` file:
   ```
   yourdomain.com
   ```

2. **Configure DNS** with your domain provider:
   - Add a CNAME record pointing to `yourusername.github.io`
   - Or add A records pointing to GitHub Pages IP addresses:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153

3. **Enable custom domain** in GitHub Pages settings

## 🌟 Alternative Deployment Platforms

### Netlify

1. **Connect your GitHub repository** to Netlify
2. **Set build settings**:
   - Build command: (leave empty)
   - Publish directory: `/` (root)
3. **Deploy** - Netlify will automatically deploy your site

### Vercel

1. **Import your GitHub repository** to Vercel
2. **Configure project**:
   - Framework Preset: Other
   - Root Directory: `/`
3. **Deploy** - Vercel will handle the rest

### Firebase Hosting

1. **Install Firebase CLI**:
   ```bash
   npm install -g firebase-tools
   ```

2. **Initialize Firebase**:
   ```bash
   firebase init hosting
   ```

3. **Deploy**:
   ```bash
   firebase deploy
   ```

## 🔄 Continuous Deployment

### GitHub Actions (Optional)

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./
```

## 🛠️ Local Development

### Using Python (Simple)

```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

### Using Node.js

```bash
# Install a simple server
npm install -g http-server

# Run the server
http-server -p 8000
```

### Using Jekyll (Full Features)

```bash
# Install Jekyll
gem install bundler
bundle install

# Run Jekyll server
bundle exec jekyll serve
```

## 📊 Performance Optimization

### Before Deployment

1. **Optimize images**:
   - Compress images using tools like TinyPNG
   - Use appropriate formats (WebP for modern browsers)
   - Add alt text for accessibility

2. **Minify files**:
   - Minify CSS and JavaScript
   - Remove unused code

3. **Enable compression**:
   - Most hosting platforms enable gzip compression automatically

### After Deployment

1. **Test your site**:
   - Use Google PageSpeed Insights
   - Test on different devices and browsers
   - Check mobile responsiveness

2. **Set up analytics**:
   - Add Google Analytics
   - Monitor site performance

## 🔍 SEO Setup

1. **Update meta tags** in `index.html`
2. **Submit sitemap** to Google Search Console
3. **Add structured data** for better search results
4. **Optimize images** with proper alt text

## 🚨 Troubleshooting

### Common Issues

1. **Site not loading**:
   - Check repository name (should be `username.github.io`)
   - Verify GitHub Pages is enabled
   - Check for build errors

2. **Custom domain not working**:
   - Verify DNS settings
   - Check CNAME file
   - Wait for DNS propagation (up to 24 hours)

3. **Images not displaying**:
   - Check file paths
   - Ensure images are committed to repository
   - Verify file permissions

### Getting Help

- Check GitHub Pages documentation
- Review repository settings
- Check browser console for errors
- Test locally first

## 📈 Monitoring and Maintenance

1. **Regular updates**:
   - Keep content fresh
   - Update dependencies
   - Monitor performance

2. **Backup**:
   - Your code is already backed up in Git
   - Consider backing up custom images

3. **Analytics**:
   - Monitor visitor statistics
   - Track page performance
   - Analyze user behavior

---

**Happy Deploying! 🎉**

Your portfolio website is now ready to showcase your work to the world!
