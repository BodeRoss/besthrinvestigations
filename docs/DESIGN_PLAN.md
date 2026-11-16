# Design plan

Planning only. This document describes the visual design for the Best Human Resources Consulting website. It does not add pages, styles, scripts, packages, fonts, or a logo, and it does not change the static HTML, CSS, and JavaScript architecture in `docs/ARCHITECTURE.md`.

The visual direction in this document is approved. Website pages have not been built.

This approval covers design only. It is not Diane Ross’s final approval of the website content. Wording still comes from the current working copy in `docs/APPROVED_WEBSITE_COPY.md` and `docs/CONTENT_PLAN.md`. That copy can still change. See section 9.

The public name used here is **Best Human Resources Consulting**, with the subtitle **Professional Investigation Services for Employers**.

## 1. Overall visual direction

The site should feel professional, modern, trustworthy, approachable, and easy to navigate.

Approved page list:

1. Home
2. Services
3. Process
4. About
5. Contact

Every page uses the same header, navigation, and footer. Content sits in one centered column with a comfortable reading width. Sections alternate between white and light gray so the page has structure without decoration.

Keep the design quiet:

- No animation beyond ordinary link and button hover and a visible keyboard focus style
- No decorative illustrations, patterns, or stock photography
- No external images, icon fonts, or font services
- The only photograph is Diane Ross’s existing headshot

## 2. Color palette

Approved colors:

| Role | HEX | Use |
| --- | --- | --- |
| Navy | `#0E2744` | Headings, primary buttons, header background, footer background |
| Sage | `#3E6B62` | Text links, step numbers, secondary button border and label, header hover and current-page accent |
| White | `#FFFFFF` | Page background, cards, header business name, header navigation links, footer text |
| Light gray | `#F4F6F8` | Alternating section background, header subtitle |

Supporting colors below make those four readable. They are not a separate palette. Body text stays dark, and sage is not used as a pale tint for small text.

| Role | HEX | Use |
| --- | --- | --- |
| Ink | `#1C2430` | Body text |
| Secondary text | `#3E4A59` | Supporting lines |
| Sage wash | `#E6F0EE` | Quiet background behind the confidentiality notice only |
| Line | `#D5DCE3` | Card borders |

Checked contrast of the text pairs against their backgrounds:

| Pair | Contrast |
| --- | --- |
| Ink `#1C2430` on white | 15.6:1 |
| Navy `#0E2744` on white | 15.1:1 |
| Navy `#0E2744` on light gray `#F4F6F8` | 13.9:1 |
| Secondary text `#3E4A59` on white | 9.0:1 |
| Sage `#3E6B62` on white | 6.0:1 |
| Sage `#3E6B62` on light gray `#F4F6F8` | 5.6:1 |
| White on navy `#0E2744` | 15.1:1 |
| Light gray `#F4F6F8` on navy `#0E2744` | 13.9:1 |

These pairs meet WCAG 2.2 AA for normal text. The sage wash is a background, not a text color. Confirm the pairs again when the CSS is written.

## 3. Typography

Approved: use the system font stack. Do not use an external font service or download fonts.

`system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif`

Do not add files to `public/fonts/`.

| Element | Size | Weight | Line height |
| --- | --- | --- | --- |
| Page heading | 2rem, up to 2.5rem on wide screens | 650 | 1.2 |
| Section heading | 1.5rem | 650 | 1.3 |
| Card heading | 1.25rem | 650 | 1.3 |
| Body | 1.125rem (18px) | 400 | 1.6 |
| Subtitle and small supporting text | 1rem | 400 | 1.5 |
| Navigation and buttons | 1rem | 600 | 1.4 |

Keep line length near 65–75 characters. Left-align paragraphs and lists. Do not set body text in all caps. Sizes stay large enough to read on a phone.

## 4. Page structure

### Header and navigation

Approved header:

- Navy background, `#0E2744`
- Business name in white: Best Human Resources Consulting
- Subtitle in light gray, directly under the name: Professional Investigation Services for Employers
- Navigation links in white
- Sage `#3E6B62` for the current page and for hover
- Space reserved for a future logo
- The business name and subtitle stay visible when a logo is added

The header stays at the top of every page. It contains the brand and the navigation.

**Brand, from left to right:**

1. A reserved logo area.
2. The business name, linked to Home.
3. The subtitle.

The name and subtitle are the brand. The header looks finished with no logo. When a logo is added later, the name and subtitle remain on screen beside it.

**Reserved logo area**

Leave a horizontal slot to the left of the name, vertically centered with the name and subtitle. When a logo exists later, it is a separate image file in `public/images/`, referenced by a relative path. Display height is about 48px on desktop and 40px on a phone, with the file’s own width kept in proportion.

This plan does not create a logo, a placeholder image, or a logo filename. Until a file is supplied, the slot is empty and takes no visible space, so the name remains left-aligned. Adding the image later is an inserted element in that slot, not a redesign of the navigation.

**Navigation**

Approved links, in this order: Home, Services, Process, About, Contact.

The current page is marked with a sage background and a visually hidden “current page” label, so color is not the only cue. Links are white. Hover uses a sage underline. The current page uses a sage background with white text.

On a phone, use a simple accessible menu. The links sit behind a button labeled **Menu**. Activating it shows the same five links in a vertical list under the header. The button changes to **Close**. Keyboard users can reach every link and close the menu. Build that control with ordinary HTML and CSS. Do not add a framework or JavaScript for the menu.

There is one `h1` per page. The header brand is a link, not a heading.

### Home

Approved hero:

- `h1`: HR consulting and workplace investigations—done professionally.
- The business name and subtitle do not repeat in the hero. They stay in the header.

Also in the hero, from the working copy:

- Supporting paragraph: Helping organizations of all sizes and levels strengthen HR practices and handle workplace concerns with a clear, respectful, impartial process.
- Primary button: **Request a Consultation**, linking to the Contact page. Navy background, white text.
- Secondary button: **View Services**, linking to the Services page. White background, sage border and label.

**What We Do** follows on light gray. A short section heading, then two equal cards side by side:

- Workplace Investigations
- Consultation

Each card is white, with a navy heading, a short bulleted list, and a one-pixel line border. No icons. On a narrow screen the cards stack, Investigations first.

### Services

- `h1`: Services
- Intro paragraph from the working copy
- Two cards, stacked on small screens and side by side on a wide screen:
  - Workplace Investigations
  - Case Consultation
- Buttons at the end: **Request a Consultation** (primary) and **See Our Process** (secondary)

The card pattern matches Home so the two service pages feel related. The labels stay as written in the working copy: Home says Consultation; Services says Case Consultation.

### Process

- `h1`: Our 4-Step Process
- Intro paragraph from the working copy
- Four numbered steps in source order:
  1. Intake & Case Review
  2. Plan & Information Gathering
  3. Investigation & Documentation
  4. Findings, Recommendations & Next Steps

Each step shows the number in sage, then the step title and its three bullets. On a wide screen the four steps sit in one row. On a tablet they sit in two rows of two. On a phone they stack. Numbers stay visible so the sequence is clear without a connecting line or animation.

Buttons at the end: **Request a Consultation** and **View Services**.

### About

- `h1`: About
- Diane’s photograph and the About paragraph sit together. On a wide screen the photograph is on the left and the paragraph is on the right. On a phone the photograph comes first, then the paragraph.
- Then three text blocks, each a heading and a bulleted list, on a light gray band:
  - What Guides Our Work
  - How We Help
  - Who We Work With
- Buttons: **Talk to Us** (Contact) and **How the Process Works** (Process)
- Then **Meet Diane Ross**, after the existing About content. The five biography groups stay as separate headings, lists, and paragraphs. The photograph is not repeated there.

The photograph and the biography are both on the About page. Biography wording and credentials presentation are still waiting for Diane’s approval.

### Contact

- `h1`: Contact
- Introduction: We welcome the opportunity to discuss your organization's HR needs and workplace investigation requirements.
- The email address shown as text and as a `mailto` link: besthrconsultingservices@gmail.com
- **Request a Consultation** uses that same mailto link
- The confidentiality notice, in its own bordered sage-tinted area: Please do not include confidential employee information or sensitive case details in your initial message.

There is no contact form. A form is a possible future enhancement, not part of the current page. The biography is not on Contact.

### Footer

Approved footer:

- Navy background
- Links to Services, Process, About, and Contact
- Home stays available through the business name in the header, not as a footer link

Also show: © 2026 Best Human Resources Consulting — Diane Ross

Footer text is white. Footer links are underlined so they remain obvious on the navy background.

## 5. Image placement

Approved photograph:

| File | Type | Pixel size | File size |
| --- | --- | --- | --- |
| `public/images/diane-ross.png` | PNG | 400 × 400 | 219,394 bytes |

- Display it on the About page.
- On wide screens, place it beside the About paragraph. On a phone, place it above that paragraph.
- Display the full square. Do not crop it into a circle or cover the face with a color overlay.
- Do not display it larger than 400px on a side.
- A practical display size is 280–320px beside the About text on desktop, and up to the content width on a phone, still capped at 400px.
- Image description: “Diane Ross, Best Human Resources Consulting.”
- Keep the original file unchanged. Do not move, rename, edit, replace, or regenerate it.
- Do not use an externally hosted photograph.

No other images are planned. A future logo, if one is supplied, is a separate file added under `public/images/` later. It is not created here. The business name and subtitle stay visible next to it.

## 6. Mobile, tablet, and desktop

Approved: support phones, tablets, and desktop screens, with readable text and the accessibility practices in section 7.

Use normal document flow and CSS. Do not require a library or JavaScript.

| Viewport | Behavior |
| --- | --- |
| Phone, under 700px | Single column. Header brand stacks the name and subtitle. Menu button shows navigation. Buttons stack and are full width. Service cards and process steps stack. Photograph sits above the About paragraph, capped at 400px. |
| Tablet, 700px to 1023px | Content width grows. Service cards and process steps use two columns. Header can show the full navigation if the five links fit; otherwise keep the Menu button. |
| Desktop, 1024px and wider | Content column about 1080px, centered. Header is one row: brand on the left, navigation on the right. Service cards are two columns. Process steps are four columns. Photograph and About paragraph are side by side. |

Keep at least 16px of side padding on small screens. Buttons and nav links need a target at least 44px tall. Avoid horizontal scrolling.

## 7. Accessibility

- Body text is 18px with 1.6 line height.
- Text colors use the contrast pairs in section 2.
- Every page has one `h1`, then section headings in order.
- Navigation, buttons, and the email link are reachable by keyboard in the order they appear.
- Focus is a 2px navy outline, offset from the control, visible on white and on light gray. On the navy header and footer, the outline is white.
- The current page is indicated by more than color.
- The photograph uses the description in section 5. When a logo is added later, its description can be empty because the business name remains beside it and should not be announced twice.
- The email address is visible text, not only an icon.
- The confidentiality notice is real text in the page, placed with the email.
- Color is not the only way information is shown. Step order uses numbers. Lists use list markup.
- Do not autoplay motion. Honor a user’s reduced-motion setting by keeping hover changes to color only.
- Include a skip link as the first focusable item: “Skip to content.”

## 8. Approved design decisions

These decisions are approved. They are the visual direction to build from. They do not approve the website copy.

1. **Pages.** Five static pages: Home, Services, Process, About, and Contact.
2. **Palette.** Navy `#0E2744`, sage `#3E6B62`, white `#FFFFFF`, and light gray `#F4F6F8`.
3. **Type.** The system font stack in section 3. No external font service and no font download.
4. **Header.** Navy `#0E2744` background. Business name in white: Best Human Resources Consulting. Subtitle in light gray: Professional Investigation Services for Employers. Navigation links are white. Sage `#3E6B62` marks the current page and the hover state. Space is reserved for a future logo. The name and subtitle stay visible after a logo is added.
5. **Navigation.** Home, Services, Process, About, Contact. Simple accessible mobile navigation. No framework and no JavaScript for that menu.
6. **Home heading.** The main heading is “HR consulting and workplace investigations—done professionally.” The hero does not repeat the business name or subtitle.
7. **Photograph.** Use `public/images/diane-ross.png` on the About page. Preserve the original file. Do not display it larger than 400 × 400 pixels. The description is “Diane Ross, Best Human Resources Consulting.”
8. **Biography placement.** The complete biography is on the About page, after the photograph, introduction, approach, and buttons. Contact holds the consultation email and confidentiality notice. The layout must accommodate later wording changes. A contact form is not part of the current design.
9. **Footer.** Navy background. Links to Services, Process, About, and Contact. Home is reached through the business name in the header.
10. **Responsive layout.** Phones, tablets, and desktops, with readable text and the accessibility practices in section 7.

## 9. Content still awaiting Diane’s approval

Design approval does not approve the words on the site.

- `docs/APPROVED_WEBSITE_COPY.md` remains the current working copy.
- Diane’s final content approval is still pending.
- Biography wording and credentials presentation are still open, as recorded in `docs/CONTENT_PLAN.md`.
- Further content adjustments are not part of the working copy until they are added there.
- The layout in this plan is meant to absorb those wording changes without a redesign.
