# BillEase — Smart Bill & Subscription Manager

> A unified mobile hub that consolidates recurring utilities (water, electricity) and recurring digital/physical subscriptions (gym, YouTube Premium, streaming) with secure card storage, one-tap payments, and monthly spending insights.

---

## 1. Project Overview & Meta Data

| | |
|---|---|
| **Project Name** | BillEase |
| **Role** | UI/UX Designer & Researcher |
| **Tools** | Figma, FigJam, Behance |
| **Target Audience** | Young professionals, students, and busy household managers juggling multiple billing cycles and payment dates |

---

## 2. Problem Statement

**What**
Users struggle to track split payment deadlines across various platforms (utility portals, entertainment subscriptions, memberships), leading to late fees or untracked recurring costs.

**Why**
Lack of a centralized payment ecosystem creates cognitive overload and fragmented transaction histories across disparate apps and bank portals.

**How**
Provide a streamlined mobile interface to securely vault payment cards, schedule automatic or manual multi-biller settlements, and visualize monthly expenditure trends through categorized summary dashboards.

---

## 3. Design Process Breakdown (Design Thinking)

1. **Empathize & Define** — Conduct user interviews to identify pain points around bill tracking, map out user personas, and document emotional highs and lows via empathy mapping.
2. **Ideate** — Create task flows and structured user navigation paths for adding cards, paying utilities, and reviewing monthly analytics.
3. **Prototype** — Draft low-fidelity sketches for layout structure, establish a clean design system, and build clickable, interactive high-fidelity Figma components.
4. **Test & Iterate** — Perform peer evaluation usability tests on the Figma prototype to refine navigation friction, payment confirmation clarity, and visual hierarchy.

---

## 4. User Personas

### Persona 1 — "The Multi-Subscriber Professional" (Age 24–30)
- **Needs:** Centralized view of digital subscriptions (YouTube, Spotify, gym) with renewal alerts.
- **Pain Point:** Forgetting auto-renewal dates and losing track of cumulative monthly micro-transactions.

### Persona 2 — "The Household Budget Manager" (Age 32–45)
- **Needs:** Quick, secure bill settlement for essential utilities (water, electricity, broadband) in one click.
- **Pain Point:** Entering 16-digit card details into individual, clunky government/utility portals every month.

---

## 5. Core User Flow & Information Architecture

**Add Payment Card Flow**
```
Dashboard → Wallet Tab → Add New Card → Card Details Input (Number, Expiry, CVV)
→ Security Verification (OTP/Biometric) → Card Saved & Linked
```

**Bill Settlement Flow**
```
Home → Select Category (Utilities / Subscriptions) → Choose Biller (e.g. Water Board)
→ Enter Account/Bill No. → Select Saved Card → Swipe to Confirm Payment
→ Receipt & Updated Monthly Summary
```

---

## 6. Style Guide & Visual Identity

**Design language:** Modern, clean, and minimal — generous white space, soft shadows, rounded corners (12–20px radius), and a fintech-trust aesthetic that never feels cluttered.

### Color Palette

| Role | Name | Hex | Usage |
|---|---|---|---|
| Primary | Deep Navy Blue | `#0F172A` | Headers, nav bar, primary buttons, key text — conveys security, trust, financial stability |
| Accent / Action | Emerald Mint | `#10B981` | Success states, confirmed payments, savings indicators, CTAs |
| Background | Slate White | `#F8FAFC` | Screen backgrounds, cards |
| Neutral / Text | Charcoal | `#334155` | Body copy, secondary labels, icons |

### Typography

- **Typeface:** Inter or SF Pro Display (clean, geometric sans-serif)
- **Headers:** Bold, 20–28px
- **Form labels:** Medium, 14–16px
- **Body text:** Regular, 14–16px
- **Numeric/financial figures:** Tabular nums, Semibold, for scannable alignment in lists and summaries

### UI Principles
- Minimum 8px spacing grid; 16–24px section padding
- Cards with subtle elevation (2–4px blur shadow) over the Slate White background
- Emerald Mint reserved exclusively for positive/action states — never used decoratively, to preserve its meaning
- Icons: rounded/line-style, single-weight, matching Charcoal or Navy depending on context

---

## 7. Key Screens & AI Prototyping Prompts

Each prompt below is written for AI UI-generation tools (Figma AI, Google Stitch, or similar) and encodes the BillEase style guide (Deep Navy Blue `#0F172A`, Emerald Mint `#10B981`, Slate White `#F8FAFC`, Charcoal `#334155`, Inter/SF Pro Display) so every generated screen stays visually consistent.

### A. Core Dashboard Screens

**1. Home & Monthly Overview**
> Design a modern, minimal mobile app home screen for "BillEase," a bill and subscription manager. Use a Slate White (#F8FAFC) background with a Deep Navy Blue (#0F172A) top header showing a greeting and profile icon. Center a large circular progress ring in Emerald Mint (#10B981) showing "Total Spent This Month" vs. budget, with the amount in bold Inter typography inside the ring. Below it, a horizontally scrollable row of "Upcoming Bills — Due in 7 Days" cards, each showing biller icon, name, amount, and due date on a white rounded card with soft shadow. Below that, a 2x2 grid of quick-action buttons (Pay Bill, Add Subscription, View Wallet, Analytics) in rounded Navy or Mint outline buttons. Bottom tab bar with Home, Wallet, Analytics, Profile icons. Clean, uncluttered, generous white space, rounded 16px corners throughout.

**2. Biller Directory & Categories**
> Design a mobile "Biller Directory" screen for the BillEase app. Slate White (#F8FAFC) background, Deep Navy (#0F172A) header titled "Pay a Bill" with a search bar beneath it. Below the search bar, two clearly labeled section headers: "Utilities" and "Lifestyle & Subscriptions." Under "Utilities," a grid of rounded square icon-cards for Water, Electricity, Gas — each with a simple line icon, Charcoal (#334155) label text, and white card background with subtle shadow. Under "Lifestyle & Subscriptions," a matching grid for Gym, Streaming, Memberships. Selected/hovered cards get a thin Emerald Mint (#10B981) border. Consistent 16px grid spacing, rounded corners, Inter typography, bottom tab bar visible.

**3. Payment & Card Manager**
> Design a "Wallet" screen for the BillEase mobile app. Slate White (#F8FAFC) background, Deep Navy (#0F172A) header titled "My Cards." Below the header, a horizontal swipeable carousel of vaulted payment cards rendered as sleek rounded rectangles in Deep Navy gradient with masked card numbers (•••• 4821), cardholder name, and a small "Primary" Emerald Mint (#10B981) badge on the default card. Dots indicator below the carousel for card position. Beneath the carousel, a list of card controls: "Set as Primary," "View Transaction Limit," and a Mint-outlined "+ Add New Card" button. Bottom sheet style transaction limit display with a slim progress bar in Emerald Mint. Clean fintech aesthetic, rounded 20px card corners, soft shadows, Inter typography.

**4. Analytics & Summary Tab**
> Design an "Analytics" screen for the BillEase mobile app. Slate White (#F8FAFC) background, Deep Navy (#0F172A) header titled "Monthly Summary" with a month selector arrow control. Below it, a donut chart in a Deep Navy / Emerald Mint / Charcoal color scheme breaking down spend by category (Utilities, Subscriptions, Memberships), with a legend listing category, amount, and percentage. Beneath the donut chart, a horizontal bar chart comparing this month vs. last month spend per category, bars in Emerald Mint with Navy comparison markers. At the bottom, a small stat card showing "-12% vs last month" in Emerald Mint with an upward/downward trend arrow. Rounded card containers, soft shadows, generous padding, Inter typography, bottom tab bar visible.

### B. Add Payment Card Flow

**5. Add New Card (entry screen)**
> Design a "Wallet" empty/entry state screen for BillEase prompting the user to add their first payment card. Slate White (#F8FAFC) background, Deep Navy header. Centered illustration of a stylized card/wallet icon in Navy and Mint line-art, with heading "No cards added yet" and subtext in Charcoal. Large rounded Emerald Mint (#10B981) primary button reading "+ Add New Card" pinned near the bottom. Minimal, friendly, uncluttered composition.

**6. Card Details Input**
> Design a "Card Details" input form screen for BillEase. Slate White (#F8FAFC) background, Deep Navy header titled "Add New Card" with a back arrow. Below, a live-preview card graphic in Deep Navy gradient at the top that updates as the user types. Beneath the preview, clean rounded input fields with Charcoal Medium-weight labels for Card Number, Expiry Date, and CVV, laid out with the expiry and CVV fields side-by-side. Fields have thin Navy borders that turn Emerald Mint on focus. A full-width Emerald Mint "Continue" button pinned at the bottom. Inter typography, 16px field padding, rounded 12px corners.

**7. Security Verification (OTP/Biometric)**
> Design a "Security Verification" screen for BillEase. Slate White (#F8FAFC) background, centered layout. A Deep Navy circular icon with a fingerprint or shield glyph at the top, heading "Verify It's You" in bold Inter, and subtext explaining an OTP was sent or biometric is required. Below, six individual OTP input boxes with thin Navy borders, the active box highlighted in Emerald Mint. A "Resend Code" text link in Charcoal, and a full-width Emerald Mint "Verify" button pinned at the bottom. Alternative: a large centered biometric/fingerprint icon with a pulsing Mint ring animation cue if biometric mode. Minimal, secure, reassuring visual tone.

**8. Card Saved & Linked (confirmation)**
> Design a success confirmation screen for BillEase after a card is added. Slate White (#F8FAFC) background, centered composition. A large circular Emerald Mint (#10B981) checkmark badge at the top, heading "Card Added Successfully" in bold Deep Navy Inter typography, and subtext confirming the card is now linked and ready to use. Below, a small preview of the newly added card in Navy gradient style. A full-width Emerald Mint "Done" button pinned at the bottom, with a secondary Charcoal text link "Add Another Card." Celebratory but minimal — no clutter, soft micro-illustration accents only.

### C. Bill Settlement Flow

**9. Select Category**
> Design a "Select Category" screen for BillEase, the first step in the bill payment flow. Slate White (#F8FAFC) background, Deep Navy header titled "What are you paying today?" with a back arrow. Two large rounded selectable cards stacked vertically: "Utilities" (with a water/electric line icon) and "Lifestyle & Subscriptions" (with a streaming/gym line icon), each on white cards with soft shadow and a Charcoal subtitle describing included billers. Selected state shows an Emerald Mint border and checkmark. Minimal, spacious, Inter typography.

**10. Choose Biller**
> Design a "Choose Biller" screen for BillEase, showing billers within the Utilities category. Slate White (#F8FAFC) background, Deep Navy header titled "Utilities" with a back arrow and search bar. Below, a vertical list of biller rows (e.g., "Water Board," "Electricity Board," "Gas") each with a rounded icon avatar, biller name in Charcoal Medium text, and a chevron arrow on the right, separated by thin dividers. Tapped/selected row highlighted with a light Emerald Mint tint background. Clean list design, generous row height for easy tapping, Inter typography.

**11. Enter Account/Bill Number**
> Design an "Enter Bill Details" form screen for BillEase. Slate White (#F8FAFC) background, Deep Navy header titled "Water Board Payment" with a back arrow and small biller logo. Below, a single prominent rounded input field labeled "Account / Bill Number" in Charcoal Medium text with a Navy border that turns Emerald Mint on focus. Optional helper text below explaining where to find the number, with a small illustrative icon. A full-width Emerald Mint "Fetch Bill" or "Continue" button pinned at the bottom. Minimal single-focus layout, Inter typography.

**12. Select Saved Card**
> Design a "Select Payment Method" bottom-sheet screen for BillEase during checkout. Slate White (#F8FAFC) background with a rounded-top modal sheet sliding up over a dimmed backdrop. Sheet header "Choose Card" in bold Inter. Below, a vertical list of saved cards as compact rounded rows showing masked card number, card network icon, and a radio-selector on the right — the Primary card pre-selected with an Emerald Mint (#10B981) filled radio. A Mint-outlined "+ Add New Card" row at the bottom of the list, followed by a full-width Emerald Mint "Confirm" button. Clean, modal-style, rounded 20px sheet corners.

**13. Swipe to Confirm Payment**
> Design a "Confirm Payment" screen for BillEase showing a payment summary before completion. Slate White (#F8FAFC) background, Deep Navy header titled "Review & Pay." Below, a summary card listing Biller, Account Number, Amount Due, and Card being charged, in clean rows with Charcoal labels and bold Navy values. At the bottom, a horizontal "Swipe to Confirm Payment" slider component styled as a long rounded track in Emerald Mint with a circular draggable thumb showing an arrow icon and a subtle shimmer animation cue. Minimal, trustworthy, high-clarity layout with strong visual hierarchy on the amount.

**14. Receipt & Updated Monthly Summary**
> Design a "Payment Successful" receipt screen for BillEase. Slate White (#F8FAFC) background, centered composition. A large Emerald Mint (#10B981) checkmark badge at the top, heading "Payment Successful" in bold Deep Navy Inter typography, and the paid amount displayed prominently below in large numerals. Beneath, a receipt-style card with dashed border edges listing Biller, Reference Number, Date, and Card Used in Charcoal text rows. Below the receipt, a compact "Updated Monthly Summary" mini progress bar in Emerald Mint showing the new total spend vs. budget. Two buttons at the bottom: a Mint filled "Share Receipt" and a Navy-outlined "Back to Home." Clean, celebratory, minimal clutter.

---

## 8. Usability Testing Focus (Test & Iterate)

- Navigation friction between category → biller → confirmation steps
- Clarity of the swipe-to-confirm payment gesture vs. accidental triggers
- Visual hierarchy of the monthly overview (is the spend-vs-budget ring immediately understandable?)
- Legibility and trust perception of the card vaulting flow (OTP/biometric step)
