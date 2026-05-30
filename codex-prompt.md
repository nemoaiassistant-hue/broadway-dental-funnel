# Broadway Dental Boutique — Invisalign Funnel

Build a **mobile-first, full-screen swipeable funnel** (like Perspective Funnels / Instagram Stories) for Broadway Dental Boutique's Invisalign treatment. Single `index.html` file with all CSS and JS inline.

## Brand
- **Name:** Broadway Dental Boutique
- **Tagline:** "The Smile You Deserve"
- **Location:** 38 The Broadway, Crawley, West Sussex, RH10 1HG
- **Phone:** 01293 428342
- **Website:** broadwaydentalb.co.uk
- **Doctor:** Dr. Amo (Invisalign specialist)
- **Gold/bronze:** #A38B5D
- **Black:** #000000
- **White:** #FFFFFF
- **Light grey bg:** #F5F5F5
- **Font:** System sans-serif (clean, modern)

## Funnel Flow (8 cards, full-screen each)

Users swipe/click through cards. Each card fills the entire viewport (100vh). Navigation: swipe gesture on mobile, scroll/tap arrows on desktop. A progress bar at the top shows which card you're on.

### Card 1: Hook (Black background, gold text)
- **Eyebrow:** "BROADWAY DENTAL BOUTIQUE · CRAWLEY"
- **Large headline:** "Want straighter teeth without metal braces?"
- **Subtext:** "Take this 60-second quiz to see if Invisalign is right for you."
- **CTA button (gold bg, black text):** "Start Quiz →"
- Small gold Invisalign logo or teeth icon (SVG inline)

### Card 2: Question 1 (Light bg #F5F5F5, black text)
- **Question:** "How would you describe your teeth right now?"
- **Options (large tap targets, 3 options stacked):**
  - "Mildly crooked" → next
  - "Quite crooked or gapped" → next
  - "Very crooked, I hide my smile" → next
- All lead to same next card (this is a conversion funnel, not a diagnostic tool)

### Card 3: Question 2 (Black bg, white text)
- **Question:** "Have you considered straightening your teeth before?"
- **Options (2 large buttons):**
  - "Yes, I've thought about it" → next
  - "No, this is my first time" → next

### Card 4: Question 3 (Light bg, black text)
- **Question:** "What matters most to you?"
- **Options (3 cards with icons):**
  - "Straight teeth" (smile icon)
  - "More confidence" (star icon)
  - "Better oral health" (heart icon)

### Card 5: Results Teaser (Black bg, gold accent)
- **Headline:** "Great news! ✨"
- **Text:** "Based on your answers, you could be a perfect candidate for Invisalign at Broadway Dental Boutique."
- **Subtext:** "Dr. Amo, our Invisalign specialist, has helped hundreds of patients in Crawley achieve their dream smile."
- **CTA:** "See Your Options →"

### Card 6: Social Proof (Light bg)
- **Headline:** "Real patients. Real results."
- **Testimonial cards (2-3 stacked, swipeable):**
  - "I'm so happy with my Invisalign and whitening treatment and so glad I chose Broadway Dental" — Francesca D.
  - "I'm nearing the end of my treatment and my teeth look amazing and straight." — Sarah A.
  - "I had Invisalign, new crowns and composite bonding. From start to finish, I felt looked after." — Laura H.
- **Trust badges:** ⭐⭐⭐⭐⭐ "Multi award-winning practice"
- **CTA:** "Book Your Free Consultation →"

### Card 7: Lead Capture Form (Black bg, gold accents)
- **Headline:** "Claim your free Invisalign consultation"
- **Subtext:** "Worth £150. Limited availability this month."
- **Form fields:**
  - First name (required)
  - Last name (required)
  - Email (required)
  - Phone (required)
  - Hidden field: source = "invisalign-funnel"
- **CTA button (gold bg):** "Book My Free Consultation →"
- **Privacy note:** "We'll contact you within 24 hours to arrange your consultation. Your data is safe with us."
- On submit: show success card (Card 8). NO actual backend post — just frontend capture.

### Card 8: Thank You / Success (Gold bg, black text)
- **Large checkmark animation** (SVG)
- **Headline:** "You're all set! 🎉"
- **Text:** "We'll be in touch within 24 hours to book your free Invisalign consultation."
- **Call button:** "Call us now: 01293 428342" (tap to call)
- **Link:** "Visit our website →" (broadwaydentalb.co.uk)

## Design Requirements

### Mobile-First (CRITICAL)
- Every card is exactly **100vh × 100vw** — no scrolling within a card
- Content centered vertically within each card
- Touch swipe to navigate between cards
- Large tap targets (minimum 48px height for buttons)
- Text sizes: headlines 28-36px, body 16-18px, buttons 16px
- Safe area padding for notched phones (env(safe-area-inset-*))

### Navigation
- **Progress bar** at top: thin gold line showing progress (1/8, 2/8, etc.)
- **Swipe left** = next card, **swipe right** = previous card
- **Arrow buttons** on desktop (left/right arrows on card sides)
- **Dot indicators** at bottom (like Instagram Stories)
- Cards animate with a smooth slide transition (CSS transform)
- Back button visible on cards 2-8 (top left corner)

### Animations
- Cards slide in from right, slide out to left (smooth 300ms transition)
- Button hover: subtle scale (1.02) + shadow
- Card 8 checkmark: draw-in animation (SVG stroke-dasharray)
- Option buttons: slight bounce on tap (CSS active state)
- Gold accent elements have a subtle shimmer/glow

### Typography
- System font stack: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif
- Headlines: bold, tight letter-spacing (-0.02em)
- Body: regular weight, line-height 1.5
- All text crisp and readable on mobile

### No External Dependencies
- All CSS inline in `<style>`
- All JS inline in `<script>`
- No images — use inline SVGs for icons (teeth, smile, star, heart, checkmark, arrow)
- No Google Fonts — system fonts only for speed
- No CDN links whatsoever

## Technical
- Single file: `index.html`
- Touch swipe via touchstart/touchmove/touchend events (no libraries)
- Keyboard navigation: left/right arrows
- Prevent pull-to-refresh and overscroll bounce
- Form validation: basic HTML5 required + email pattern
- On form submit: prevent default, capture data in JS, show Card 8
- `console.log()` the captured form data (for demo purposes)
- Viewport: `<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">`

## Quality
- Must look and feel like a native app, not a website
- Must feel premium and trustworthy (dental practice, not cheap marketing)
- Smooth 60fps animations
- Works on iOS Safari, Android Chrome, desktop Chrome/Safari
- No horizontal scroll, no layout shift, no janky scrolling
