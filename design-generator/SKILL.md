---
name: design-generator
description: "Generate websites and web interfaces in specific design styles using pre-built design systems. Actions: generate, create, build, make, design a website/landing page/app interface in [style] style. Styles include: Apple, Spotify, NVIDIA, Stripe, OpenAI, Figma, Linear, Notion, Vercel, GitHub, Tesla, Uber, PlayStation, SpaceX, and 50+ more. Triggers on: '生成xx风格的网站', 'create a spotify-style interface', 'make a apple-like landing page', 'build in [brand] design language', 'design in the style of [company]'. Use when user wants production-ready UI code that faithfully recreates a specific brand's design aesthetic."
---

# Design Generator

IRON LAW: NEVER apply generic AI aesthetics (purple/blue gradients, Inter font, rounded card grids) — follow the design system EXACTLY as specified.

## Workflow

Copy this checklist and check off items as you complete them:

```
Design Generator Progress:

- [ ] Step 1: Identify Design Style ⚠️ REQUIRED
  - [ ] 1.1 Parse user's requested style
  - [ ] 1.2 Search references/designs/ for matching .md file
  - [ ] 1.3 Load the matched design system
- [ ] Step 2: Analyze Design System ⛔ BLOCKING
  - [ ] 2.1 Extract color palette and roles
  - [ ] 2.2 Extract typography rules
  - [ ] 2.3 Extract component styles (buttons, cards, inputs)
  - [ ] 2.4 Extract layout and spacing principles
  - [ ] 2.5 Extract Do's and Don'ts
- [ ] Step 3: Generate Code ⚠️ REQUIRED
  - [ ] 3.1 Apply colors exactly as specified (hex codes, no approximations)
  - [ ] 3.2 Apply typography exactly (font families, sizes, weights, letter-spacing)
  - [ ] 3.3 Apply component styles (border-radius, shadows, padding)
  - [ ] 3.4 Apply layout principles (spacing scale, grid, whitespace)
- [ ] Step 4: Validate Output ⚠️ REQUIRED
- [ ] Step 5: Present to User ⚠️ REQUIRED
```

## Step 1: Identify Design Style ⚠️ REQUIRED

### 1.1 Parse User's Requested Style

Ask: What brand or style did the user request?

Common patterns in user requests:
- "Apple 风格" → Apple
- "Spotify 风格" → Spotify
- "Stripe 风格" → Stripe
- "创建一个 NVIDIA 风格的页面" → NVIDIA
- "用 Linear 的设计风格" → Linear

### 1.2 Search for Matching Design File

Search in `references/designs/` directory. The structure is:
```
references/designs/
  AI&LLMPlatforms/      (OpenAI, Anthropic, xAI, Cohere, etc.)
  Automotive/           (Tesla, etc.)
  Backend&DevOps/       (Vercel, Railway, etc.)
  Design&CreativeTools/ (Figma, Framer, etc.)
  DeveloperTools&IDEs/  (GitHub, VS Code, etc.)
  E-commerce&Retail/    (Shopify, Amazon, etc.)
  Fintech&Crypto/       (Stripe, Coinbase, etc.)
  Media&ConsumerTech/   (Apple, Spotify, NVIDIA, etc.)
  Productivity&SaaS/    (Linear, Notion, Slack, etc.)
```

Search for a .md file whose name matches the requested style. Case-insensitive matching.

### 1.3 Load the Matched Design System

If found: Load the entire file into context.
If not found: Ask the user to choose from available styles (list categories and sample names).

**Available styles (66 total):**
- AI&LLMPlatforms: OpenAI, Anthropic, xAI, TogetherAI, Cohere, MistralAI, Ollama, ElevenLabs, Runway, MiniMax, OpenCode, VoltAgent
- Automotive: Tesla
- Backend&DevOps: Vercel, Railway, Supabase, Cloudflare, DigitalOcean, Render
- Design&CreativeTools: Figma, Framer, Canva, Adobe
- DeveloperTools&IDEs: GitHub, VS Code, JetBrains, Replit
- E-commerce&Retail: Shopify, Amazon, Etsy
- Fintech&Crypto: Stripe, Coinbase, Plaid, Wise
- Media&ConsumerTech: Apple, Spotify, NVIDIA, SpaceX, Uber, PlayStation, IBM, WIRED, TheVerge, Pinterest
- Productivity&SaaS: Linear, Notion, Slack, Zoom, Atlassian, Asana, Notion, Airtable

## Step 2: Analyze Design System ⛔ BLOCKING

Before generating ANY code, extract and verify you understand:

### 2.1 Color Palette
Ask: What are the exact hex codes for:
- Primary background(s)
- Primary text color(s)
- Accent/brand color(s)
- Interactive element colors (buttons, links)

### 2.2 Typography
Ask: What font families are used?
- Display/heading font
- Body/UI font
- What are the exact sizes, weights, line-heights, letter-spacings for each text role?

### 2.3 Component Styles
Ask: What do buttons look like?
- Background color
- Text color
- Border-radius (exact values like "9999px" or "8px")
- Padding
- Shadow (if any)

Ask: What do cards/containers look like?
- Background
- Border-radius
- Shadow
- Border (yes/no)

### 2.4 Layout Principles
Ask:
- What is the spacing base unit?
- What is the max content width?
- Is it full-width or contained?

### 2.5 Do's and Don'ts
The design file contains explicit rules. Follow them strictly.

## Step 3: Generate Code ⚠️ REQUIRED

### 3.1 Colors — EXACT MATCH ONLY

Use the EXACT hex codes from the design system. Do NOT approximate or "improve" the colors.

```css
/* WRONG - approximate colors */
background: #1a1a2e

/* CORRECT - exact from design spec */
background: #121212
```

### 3.2 Typography — EXACT MATCH ONLY

Use the EXACT font families, sizes, weights, letter-spacings specified.

```css
/* WRONG - using different font or approximate values */
font-family: 'Inter', sans-serif;
font-size: 16px;
font-weight: 600;

/* CORRECT - exact from Apple design spec */
font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', sans-serif;
font-size: 17px;
font-weight: 400;
letter-spacing: -0.374px;
```

### 3.3 Component Styles — Pixel Perfect

Apply the exact border-radius values (many use extreme values like 980px, 9999px):

```css
/* WRONG - generic rounded corners */
border-radius: 8px;

/* CORRECT - Apple uses 980px radius for pill buttons */
border-radius: 980px;
```

### 3.4 Shadows — Check If Used

Many dark themes require heavy shadows (0.3-0.5 opacity) to be visible:

```css
/* Spotify style heavy shadow */
box-shadow: rgba(0, 0, 0, 0.5) 0px 8px 24px;
```

## Step 4: Validate Output ⚠️ REQUIRED

Before presenting, verify:

- [ ] No placeholders like TODO, FIXME, xxx remain
- [ ] No generic fonts like Inter, Roboto, Arial used (unless specified in design)
- [ ] No generic purple/blue gradients
- [ ] All hex codes are exact matches from the design system
- [ ] Typography hierarchy matches exactly (sizes, weights, letter-spacing)
- [ ] Interactive elements (buttons, links) use the correct accent color
- [ ] No "AI aesthetic" — should look indistinguishable from the real brand

## Step 5: Present to User ⚠️ REQUIRED

Present the generated code with:
1. Brief description of what was created
2. The design system used (name and key characteristics)
3. How to run/use the code

Ask if they want any adjustments.

## Anti-Patterns

What Claude's lazy default would do — explicitly forbidden:

- [ ] DO NOT use purple/blue gradients as backgrounds
- [ ] DO NOT use Inter, Roboto, or Arial as primary fonts
- [ ] DO NOT use generic rounded corners (8px everywhere)
- [ ] DO NOT use blue as the default accent color
- [ ] DO NOT add shadows that aren't in the design system
- [ ] DO NOT use "Learn More" as CTA text (use brand-specific language)
- [ ] DO NOT approximate colors ("a slightly darker shade of...")
- [ ] DO NOT skip the design system analysis step

## Pre-Delivery Checklist

### Correctness
- [ ] All hex codes are exact matches from design system
- [ ] Typography uses correct font families and exact values
- [ ] Border-radius values match exactly (including extreme values like 980px)
- [ ] No placeholder text remains

### Brand Authenticity
- [ ] Would look indistinguishable from the actual brand's website
- [ ] No generic "AI aesthetic" present
- [ ] Accent color used ONLY for interactive elements (not decorative)
- [ ] Follows the Do's and Don'ts from the design system

### Code Quality
- [ ] CSS is valid and would render correctly
- [ ] Responsive considerations match the design system's breakpoints
- [ ] Interactive states (hover, active, focus) are styled
