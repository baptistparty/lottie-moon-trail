# The Lottie Moon Trail

An 8-bit, Oregon Trail-style game based on the life of Charlotte "Lottie" Digges Moon
(1840-1912). One self-contained HTML file. No build step, no dependencies, plays on mobile.

Jon Whitehead - developer and prompt author, assisted by Claude.
From your friends at [Center for Baptist Leadership](https://centerforbaptistleadership.org).

## Publish it (GitHub Pages)

1. Create a public repo, e.g. `lottie-moon-trail`, and upload `index.html` (and this README).
2. Repo **Settings > Pages**: Source = "Deploy from a branch", Branch = `main`, folder = `/ (root)`.
3. The game goes live at `https://baptistparty.github.io/lottie-moon-trail/` in about a minute.
4. Optional custom domain: add it under Settings > Pages, then point a CNAME at
   `baptistparty.github.io` in your DNS.

## Turn on analytics

The game ships with analytics off. To enable:

1. Sign up free at [goatcounter.com](https://www.goatcounter.com) and pick a site code
   (for example `lottiemoon`, giving you `lottiemoon.goatcounter.com`).
2. In `index.html`, find near the top of the `<script>` block:

       const GC_CODE='';

   and set it to your code:

       const GC_CODE='lottiemoon';

3. Commit. Your dashboard at `https://lottiemoon.goatcounter.com` shows traffic plus
   these gameplay events:

   | Event path | Meaning |
   | --- | --- |
   | `/pick-difficulty` | Opened the difficulty screen |
   | `/start/easy` `/start/normal` `/start/hard` | Run started, by mode |
   | `/chapter/1-complete` ... `/chapter/6-complete` | Chapter finished |
   | `/game-over/health/ch4/normal` | Run ended, with cause, chapter, mode |
   | `/back-out/ch4` | Used a back-out after a death |
   | `/finish/normal` | Reached the 1912 ending |
   | `/ending/toy` | Took the Crawford Toy alternate ending |
   | `/legacy` | Viewed the legacy/score screen |
   | `/credits` | Viewed credits |
   | `/click/cbl` | Clicked the Center for Baptist Leadership link |

No cookies are set, no personal data is collected, and requests are skipped entirely
when the visitor's browser sends Do Not Track. Analytics do not report from the
claude.ai artifact preview, which blocks outside requests; they work once the page is
hosted.

### Alternatives

- **Cloudflare Web Analytics** - free, one script tag, but page views only, no custom events.
- **Plausible** or **Fathom** - about $9-14/month, hosted in the EU, custom events supported.
  If you use Plausible, its `window.plausible()` call can be dropped into the `track()`
  function alongside the GoatCounter line.
- **itch.io** - if you also publish the game there, you get play counts and
  pay-what-you-want support built in.
