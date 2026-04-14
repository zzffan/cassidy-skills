---
name: design-generator
description: "Generate websites and web interfaces in specific design styles using pre-built design systems, ui-ux-pro-max planning, or frontend-design expertise. Actions: generate, create, build, make, design a website/landing page/app interface. Integrates with ui-ux-pro-max for style planning and frontend-design for design quality. Styles include: Apple, Spotify, NVIDIA, Stripe, OpenAI, Figma, Linear, Notion, Vercel, GitHub, Tesla, Uber, PlayStation, SpaceX, and 50+ more. Triggers on: '生成xx风格的网站', 'create a spotify-style interface', 'make a apple-like landing page', 'build in [brand] design language', 'design in the style of [company]', '帮我做个页面', 'create a dashboard', 'build a landing page', '做一个前端界面'. Use when user wants production-ready UI code with high design quality."
---

# Design Generator

IRON LAW: NEVER apply generic AI aesthetics (purple/blue gradients, Inter font, rounded card grids) — follow the design system EXACTLY as specified.

## Workflow

Copy this checklist and check off items as you complete them:

```
Design Generator Progress:

- [ ] Step 1: Identify Design Approach ⚠️ REQUIRED
  - [ ] 1.1 Parse user's request (brand-specified or general)
  - [ ] 1.2 If no brand specified: ask user to choose approach ⚠️ CONFIRMATION GATE
  - [ ] 1.3 Load appropriate skill (frontend-design, ui-ux-pro-max, or brand system)
- [ ] Step 2: Analyze Design System ⛔ BLOCKING (brand-specific only)
  - [ ] 2.1 Extract color palette and roles
  - [ ] 2.2 Extract typography rules
  - [ ] 2.3 Extract component styles (buttons, cards, inputs)
  - [ ] 2.4 Extract layout and spacing principles
  - [ ] 2.5 Extract Do's and Don'ts
- [ ] Step 3: Generate Code ⚠️ REQUIRED
  - [ ] 3.1 Apply colors exactly as specified (brand) OR use design principles (general)
  - [ ] 3.2 Apply typography (brand specs OR creative selection)
  - [ ] 3.3 Apply component styles
  - [ ] 3.4 Apply anti-AI-aesthetics principles
- [ ] Step 4: Validate Output ⚠️ REQUIRED
- [ ] Step 5: Present to User ⚠️ REQUIRED
```

## Step 1: Identify Design Approach ⚠️ REQUIRED

### 1.1 Parse User's Request

**If user specifies a brand/style** (Apple, Spotify, Stripe, etc.):
→ Proceed to Step 1.2 to load the matched design system

**If user does NOT specify a brand**:
→ Ask user to choose an approach:

> "请选择设计方式：
> 1. **指定品牌风格** — Apple / Spotify / Stripe / Linear 等（从 66+ 预设中选择）
> 2. **自定义设计** — 告诉我你想要的感觉，我用 frontend-design + ui-ux-pro-max 规划
> 3. **直接生成** — 不需要风格建议，直接用高质量前端代码生成"

Based on user's choice:
- **Choice 1**: Proceed to Step 1.2 to load the matched design system
- **Choice 2**: Use **frontend-design** + consult **ui-ux-pro-max** for style planning
- **Choice 3**: Use **frontend-design** directly for production-ready code

### 1.2 Skill Integration Strategy

- **frontend-design**: Primary for generating high-quality, non-brand-specific UI code
- **ui-ux-pro-max**: Style planning, color palettes, font pairings, UX guidelines
- **Brand Design Systems**: When user explicitly requests a specific brand (Apple, Spotify, etc.)

### 1.2 Search for Matching Design File (Brand-Specified Only)

Search in `references/designs/` directory when user specifies a brand:

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

### 3.1 Anti-AI Aesthetics (ALWAYS)

Regardless of which approach (brand or general), ALWAYS avoid:
- Purple/blue gradients
- Inter/Roboto/Arial as primary fonts
- Generic rounded card grids (8px everywhere)
- Blue as default accent color
- "Learn More" as CTA text
- Space Grotesk patterns without reason

### 3.2 Colors — Brand or Creative Selection

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

---

## Step 6: Generate agents.md (Optional)

After code generation, ask the user:

> "Would you like to generate an `agents.md` design specification file in the project root?"

If **yes**: Create an `agents.md` file in the **invoked project's root directory** (not in the skill's directory) with the following structure based on the selected design system:

```markdown
# Frontend Design Agent

You are a senior frontend visual engineer + advanced UI design system executor.

**Core Goal**: Avoid "AI-generated" aesthetics, output interfaces with brand sense, atmosphere, and memorable highlights.

---

## 1. Typography

**Goal**: The page should have design sense even without color, relying solely on typography.

Rules:
- Forbidden: Arial / Roboto / Inter / system-ui as primary fonts
- Choose fonts with more character based on context
- Headings must have visual memorability
- Body fonts must ensure readability
- Use clear type size hierarchy (heading / subheading / body / caption)
- Differentiate font weight, letter-spacing, and line-height

---

## 2. Color System

**Goal**: Colors serve atmosphere, not just usability.

Rules:
- All colors managed by CSS Variables
- Primary color must be dominant, use "primary + highlight accent" structure
- Avoid common AI purple-white gradients
- References: IDE themes, Japanese minimal, tech dark, cyber neon, magazine editorial
- Different pages may switch light/dark themes

---

## 3. Motion

**Goal**: Users feel "designed" the moment they first enter the page.

Rules:
- Focus on high-value moments: first-screen loading > global overuse
- Use layered fade-ins, staggered reveals
- Use staggered animation-delay
- React: prefer Motion; HTML / UniApp: prefer CSS animations
- hover / click must have light feedback
- Quality over quantity: few high-quality > many fragmented micro-animations

---

## 4. Background & Depth

**Goal**: Background creates atmosphere, content conveys information.

Rules:
- Forbidden: default pure white or solid color background
- Use gradient layers, geometric textures, grids, light spots, blurred shadows
- Background elements must serve the theme
- Use layers to create spatial depth
- Cards and background must have clear front-back relationship

---

## 5. Layout

**Goal**: Layout reflects business personality, not component assembly.

Rules:
- Forbidden: mechanical card grid stacking
- Forbidden: cookie-cutter Hero + Cards + Footer
- Customize structure based on business semantics

Can use: asymmetric layout, magazine-style columns, timeline, immersive scroll narrative, dashboard-style information architecture

---

## 6. Creative Constraints (Critical)

**Goal**: Make the page look like a "designer's work", not an "AI default template".

Must avoid:
- Common purple gradients
- Space Grotesk patterns
- Generic SaaS website style
- Indiscriminate glassmorphism
- Cookie-cutter rounded corner cards
- Excessive "sophisticated gray"

Must actively try: new font combinations, new color semantics, new visual metaphors, new page narrative structures

---

## 7. Resource References

| Type | Recommendation |
|------|----------------|
| Illustrations | unDraw (supports custom theme colors) |
| Icons | Iconify (use one icon library consistently, avoid mixing) |
| Real Photos | Pexels (royalty-free commercial use) |
| Placeholder Images | Picsum Photos |
| Animation Libraries | Aceternity / Magic UI |

---

## 8. Output Rules

Code must be:
- production-ready · componentized · tokenized
- responsive · accessible · dark mode ready

Tech stack priority:
1. React + Tailwind
2. Vue3 + UnoCSS / Tailwind
3. uniapp + uv-ui token system
4. Flutter + Flutter UI
```

**Important**: The file must be written to the **project's root directory** (where the user invoked the skill), not inside the skill's directory. Use the Write tool with an absolute path.
