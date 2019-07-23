# THE PLAID AGENCY Launch Checklist
The following pages will outline the general guidelines that involve checking a website before we deem it ready for launch. This will includes a checklist of items as well as best practices to consider for every website. This is a working document and will be updated as new changes are necessary.

## General Launch Checklist

### Transactional Email

All Wordpress websites must install and configure the official [Sendgrid](https://wordpress.org/plugins/sendgrid-email-delivery-simplified/) plugin.

An API key will need to be created for the website at [Sendgrid.com](https://sendgrid.com/) and then configured in the plugin. Credentials for our Sendgrid account are available in Keepass.

In addition to the API Key, [Sending Domain Authentication](https://sendgrid.com/docs/ui/account-and-settings/how-to-set-up-domain-authentication/) will need to be set up in order to ensure email has a high deliverability rate. We'll need access to the DNS for the website to add the required values. Make sure to always complete this step if possible!

Finally, ensure that all forms on the website use `wordpress@websitename.com` as the Sending Address. For the Sending Name, make sure to use the exact name of the website as it is written in Wordpress (i.e. Website Name). Make sure to configure these settings in Sendgrid's plugin settings page, Ninja Forms, Contact Form 7, and any other plugins that might send email.

### Image Optimization

Ensure that all images have been optimized before a website goes live. Ideally this should be done as new images are added during development, but please run any NEW images through an optimizer when adding to existing pages/websites.

- JPEG: [JPEGMini](http://www.jpegmini.com/main/shrink_photo)
- PNG: [TinyPNG](https://tinypng.com)

Running an image through these optimizers can lower the file size by 75%+ which is a HUGE improvement on load times and keeps the websites fast.

### Asset Optimization (CSS / Javascript Files)

Similar to imagery, all assets included on a website should always be the minified, optimized versions.

Example: If you have an option of including jquery.js or jquery.min.js, go with the .min version. Another example: bootstrap.css or bootstrap.min.css? Always the .min.

Combine multiple JS and CSS files into a single minified JS and CSS file if possible. AVADA includes an option to combine files under the `Theme Options > Performance` tab.

### Website Code / Link Validation

Run the website through these tools tools:

- HTML: [W3C HTML Validator](https://validator.w3.org)
- CSS: [W3C CSS Validator](https://jigsaw.w3.org/css-validator)
- Links: [W3C Link Checker](https://validator.w3.org/checklink)

These tools can run websites through to check to make sure the HTML and CSS are “valid” in that they have no errors or warnings, which helps improve SEO and performance.

Keep in mind that it isn’t always possible to get rid of all warnings or errors, these are just general guidelines and best practices. A lot of warnings can and should be ignored.

### Mobile Friendly / Page Speed

Google provides a test to run the site through to ensure it is mobile friendly. This will test for site speed as well as a number of mobile checks:

- Mobile Test: [Google Mobile Friendly Tester](https://search.google.com/search-console/mobile-friendly)

Ensure that every website and page is mobile friendly (doesn’t break).

Google rewards mobile friendly websites with better SEO results.

### Browsers & Devices

In addition to the mobile checks above, it’s a good idea to test the site on various available devices, browsers, and operating systems.

Each of the following browsers is worth testing separately as they use unique rendering engines which may slightly differentiate how a website looks:

- Google Chrome (Blink rendering engine)
- Mozilla Firefox (Gecko rendering engine)
- Safari (Webkit rendering engine)
- Microsoft Edge (EdgeHTML rendering engine)

The following devices are worth testing as well:

- Phones
- Tables
- Landscape / Portrait View
- Multiple browser check on mobile (use the above list)

### SEO Content

Does every page on the website have a unique title tag and meta description? While all the content on your website should be optimized for search, the most important elements are:

- Page Titles
- Meta descriptions
- Headings (h1,h2,h3, etc)
- Body content
- Image titles and alt text
- URLs (no broken links, human-readable links like /test instead of /test.php).
- Website includes a Favicon (little icon in the address/bookmark bar).

### Forms

Ensure all forms are working, provide validation, and send to the correct email addresses with the appropriate information included.

## Extra Guidelines

### Image Dimension Guidelines

In addition to image optimization, we must consider image dimensions and size before adding them to a page:

- Images that need to spread the entire width of the screen will generally be no larger than 1920px wide, as this is the most common monitor width.
- Smaller images that fill content areas are usually less than or equal to 1000px in width, as this is usually the max width of the content area.
- Images that would help fill in content areas (½ or ⅓ of content area width) can generally be around 480px in width.

Logos will usually be SVG files, which are small vector files that work at any resolution.

### SSL

If possible, ensure the site is secured with SSL (green lock icon in browser).

Secure websites provide better SEO than those that remain insecure.

Chrome (and possibly other browsers) will actually warn against pages that aren’t secure in the future if they have any way of taking or processing money, so this is something to keep in mind.

### Google Analytics

Ensure that Google Analytics is installed and configured for the new website.

Add the office IP address to an exclusion filter on GA so that we aren’t tracking our own traffic to the website.

- [https://support.google.com/analytics/answer/1034823](https://support.google.com/analytics/answer/1034823)
- [http://whatismyipaddress.com](http://whatismyipaddress.com)

### XML Sitemaps

XML Sitemaps are files that contain links to every page on the site. They exist to help Google and other search engines index the site appropriately.

- [XML Sitemap Explanation](https://support.google.com/webmasters/answer/156184?hl=en)

XML sitemaps are saved as sitemap.xml in the root directory of the web server.

XML Sitemaps can be generated automatically with various tools:

- [Google XML Sitemap Generator](https://code.google.com/archive/p/sitemap-generators/wikis/SitemapGenerators.wiki)

XML Sitemaps should be submitted to Google and other search engines manually if large changes are made. Otherwise these changes will happen organically:

- Sign in to Google Webmaster Tools.
- Click "Add a Site."
- Enter the URL for your company (e.g. `http://www.yourdomain.com`). Click "Continue."
- Click "Crawl" on the left-hand side of the page, and choose "Sitemaps."
- Click "Add/Test Sitemap."
- Enter sitemap.xml after `http://www.yourdomain.com/`.
- Click "Submit Sitemap."

### 301 Redirects and 404s

Old URLs that no longer exist should have a 301 redirect to direct them to a new location if a user visits these links.

Make sure there is a working 404 page as well.
