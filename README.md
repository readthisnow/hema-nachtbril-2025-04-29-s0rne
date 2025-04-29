# Landing Page Maintenance Guide

This guide provides detailed instructions for maintaining and customizing the Nachtbril landing page. Whether you're new to web development or need a quick reference, follow these step-by-step instructions.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains the main navigation and logo. To modify:

1. **Logo Text:**
```html
<!-- Find this line in the header -->
<a href="/" class="text-2xl font-bold text-gray-800">Nachtbril</a>
```
- Replace "Nachtbril" with your desired text
- Adjust size using `text-2xl` (options: text-sm, text-base, text-lg, text-2xl, text-3xl)

2. **Navigation Links:**
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-gray-900 transition-colors">Kenmerken</a>
    <!-- Additional links -->
</div>
```
- Update text between `>` and `</a>`
- Maintain the class structure for consistent styling

### Hero Section
Located at the top of the page:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-6">
    Hema Nachtbril
    <span class="block text-blue-600 mt-2">Nu 10% Korting!</span>
</h1>
```
- Update heading text while keeping the `<span>` structure
- Adjust text size using the responsive classes:
  - `text-4xl`: Mobile devices
  - `md:text-5xl`: Medium screens
  - `lg:text-6xl`: Large screens

### Features Section
Each feature card follows this structure:
```html
<div class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-all transform hover:scale-105">
    <!-- Icon container -->
    <h3 class="text-xl font-semibold mb-4">Anti-Vermoeidheid Technologie</h3>
    <p class="text-gray-600">Nog maar enkele exemplaren beschikbaar...</p>
</div>
```
- Update heading text in `<h3>`
- Modify description in `<p>`
- Keep the class structure intact for animations and styling

## Fixing Broken Links

### Navigation Menu Links
Current links in the navigation:
```html
<a href="#features">Kenmerken</a>
<a href="#benefits">Voordelen</a>
<a href="#faq">FAQ</a>
<a href="https://nachtbril.com/shop">Bestel Nu</a>
```

To update:
1. Internal links (starting with #):
   - Match the `id` of the section you're linking to
   - Example: `href="#features"` links to `<section id="features">`

2. External links:
   - Replace `https://nachtbril.com/shop` with your shop URL
   - Always include `https://` or `http://`

### Call-to-Action Buttons
```html
<a href="https://nachtbril.com/shop" class="inline-block bg-blue-600...">
    Profiteer Nu van 10% Korting
</a>
```
- Update all instances of `https://nachtbril.com/shop`
- Maintain the class structure for styling

## Linking Privacy and Terms Pages

### Footer Links Section
```html
<ul class="space-y-2">
    <li><a href="#" class="text-gray-400 hover:text-white transition-colors">Privacy Policy</a></li>
    <li><a href="#" class="text-gray-400 hover:text-white transition-colors">Algemene Voorwaarden</a></li>
</ul>
```

To add proper links:
1. Create privacy.html and terms.html in your root directory
2. Update the href attributes:
```html
<li><a href="privacy.html" class="text-gray-400 hover:text-white transition-colors">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-white transition-colors">Algemene Voorwaarden</a></li>
```

## Troubleshooting

### Common Issues:

1. **Broken Layout:**
   - Check if all Tailwind CSS classes are spelled correctly
   - Verify the Tailwind CDN link is working:
   ```html
   <script src="https://cdn.tailwindcss.com"></script>
   ```

2. **Animations Not Working:**
   - Ensure AOS script is properly loaded:
   ```html
   <script src="https://unpkg.com/aos@next/dist/aos.js"></script>
   ```
   - Verify initialization:
   ```html
   <script>
       AOS.init({
           duration: 1000,
           once: true
       });
   </script>
   ```

3. **Links Not Working:**
   - Check for typos in href attributes
   - Verify file paths are correct
   - Ensure section IDs match their corresponding links

### Need Help?
- Double-check class names against [Tailwind CSS documentation](https://tailwindcss.com/docs)
- Verify all scripts are loading in browser developer tools
- Test all links after making changes

Remember to always test your changes across different devices and screen sizes to ensure responsive design remains intact.