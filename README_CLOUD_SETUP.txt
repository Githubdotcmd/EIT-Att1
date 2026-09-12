PROGRAMMING FUNDAMENTALS — SHARED CLOUD DATA SETUP

The 5 HTML pages keep their existing visual format and functionality. The new persistence layer stores landing-page settings and each section's students/settings/attendance in one Firebase Realtime Database so changes can be seen from different devices/browsers.

ONE-TIME SETUP
1. Create/open a Firebase project at https://console.firebase.google.com/
2. Create a Realtime Database.
3. For initial setup, use the database URL shown by Firebase (for example: https://YOUR-PROJECT-default-rtdb.firebaseio.com).
4. In Realtime Database Rules, allow the pages to read/write the required data. For a private production site, use Firebase Authentication and restricted rules; do NOT leave an unrestricted public database permanently.
5. Open pf-cloud-config.js and replace:
   window.PF_CLOUD_DB_URL = "https://YOUR-PROJECT-default-rtdb.firebaseio.com";
   with your actual database URL.
6. Keep pf-cloud-config.js in the same folder as index.html and all 4 section HTML files.
7. Open index.html. All 4 section links continue to open their original HTML pages.

DATA PATHS
programming_fundamentals/landing
programming_fundamentals/section_1A
programming_fundamentals/section_1B
programming_fundamentals/section_1C
programming_fundamentals/section_A2B2

The pages also keep local browser storage as an offline fallback. When the Firebase URL is configured, cloud data is loaded first and the pages poll the shared database every few seconds so changes made elsewhere become visible.
