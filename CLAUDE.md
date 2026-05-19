# coreylang.github.io — Resume Website

Personal resume website for Christopher "Corey" Lang, Software Engineer. Deployed via GitHub Pages at https://coreylang.github.io.

## Tech Stack

- **Plain HTML/CSS/JS** — no build system, no package manager, no framework
- **Tailwind CSS** loaded via CDN (`https://cdn.tailwindcss.com`)
- **Single file**: `index.html` contains both the interactive web view and the print-friendly version
- `Christopher_Corey_Lang_Resume.pdf` — downloadable resume PDF (kept in sync manually)
- `favicon.png` — site icon

## File Structure

```
index.html                         — entire site (web + print views)
Christopher_Corey_Lang_Resume.pdf  — downloadable resume
favicon.png                        — favicon
```

## How Job Entries Work

Job entries live inside `.job` divs within a `border-l-4 border-gray-300 pl-6 space-y-12` timeline container. Each entry follows this pattern:

```html
<div class="job relative">
  <div class="absolute -left-9 top-1 w-5 h-5 bg-COLOR-600 rounded-full border-4 border-white"></div>
  <time class="job-timeline text-xs text-gray-500 uppercase tracking-wide">YEAR – YEAR</time>
  <h3 class="text-xl font-semibold text-gray-800">COMPANY NAME</h3>
  <p class="job-title text-sm text-gray-600">ROLE — <a href="URL" target="_blank" class="text-blue-600">domain.com</a></p>
  <ul class="list-disc list-inside list-spaced text-gray-700 mt-2 text-sm">
    <li>Bullet point.<br/>
      <span class="tech-stack text-gray-400 text-xs">[Tech, Stack, Here]</span>
    </li>
  </ul>
</div>
```

The timeline renders newest-first (top to bottom). The dot color (`bg-COLOR`) is per-entry — no strict convention, but the most recent/active entry should stand out. The `parseResumeToJSON()` function in `<head>` extracts data using `.job`, `h3`, `time.job-timeline`, `p.job-title`, and `ul > li` selectors — preserve those class names.

There are **two** copies of each job entry: one in the interactive `<main>` (inside `.max-w-6xl`) and one in the print-only `<div class="hidden print:block">` section. **Always update both.**

## Current Employer

**Home Buyer Nation** — Corey is currently employed here (2025 – Present).
- Real estate web application, an alternative to Zillow
- Production domain: hbnation.co | Dev: dev.hbnation.co
- Stack: Laravel 11 (backend), VueJS (frontend), Tailwind CSS
- Brand color: `#2B3679` (deep navy blue)
- Role: Full-Stack Developer

## About The Status

The Status is an order status display application for service businesses (restaurants, food trucks, coffee shops, auto service shops). It displays real-time order progression on customer-facing TV monitors. Website: https://thestatus.dev.

- Real-time order tracking via WebSockets/polling
- Three customizable order statuses: Initial → In Progress → Complete
- Cross-platform mobile app: The Status Lite (Flutter/Dart, Android/iOS)
- React web dashboard (Vite, Tailwind CSS, JWT auth)
- RESTful API with dual auth: JWT for dashboard users, API keys for POS integrations via webhooks
- Stack: TypeScript, Express.js, Prisma ORM, MySQL, Node.js

Corey's role was Full-Stack Developer (2025–2026).

## About the Owner

- **Name**: Christopher "Corey" Lang (goes by middle name)
- **Location**: Shawnee, KS
- **Email**: coreylang.dev@gmail.com
- **Phone**: (913) 952-7686
- **GitHub**: https://github.com/coreylang
- **LinkedIn**: https://www.linkedin.com/in/corey-lang-2b3b28185/

## Job History (Chronological, Newest First)

| Company | Role | Years |
|---|---|---|
| Home Buyer Nation | Full-Stack Developer | 2025 – Present |
| The Status | Full-Stack Developer | 2025 – 2026 |
| AFCA | Senior Software Developer | 2025 |
| NovaTech | Web Developer Engineer | 2020 – 2025 |
| The Lead Group | Full Stack Developer | 2020 |
| AFCA | Senior Software Developer | 2011 – 2020 |
| Angell EYE | Senior Software Developer | 2009 – 2011 |
| Freelance | Contractor | 2000 – 2009 |

## Dot Colors (Timeline)

Each job has a colored dot. Currently assigned:
- Home Buyer Nation (current): `bg-teal-600`
- The Status: `bg-red-600`
- AFCA (2025): `bg-purple-600`
- NovaTech: `bg-blue-600`
- The Lead Group: `bg-green-600`
- AFCA (2011–2020): `bg-red-600`
- Angell EYE: `bg-orange-500`
- Freelance: `bg-orange-500`
- Personal Projects: `bg-yellow-400`
- Education dots: `bg-blue-500`, `bg-orange-500`

## Notes

- The `parseResumeToJSON()` function in the footer renders a JSON view of the resume — it scrapes the live DOM, so class names on `.job`, `h3`, `time.job-timeline`, `p.job-title` are structural, not cosmetic.
- Google Analytics is configured with tag `G-4GREHHVJ5K`.
- Lightning bolt animation runs via `setInterval` — cosmetic only, no functional impact.
- The footer copyright reads "© 2025" — update annually.
