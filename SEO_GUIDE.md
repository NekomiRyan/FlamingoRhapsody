# SEO & Google Search Console Guide

To ensure **Flamingo Rhapsody** appears on Google, follow these steps:

## 1. Google Search Console (GSC)
You need to tell Google that your site exists.

1.  Go to [Google Search Console](https://search.google.com/search-console).
2.  Log in with your Google account.
3.  Click **Add Property**.
4.  Enter your URL: `https://flamingorhapsodyinfo.web.app` (use the **URL Prefix** option).
5.  It might auto-verify since you are using Firebase/Google services. If not, it will ask you to verify ownership (you already have a `google-site-verification` tag in your HTML, so it should work).

## 2. Submit Sitemap
Once verified in GSC:

1.  Go to **Sitemaps** in the left menu.
2.  Enter `sitemap.xml` in the "Add a new sitemap" box.
3.  Click **Submit**.

Google will now crawl your site.

## 3. What We Did
-   **Sitemap**: Created `public/sitemap.xml` listing your site.
-   **Robots.txt**: Created `public/robots.txt` telling Google where the sitemap is.
-   **Structured Data**: Added "JSON-LD" code to `index.html`. This tells Google that "Flamingo Rhapsody" is an Educational Organization with specific members. This helps with "Knowledge Graph" cards in search results.
-   **Meta Tags**: Improved the description to include keywords like "Australia" and "FLL".

## 4. Timeline
It can take **a few days to a few weeks** for Google to index a new site. Be patient!
