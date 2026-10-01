# UKZNTechSocietyWebsite
Website for UKZN Tech Society
Author

Built and maintained by Abigail Moonsamy, 2026 STEM Director, UKZN Tech Society.

Tech used:

HTML5, CSS3 (grid, clip-path, custom properties, color-mix), vanilla JavaScript (ES6+)
Canvas 2D API for the hero animation
Inline SVG for the campus map
Google Visualization API (gviz) to read the Google Sheet

Features
Google Sheets as a CMS: content is read from a published Google Sheet via the gviz JSON endpoint and rendered client-side. Separate tabs for Site text, Campuses, Events, Team and Gallery.
Interactive hero card: a canvas dot-grid animation with a simple physics model (dots react to the cursor, scatter on a fast swipe, spring back).
Dynamic campus network map: an SVG ring that auto-spaces itself for any number of active campuses. Flip a campus from planned to active in the sheet and it appears everywhere automatically.
Department-coloured team cards: committee grouped by department, each in its own colour, with a 3D tilt effect and per-person LinkedIn links.
Pixel-art event calendar: a month grid marking event days, alongside poster-style event bars with filtering by campus.
Event update system: badges and dismissible banners announce venue/time/date changes, postponements and cancellations, remembered per device via localStorage.
Event posters open full-screen on demand.
Reflows to a single column on phones with a hamburger menu.
SEO:page title, meta description and Google Search Console verification.

One HTML file. No framework, no build step, no server. Open it in a browser and it runs. All the content is fetched at load time from a Google Sheet that acts as a lightweight content management system. Editing the sheet updates the site; no redeploy needed.
This was a deliberate design choice on my end because the people who maintain the site after me may not be developers, so the day-to-day editing had to be a spreadsheet, not a codebase.

EDITING GUIDE
       1. <style> ........ how everything LOOKS (colours, sizes, spacing)
       2. <body> ......... the PAGE STRUCTURE (header, the 5 tabs, footer)
       3. <script> ....... the LOGIC (pulls content from the Google Sheet)

     WHERE DOES THE TEXT COME FROM?
     Almost nothing is typed into this file. The events, team, gallery, about
     text, etc. all come LIVE from the Google Sheet. To change that content you
     edit the SHEET, not this file. This file only controls layout and styling.

     HOW TO FIND A SECTION:
     Use your editor's Find (Ctrl+F / Cmd+F) and search for these tags. Every
     major part is labelled with a >>> SIGNPOST <<< comment:

       >>> HERO           the big "One society. Two campuses." block up top
       >>> HERO HEADING   the exact headline text/logic
       >>> HERO TEXT      the paragraph under the headline
       >>> GALLERY CAROUSEL   the scrolling photo strip on home
       >>> ABOUT          the "What the Tech Society actually is" section
       >>> VISION         the "Our vision" block
       >>> EVENTS PAGE    the events tab (calendar + list)
       >>> TEAM PAGE      the meet-the-team tab
       >>> GALLERY PAGE   the full gallery tab
       >>> JOIN PAGE      the membership / form tab
       >>> HEADER         the top nav bar + logo
       >>> FOOTER         the bottom bar
       >>> SHEET FETCH    where the code reads the Google Sheet  (advanced)
       >>> COLOURS        the master colour list  (in <style>)
