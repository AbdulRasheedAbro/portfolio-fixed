# Fix log: abdulrasheedabro.github.io/my-portfolio

Audited from the GitHub source (main + gh-pages branches), contrast calculated, repo links requested, build verified.
Items marked [PHONE] must be confirmed by you on a real phone before submitting.

| # | Where | Broken | Changed | Verified |
|---|-------|--------|---------|----------|
| 1 | vite.config.js, Hero, Navbar | Source used root paths (/profile.jpg, /resume.pdf) with no `base`; the live build only worked because it differed from `main`. Redeploying from main would 404 the photo and resume. | Set `base: '/my-portfolio/'`; all asset paths use `import.meta.env.BASE_URL` | Build output contains /my-portfolio/profile.jpg and /resume.pdf |
| 2 | index.html | Favicon was the default Vite logo at /vite.svg (404 on Pages) | Own favicon.svg via %BASE_URL% | Build output |
| 3 | Navbar resume modal | Resume opened in an iframe; phone browsers render PDFs in iframes as a blank box | Under 768px the resume opens in a new tab instead | [PHONE] |
| 4 | Mobile menu button | Hamburger icon had no padding (~22px tap target) | Added padding (~46px target) | [PHONE] |
| 5 | Hero social icons | 40px tap targets | 44px | [PHONE] |
| 6 | All components | Muted text #5B6270 = 3.2:1 contrast (fails AA 4.5:1) | Changed to #808998 (~5:1) | Calculated |
| 7 | public/profile.jpg | 900x900, 118 KB, shown at 240px | Resized to 480x480 (still crisp at 2x), 34 KB; added width/height | File size |
| 8 | 7 components | Google Fonts @import repeated in 7 inline <style> blocks (render-blocking, duplicate requests) | One preconnect + one stylesheet link in index.html | Build output |
| 9 | index.html | No meta description / theme colour | Added both | Build output |
| 10 | index.css | Smooth scroll ignored reduced-motion; no global focus style | Added reduced-motion rule and :focus-visible outline | Build output |
| 11 | src/ | Dead starter files (App.css, Index.css, react.svg, vite.svg) | Deleted | Build passes |
| 12 | Hero | min-h-screen overshoots behind mobile browser bars | Added 100svh | [PHONE] |

## Links checked
All 6 project repo links return 200. Email and phone links are well-formed. Certifications use '#' placeholders (rendered hidden, not broken): add real certificate URLs if you have them.
