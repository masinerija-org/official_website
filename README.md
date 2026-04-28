# MACHINERY Hugo Site

Hugo static site for the MACHINERY Data Science community.

## Project Structure

```
.
├── hugo.toml                    # Hugo configuration
├── content/
│   ├── _index.md               # About page content
│   └── meetups/                # 23 event markdown files
├── data/
│   └── organizers.json         # Organizer data
├── themes/machinery/           # Custom theme
│   └── layouts/
│       ├── _default/baseof.html
│       ├── index.html
│       └── meetups/
│           ├── list.html
│           └── single.html
├── static/                     # Static assets (served at site root)
│   ├── uploads/                # Logo
│   └── images/
│       ├── events/             # Event cover images
│       └── organizers/         # Organizer profile photos
├── .github/workflows/hugo.yml  # GitHub Actions deployment
└── hugo-preview.html           # Standalone browser preview
```

## Local Development

Install Hugo: https://gohugo.io/installation/

```bash
hugo server -D
```

Visit http://localhost:1313

## Deploy to GitHub Pages

### Option 1: GitHub Actions (Recommended — already configured)

1. Push this repo to GitHub
2. Go to repo **Settings → Pages**
3. Under **Build and deployment → Source**, select **GitHub Actions**
4. Push to `main` branch — the workflow at `.github/workflows/hugo.yml` builds and deploys automatically

The workflow uses `${{ steps.pages.outputs.base_url }}` so it works for both:
- User/org sites: `https://masinerija-org.github.io/`
- Project sites: `https://masinerija-org.github.io/REPO_NAME/`

### Option 2: Manual

```bash
hugo --minify
# Push contents of public/ to the gh-pages branch
```

## Verified Links

✅ GitHub: https://github.com/masinerija-org  
✅ LinkedIn: https://www.linkedin.com/company/machineryorg/  
✅ All 6 organizer LinkedIn profiles  
✅ All 23 event pages with cover images  

## Updating Content

### Add a new event

Create `content/meetups/YYYY-MM-DD-event-id.md`:

```markdown
---
title: "Event Title"
date: 2026-01-15T18:00:00+02:00
event_id: "12345"
venue_name: "Venue"
venue_city: "Belgrade"
going_count: 30
cover_image: "/images/events/12345.jpeg"
---

Event description...
```

Drop the cover image in `static/images/events/`.

### Update organizers

Edit `data/organizers.json`. Photos go in `static/images/organizers/`.
