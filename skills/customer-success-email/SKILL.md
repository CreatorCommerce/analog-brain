---
name: analog-customer-success-email
description: Use this skill whenever the user asks to write, draft, generate, design, or turn notes into an Analog customer success email, customer support reply, Host follow-up, Sponsor follow-up, onboarding email, claim-listing nudge, activation next step, renewal check-in, proof request, or copy-pasteable one-to-one HTML email. This skill creates concise success email copy, production-oriented HTML, and an asset hosting checklist. Do not use for newsletters, help articles, ads, or social posts.
---

# Analog Customer Success Email

Use this skill to create an Analog customer success email that can be sent as HTML.

The email should feel personal, operational, and useful. It should help a Host, Sponsor, partner, or customer take the next step without making the message feel like a newsletter.

## Source Order

If you have local repo access, read current styling and product context from:

1. `/Users/kenyonbrown/Documents/Analog/cc-analog/design.md`
2. `/Users/kenyonbrown/Documents/Analog/cc-analog/apps/analog-directory/src/styles/globals.css`
3. `/Users/kenyonbrown/Documents/Analog/cc-analog/apps/analog-directory/src/components/pages/analog-directory/DirectorySubscriberSignup.tsx`
4. `/Users/kenyonbrown/Documents/analog-brain/skills/email-content-skills.mdx`

Use current `cc-analog` product language and Analog Brain terminology.

## Inputs

Useful inputs:

- recipient type: Host, Sponsor, partner, applicant, community lead, or internal operator
- relationship stage
- reason for email
- desired action
- deadline, if real
- links
- context from the account, collab, Event set, or campaign
- sender name and signature
- whether the message should sound warm, direct, apologetic, celebratory, or procedural

If the user gives rough notes, produce a clean email without requiring a full brief.

## Customer Success Shape

Use this structure by default:

1. Subject line and preheader
2. Greeting
3. One sentence that names why the email is being sent
4. Short body with the relevant context
5. Clear next step or checklist
6. One primary CTA or reply request
7. Human sign-off
8. Quiet footer

Keep it shorter than a newsletter.

## Voice

Write like a capable human who knows the account.

- warm but not gushy
- specific and plain
- one job per email
- short paragraphs
- no fake deadlines
- no "just checking in" unless the user explicitly wants that phrase
- no overexplaining product strategy
- no help-article style headings unless the email genuinely needs a checklist

When the email is about a problem, name the problem plainly and give the next action. Do not bury the ask.

## Visual System

Translate the `cc-analog` UI into email-safe HTML.

Use:

- warm black: `#22201F`
- page white: `#FFFFFF`
- soft surface: `#F2F2F2`
- Analog yellow: `#FFF385`
- muted text: `#716D68`
- Poppins-like sans stack: `Poppins, Arial, Helvetica, sans-serif`
- Lora-like serif stack for rare warm headings: `Lora, Georgia, Times, serif`
- a simple white body with one soft gray panel when useful
- underlined links for secondary actions

Avoid:

- big editorial heroes
- multiple feature cards
- dense image layouts
- CSS variables
- JavaScript
- forms
- unnecessary icons
- content that reads like marketing automation when it should read like a human follow-up

## HTML Requirements

Return copy-pasteable email HTML.

- Use table-based layout for the outer shell and major rows.
- Keep width between `560px` and `600px`.
- Inline critical styles.
- Include a hidden preheader.
- Add `alt` text for every image.
- Use one primary CTA at most.
- Make reply-based CTAs acceptable when there is no link.
- Keep unsubscribe/address placeholders editable if the email is sent through a marketing tool.
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

Most customer success emails should need only the Analog wordmark.

Every generated email must include an asset hosting checklist before the HTML:

- Host the selected current Analog wordmark from `/Users/kenyonbrown/Documents/analog-brain/skills/email-assets/` and replace the placeholder with its public `https://` URL before sending.
- Product screenshots, claim-page previews, sponsor logos, proof images, or event photos must be hosted on Cloudflare Images or the CreatorCommerce asset host.
- Never ship `localhost`, `/images/...`, `file://`, or base64 images in final email HTML.
- If an asset is not hosted yet, leave a clear placeholder and list exactly what to upload.

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

If the user asks for a reply rather than HTML, still offer the HTML version when the email is intended to be sent through a campaign or lifecycle tool.

## Quality Check

Before finalizing, verify:

- the first sentence explains why the recipient is getting the email
- the ask is visible without scrolling much
- the CTA matches the real workflow
- no link is fake unless clearly marked as a placeholder
- the message works if images are blocked
- the email is not pretending to be a newsletter
- the HTML is paste-ready

## Practice Preview

Use `assets/practice-customer-success.html` as the local preview and starting layout reference for a customer success email.

## Test Prompts

- "Write a Host follow-up email asking them to claim their Analog community page and give me paste-ready HTML."
- "Draft a Sponsor success email summarizing what happened after an event collab and asking for approval on the next Event set."
- "Make a warm but concise email to a community lead whose page needs better photos, and tell me what assets need hosting."
