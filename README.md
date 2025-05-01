# WebLDN Landing Page Maintenance Guide

This guide provides detailed instructions for maintaining and customizing the WebLDN landing page. Whether you're new to web development or need a quick reference, follow these steps to make common updates safely and effectively.

## Table of Contents
- [Updating Text and Styling](#updating-text-and-styling)
- [Managing Links](#managing-links)
- [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
- [Troubleshooting](#troubleshooting)

## Updating Text and Styling

### Header Section
The header contains the main navigation and logo. To modify:

1. **Logo Text**: Find this line and update "WebLDN":
```html
<a href="/" class="text-2xl font-bold text-blue-600">WebLDN</a>
```

2. **Navigation Items**: Located in the header's `<nav>` section:
```html
<div class="hidden md:flex space-x-8">
    <a href="#features">Features</a>
    <a href="#benefits">Benefits</a>
    <a href="#faq">FAQ</a>
    <a href="#contact">Contact</a>
</div>
```

### Hero Section
To update the main headline and subheading:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-6">
    Best Websites In London
</h1>
<p class="text-xl md:text-2xl text-gray-600 mb-12">
    Custom Websites For Your Business
</p>
```

### Tailwind CSS Class Guide
Common classes used throughout:
- `text-[size]`: Controls text size (e.g., `text-xl`, `text-2xl`)
- `font-[weight]`: Controls text weight (e.g., `font-bold`, `font-semibold`)
- `mb-[size]`: Adds margin bottom (e.g., `mb-6`, `mb-12`)
- `py-[size]`: Adds padding top and bottom
- `px-[size]`: Adds padding left and right

To modify spacing:
```html
<!-- Original -->
<div class="mb-6">

<!-- Increase spacing -->
<div class="mb-8">

<!-- Decrease spacing -->
<div class="mb-4">
```

## Managing Links

### Navigation Links
1. Internal section links use hashtags:
```html
<a href="#features">Features</a>
<a href="#benefits">Benefits</a>
```

2. External links need full URLs:
```html
<!-- Find this line -->
<a href="https://sigmaseo.io" class="hidden md:inline-block...">

<!-- Replace with your URL -->
<a href="https://your-domain.com" class="hidden md:inline-block...">
```

### Footer Links
The footer contains multiple link sections:

```html
<div>
    <h4 class="text-lg font-semibold text-white mb-4">Services</h4>
    <ul class="space-y-2">
        <li><a href="#" class="hover:text-white transition-colors duration-300">Web Design</a></li>
        <!-- Update href with actual URL -->
        <li><a href="/services/web-design">Web Design</a></li>
    </ul>
</div>
```

To update any footer link:
1. Locate the relevant `<a>` tag
2. Replace the `#` with your URL
3. Ensure the link text matches your destination

## Adding Privacy and Terms Pages

### Step 1: Locate Footer Legal Section
```html
<div>
    <h4 class="text-lg font-semibold text-white mb-4">Legal</h4>
    <ul class="space-y-2">
        <li><a href="#" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="#" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

### Step 2: Update Links
Replace the placeholder `#` with actual page links:
```html
<li><a href="/privacy.html" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="/terms.html" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

### Step 3: Create Matching Pages
Create `privacy.html` and `terms.html` in your root directory with matching styles:
```html
<!-- privacy.html example -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Privacy Policy - WebLDN</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
</head>
<body class="font-['Inter'] antialiased text-gray-900 bg-white">
    <!-- Copy header from index.html -->
    <!-- Add privacy policy content here -->
    <!-- Copy footer from index.html -->
</body>
</html>
```

## Troubleshooting

### Common Issues and Solutions

1. **Broken Navigation Links**
   - Ensure section IDs match exactly (case-sensitive)
   - Check for extra spaces in IDs
   - Verify hashtag prefix for internal links

2. **Responsive Design Issues**
   - Don't remove `md:` or `lg:` prefixes from classes
   - Keep the `container` class on parent elements
   - Maintain the existing grid structure in features and benefits sections

3. **Style Inconsistencies**
   - Copy exact class strings when duplicating elements
   - Maintain the same color classes (e.g., `text-blue-600`)
   - Keep hover states (`hover:`) on interactive elements

### Need Help?
- Review the Tailwind CSS documentation for class references
- Use browser inspector to examine existing elements
- Maintain backup copies before making significant changes
- Test all changes across different screen sizes

Remember to always test your changes in multiple browsers and screen sizes before deploying to production.