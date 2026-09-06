# Codex operating instructions — Contractor Website V5.3

These instructions apply to every Codex task in this repository.

## Mission and authority

Build and maintain a truthful, distinctive, accessible, fast contractor website. Keep implementation complexity away from the owner, but show every owner decision, uncertainty, failed gate, and publishing risk.

Use evidence in this order:

1. Explicit owner approval in the current task.
2. `handoff/APPROVED_BUILD_BRIEF.md` and `handoff/DESIGN_LOCK.json`.
3. Approved public facts in `handoff/PUBLIC_BUSINESS_FACTS.json`.
4. The current production website in `public/`.
5. The connected V5.3 Contractor Website Program source and private business-assets source, when available in the current context.

Never invent a business fact. A missing or conflicting fact is a blocker for that claim, not permission to guess.

## Path boundaries

Ordinary website work may edit:

- `public/`;
- the four `handoff/` files, but only when the owner has approved the public facts, old URL plan, or decisions being recorded.

Do not edit these protected paths unless the task explicitly requests course-infrastructure maintenance:

- `.github/`
- `functions/`
- `infrastructure/`
- `scripts/`
- `templates/`
- `tests/`
- `website.zip`
- `AGENTS.md`

Never commit the private business-assets source, raw review evidence, owner interview notes, originals, license or insurance scans, permits, invoices, estimates, staff or customer data, jobsite details, source-of-truth records, account credentials, or private keys.

## Build contract

- Work on a branch and request review. Do not push ordinary desktop website work directly to `main`.
- Edit real files in `public/`; the root ZIP is only the approved phone transport route.
- Treat the committed starter `public/` as a disposable safety shell, never as a visual template. For the first production build, remove every starter-only page and asset and create the real website from a blank canvas.
- Do not preserve or imitate the safety shell's page list, markup, class names, layout, colors, typography, components, CSS, or JavaScript. Derive the entire visual system from the contractor's approved facts, trade, customers, proof, service area, media, and inferred business vibe.
- Original local fonts, SVG artwork, icons, textures, imagery, animation, and JavaScript are welcome when they support the contractor's distinct character, remain accessible and performant, and pass the public-output policy.
- Preserve the owner-approved Design Lock unless the owner approves a redesign.
- When replacing an existing website, use `handoff/LEGACY_URL_PLAN.json` and preserve every old public URL at the same path by default. Use a permanent redirect only when its exact source and destination are owner-approved. Never send a collection of old pages to the homepage.
- Treat services, service areas, address publication, telephone numbers, hours, emergency or 24/7 availability, response times, prices, financing, warranties, licenses, insurance, bonding, certifications, years in business, reviews, awards, and project claims as evidence-sensitive.
- Default the primary actions to **Call** and **Request an Estimate** when those routes are confirmed. Never imply that a form is monitored continuously.
- Use semantic HTML, keyboard access, visible focus, readable contrast, useful alt text, reduced-motion behavior, responsive layouts, and one clear `h1` per page.
- Give each genuinely distinct, owner-confirmed service enough useful HTML content to help a customer decide. Do not create mass-produced or near-duplicate city pages. A service-area page must describe real coverage and customer needs, not swap place names into duplicated copy.
- For a service-area business, do not publish a private or home address. Publish an address only when the owner confirms that customers may visit it and explicitly approves public use.
- Publish credentials, reviews, before-and-after media, project galleries, warranty terms, and financing statements only from a recorded source with owner approval. Keep raw evidence private.
- Declare every public PDF or calendar file in the manifest `public_documents` list with an existing link, purpose, and owner approval.
- Keep video external and declare every exact external media URL, accessibility treatment, owner approval, poster, page, and CSP host.
- Do not add analytics, advertising pixels, chat widgets, embeds, or marketing forms without owner approval and the necessary privacy decision.
- Keep form recipients and secrets in the deployment environment. A Turnstile widget action must exactly match `TURNSTILE_EXPECTED_ACTION`.

For every production change, keep `site-manifest.json` and `version.json` synchronized. The V5.3 course intentionally retains repository compatibility with schema version `2.1`, workflow version `5.2`, and repository package spec `5.2`; do not bump those values in an individual business build. Each manifest page uses a canonical relative `file_path` plus root-relative `url_path` and `canonical_url_path`. Keep the complete generated favicon family declared and linked from every HTML page.

GitHub `main` is the final website source of truth and Cloudflare Pages is the final host. A ChatGPT Sites URL may be used only as a temporary design preview. Never describe a ChatGPT Sites preview as the finished launch, and never replace the GitHub-to-Cloudflare final path with it.

## Required gate before review

From the repository root, run:

```bash
python3 scripts/release_check.py
python3 scripts/validate_site.py public --mode production --repo-root .
```

Also inspect the site at common phone and desktop widths. Test navigation, click-to-call, request-an-estimate, contact fallback, services, service-area explanations, applicable proof links, forms, keyboard use, reduced motion, and the 404 page. If forms or external media are enabled, state that live delivery/reachability remains pending until its activation rehearsal passes.

## Review handoff

Before asking the owner to merge:

1. Summarize the visible change in plain language.
2. List every changed business fact and its approval source.
3. Provide current phone and desktop screenshots of changed page types.
4. Report exact automated and interaction test results.
5. Identify deferred optional work and every external live gate.
6. Include a rollback note for risky changes.

Do not say the website is complete while any required approval, production check, or live activation gate is unresolved.
