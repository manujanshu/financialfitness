# How to Embed the Financial Fitness Test Quiz

## 📋 Overview
This guide will show you how to embed the Financial Fitness Test quiz in any website, including Wix, WordPress, Squarespace, and custom HTML sites.

---

## 🚀 Step 1: Deploy Your App

Before embedding, you need to host your app online. Choose one of these options:

### Option A: Vercel (Recommended - Free)

1. **Install Vercel CLI:**
   ```bash
   npm install -g vercel
   ```

2. **Deploy:**
   ```bash
   vercel
   ```

3. **Follow the prompts:**
   - Set up and deploy: `Y`
   - Which scope: Select your account
   - Link to existing project: `N`
   - Project name: Press Enter (or choose a name)
   - Directory: Press Enter (./‌)
   - Override settings: `N`

4. **You'll get a URL like:**
   ```
   https://your-project-name.vercel.app
   ```

5. **For production deployment:**
   ```bash
   vercel --prod
   ```

### Option B: Netlify (Free)

1. **Build your app:**
   ```bash
   npm run build
   ```

2. **Deploy:**
   - Go to [Netlify Drop](https://app.netlify.com/drop)
   - Drag and drop the `dist` folder
   - You'll get a URL like: `https://your-app.netlify.app`

### Option C: GitHub Pages

1. **Install gh-pages:**
   ```bash
   npm install --save-dev gh-pages
   ```

2. **Add to package.json:**
   ```json
   "scripts": {
     "predeploy": "npm run build",
     "deploy": "gh-pages -d dist"
   }
   ```

3. **Deploy:**
   ```bash
   npm run deploy
   ```

---

## 🎨 Step 2: Embed in Your Website

Once deployed, use your app URL in the iframe code below.

### Basic Iframe Code

```html
<iframe 
  src="https://your-deployed-app-url.vercel.app" 
  width="100%" 
  height="800" 
  style="border: none; border-radius: 16px; max-width: 900px; display: block; margin: 0 auto;"
  scrolling="auto"
  title="Financial Fitness Test"
  allow="clipboard-write"
></iframe>
```

### Responsive Iframe (Recommended)

```html
<div style="position: relative; width: 100%; max-width: 900px; margin: 0 auto; padding-bottom: 120%; height: 0; overflow: hidden; border-radius: 16px;">
  <iframe 
    src="https://your-deployed-app-url.vercel.app" 
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none;"
    scrolling="auto"
    title="Financial Fitness Test"
    allow="clipboard-write"
  ></iframe>
</div>
```

---

## 🌐 Platform-Specific Instructions

### For Wix

1. **Open Wix Editor**
2. Click the **"+"** button (Add Elements)
3. Go to **"Embed"** → **"HTML iframe"**
4. Click **"Enter Code"**
5. Select **"Code"** tab
6. Paste this code:

```html
<iframe 
  src="https://your-deployed-app-url.vercel.app" 
  width="100%" 
  height="800" 
  style="border: none;"
  scrolling="auto"
  title="Financial Fitness Test"
></iframe>
```

7. Click **"Update"**
8. Resize the iframe element on your page as needed
9. **Publish** your site

**Wix Tips:**
- Set iframe height to at least 800px
- Enable scrolling if content is cut off
- Test on mobile preview before publishing

---

### For WordPress

1. **Edit your page/post**
2. Click the **"+"** button to add a block
3. Search for **"Custom HTML"** or **"HTML"**
4. Paste the iframe code:

```html
<div style="max-width: 900px; margin: 0 auto;">
  <iframe 
    src="https://your-deployed-app-url.vercel.app" 
    width="100%" 
    height="800" 
    style="border: none; border-radius: 16px;"
    scrolling="auto"
    title="Financial Fitness Test"
  ></iframe>
</div>
```

5. **Preview** and **Publish**

**WordPress Alternative (Shortcode):**

Add this to your theme's `functions.php`:

```php
function financial_fitness_test_shortcode() {
    return '<iframe src="https://your-deployed-app-url.vercel.app" width="100%" height="800" style="border: none; border-radius: 16px; max-width: 900px; display: block; margin: 0 auto;" scrolling="auto" title="Financial Fitness Test"></iframe>';
}
add_shortcode('financial_fitness_test', 'financial_fitness_test_shortcode');
```

Then use: `[financial_fitness_test]` in any page/post

---

### For Squarespace

1. **Edit your page**
2. Click an insert point and choose **"Code"**
3. Select **"HTML"**
4. Paste the iframe code
5. Click **"Apply"**
6. **Save** your page

---

### For Webflow

1. **Drag an "Embed" element** to your page
2. Paste the iframe code
3. Adjust the embed element size
4. **Publish** your site

---

### For Custom HTML Site

Simply paste the iframe code wherever you want the quiz to appear:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Financial Fitness Test</title>
  <style>
    body {
      margin: 0;
      padding: 20px;
      background: #f5f5f5;
    }
    .quiz-container {
      max-width: 900px;
      margin: 0 auto;
    }
  </style>
</head>
<body>
  <div class="quiz-container">
    <iframe 
      src="https://your-deployed-app-url.vercel.app" 
      width="100%" 
      height="800" 
      style="border: none; border-radius: 16px;"
      scrolling="auto"
      title="Financial Fitness Test"
    ></iframe>
  </div>
</body>
</html>
```

---

## 📱 Mobile Responsiveness

The quiz is already mobile-responsive. For best results:

1. **Use `width="100%"`** in the iframe
2. **Set minimum height:** 800px for desktop, auto-adjust for mobile
3. **Test on mobile devices** before going live

### Mobile-Optimized Embed:

```html
<style>
  .quiz-embed {
    width: 100%;
    height: 800px;
    border: none;
    border-radius: 16px;
    max-width: 900px;
    margin: 0 auto;
    display: block;
  }
  
  @media (max-width: 768px) {
    .quiz-embed {
      height: 1000px;
      border-radius: 0;
    }
  }
</style>

<iframe 
  class="quiz-embed"
  src="https://your-deployed-app-url.vercel.app" 
  scrolling="auto"
  title="Financial Fitness Test"
></iframe>
```

---

## 🔧 Advanced: Auto-Resize Iframe

For dynamic height adjustment, add this JavaScript to your parent page:

```html
<iframe 
  id="financial-quiz"
  src="https://your-deployed-app-url.vercel.app" 
  width="100%" 
  height="800" 
  style="border: none;"
  scrolling="auto"
  title="Financial Fitness Test"
></iframe>

<script>
  window.addEventListener('message', function(e) {
    if (e.data.type === 'resize') {
      const iframe = document.getElementById('financial-quiz');
      if (iframe) {
        iframe.style.height = e.data.height + 'px';
      }
    }
  });
</script>
```

---

## 🎯 Google Forms Integration (Future)

To integrate with Google Forms in the future:

1. Create a Google Form with matching questions
2. Use Google Apps Script to send data from the quiz to the form
3. Or export quiz results as CSV and import to Google Sheets

---

## ✅ Testing Checklist

Before going live, test:

- ✅ Quiz loads correctly in the iframe
- ✅ All questions display properly
- ✅ Progress bar works
- ✅ Results screen shows correctly
- ✅ Mobile view is responsive
- ✅ Contact form submission works
- ✅ Print functionality works

---

## 🆘 Troubleshooting

### Issue: Iframe not showing
**Solution:** Check if your hosting allows iframe embedding. Some hosts block iframes for security.

### Issue: Content is cut off
**Solution:** Increase the `height` attribute (try 1000px or 1200px)

### Issue: Scrolling doesn't work
**Solution:** Change `scrolling="no"` to `scrolling="auto"`

### Issue: Looks different in Wix
**Solution:** Wix adds its own styling. Use the "Code" embed option instead of "Website"

### Issue: Mobile view is broken
**Solution:** Ensure viewport meta tag is set and use responsive iframe code

---

## 📞 Support

For issues or questions, check:
- Browser console for errors
- Network tab to see if the app is loading
- Try opening the direct URL first to ensure the app works standalone

---

## 🎉 You're Done!

Your Financial Fitness Test quiz is now embedded and ready for users!

**Example URLs to test:**
- Development: `http://localhost:5173`
- Production: `https://your-app.vercel.app`
- Embed demo: Open `/public/embed.html` in your deployed app
