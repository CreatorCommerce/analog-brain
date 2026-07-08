---
name: analog-newsletter-email
description: Use this skill whenever the user asks to write, draft, generate, design, or turn content into an Analog newsletter email, The Blueprint email, field note digest, product/market update, community roundup, or copy-pasteable newsletter HTML. This skill creates final newsletter copy, production-oriented table HTML, and an asset hosting checklist. Do not use for one-to-one customer success emails, help articles, ads, or social posts.
---

# Analog Newsletter Email

Use this skill to create an Analog newsletter that can be sent as HTML.

The newsletter should feel like The Blueprint: useful field notes, product context, market signal, and founder/operator judgment. It should not feel like a generic SaaS blast.

## Source Order

If you have local repo access, read current styling and product context from:

1. `/Users/kenyonbrown/Documents/Analog/cc-analog/design.md`
2. `/Users/kenyonbrown/Documents/Analog/cc-analog/apps/analog-directory/src/styles/globals.css`
3. `/Users/kenyonbrown/Documents/Analog/cc-analog/apps/analog-directory/src/components/pages/analog-directory/AnalogDirectoryBlogPage.tsx`
4. `/Users/kenyonbrown/Documents/analog-brain/skills/email-content-skills.mdx`

Use the current `cc-analog` product language over older Analog references.

## Inputs

Ask for missing inputs only when they materially change the email.

Useful inputs:

- audience: Sponsors, Hosts, operators, partners, investors, or a mixed list
- goal: educate, drive replies, announce a product surface, recap field learning, or invite action
- key points
- links
- images or assets
- send date
- desired CTA
- sender name

When the user gives rough notes, turn them into a clean newsletter without asking for a polished brief.

## Newsletter Shape

Use this structure by default:

1. Subject line and preheader
2. Header with Analog wordmark and issue/date label
3. Editorial hero with one clear thesis
4. Short opening note
5. Two or three sections, each with a headline, body, and optional link
6. One product or field signal panel
7. One primary CTA
8. Simple footer with unsubscribe placeholder

Keep the email focused. One main idea should hold the whole issue together.

## Voice

Write like an operator explaining what changed and why it matters.

- concrete nouns over hype
- short paragraphs
- founder/operator clarity
- practical takeaways
- no generic "we are thrilled" openings
- no fake urgency
- no dense investor abstraction unless it changes what a pilot does next

Use Analog terms correctly:

- Sponsor funds campaigns
- Host creates events and uses sponsor budgets
- collab means a sponsor-host relationship inside one campaign
- spend card means a temporary operational Stripe Issuing card
- Event set means a campaign subgroup that owns market persona, special requests, files/assets, and prospecting
- Event Prospecting Catalog means the enriched, claimable IRL supply map

## Visual System

Translate the `cc-analog` UI into email-safe HTML.

Use:

- warm black: `#22201F`
- page white: `#FFFFFF`
- soft surface: `#F2F2F2`
- Analog yellow: `#FFF385`
- yellow hover/fallback: `#F2E76F`
- muted text: `rgba(34, 32, 31, 0.62)` or email-safe `#716D68`
- Poppins-like sans stack: `Poppins, Arial, Helvetica, sans-serif`
- Lora-like serif stack for editorial headings: `Lora, Georgia, Times, serif`
- rounded panels between `12px` and `24px`
- thin dividers: `#E1DEDA`
- underlined tertiary links

Avoid:

- CSS variables in final email HTML
- JavaScript
- forms
- video
- heavy box shadows
- background images for critical content
- negative letter spacing
- image-only copy
- nested card piles
- giant marketing hero layouts

## HTML Requirements

Return copy-pasteable email HTML.

- Use table-based layout for the outer shell and major rows.
- Keep width between `600px` and `640px`.
- Inline critical styles.
- Include a hidden preheader.
- Add `alt` text for every content image.
- Add explicit `width` attributes to images.
- Use bulletproof CTA links as styled anchors.
- Keep mobile styles inside a small `<style>` block.
- Keep unsubscribe and address placeholders editable.
- Do not use local file paths in production HTML.

## Brand Defaults

Use these footer and brand defaults unless the brief overrides them:

- Logo sources: `/Users/kenyonbrown/Documents/analog-brain/skills/email-assets/analogblack.png`, `/Users/kenyonbrown/Documents/analog-brain/skills/email-assets/analogyellow.png`, and `/Users/kenyonbrown/Documents/analog-brain/skills/email-assets/analogwhite.png`
- Dashboard link: `https://analog.host`
- Directory link: `https://analog.directory`
- Dashboard Instagram: `https://www.instagram.com/analog.host/`
- Directory Instagram: `https://www.instagram.com/analog.directory/`
- Dashboard X: `https://x.com/analog_host`
- Directory X: `https://x.com/analog_directory`
- Address: `565 Broadway St. Venice, CA 902921`

Use the black wordmark on white or soft gray sections, the white wordmark on warm black sections, and the yellow wordmark only when the background needs the high-contrast Analog brand mark.

## Asset Handling

Every generated newsletter must include an asset hosting checklist before the HTML.

Use this rule:

- If an image appears in the HTML, it needs a public `https://` URL before sending.
- Host the selected current Analog wordmark from `/Users/kenyonbrown/Documents/analog-brain/skills/email-assets/` and replace the placeholder with its public `https://` URL before sending.
- Hero images, community photos, product screenshots, maps, or sponsor logos should be uploaded to Cloudflare Images or the CreatorCommerce asset host.
- Never ship a `localhost`, `/images/...`, `file://`, or base64 image in final email HTML.
- If a needed asset is not hosted yet, leave a clear placeholder like `https://YOUR_HOSTED_IMAGE_URL` and list exactly what to host.

For each asset, list:

- asset purpose
- current source, if known
- required hosted URL
- recommended dimensions
- alt text

## Output Format

Return:

````text
Subject:
Preheader:

Asset hosting checklist:
- ...

HTML:
```html
...
```

Plain-text fallback:
...
````

If the user asks for only the HTML, still include the subject, preheader, and asset checklist above it unless they explicitly say not to.

## Quality Check

Before finalizing, verify:

- the subject names the concrete value of the issue
- the preheader adds context instead of repeating the subject
- the CTA is singular and obvious
- the HTML can be pasted into an email tool
- every image has a hosted URL or a hosting note
- the email reads well with images blocked
- all links are real or clearly marked placeholders

## Practice Preview

Use `assets/practice-newsletter.html` as the local preview and starting layout reference for a newsletter-style email.

## Test Prompts

- "Turn these notes about the first Sponsor workflow pilot into a Blueprint newsletter with send-ready HTML."
- "Write a monthly Analog field notes email for Hosts and Sponsors. Include a CTA to reply with their city."
- "Make a newsletter announcing a new Event Prospecting Catalog update, and tell me what images need to be hosted."
