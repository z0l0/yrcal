# FlowCal — Product Requirements Document

> **"Don't just manage your time. Audit your life."**
>
> A privacy-first calendar app that syncs seamlessly with Google Calendar. Built for people who want to own their time, not rent it.

---

## The Pitch

FlowCal is the calendar app for people who are tired of Big Tech knowing every detail of their lives. It's Google Calendar sync without the surveillance. Beautiful, fast, private.

**Why this wins:**
- Privacy is the new luxury. People are waking up.
- Google Calendar has 500M+ users who are locked in but increasingly uncomfortable
- No real competitor offers seamless GCal sync + true privacy
- Jesse Itzler's Big Ass Calendar philosophy meets modern software
- Acquisition target: BigAssCalendar.com wants digital. We're the answer.

**The Viral Hook:**
At the end of the year, Spotify tells you what you listened to. FlowCal tells you **who you became**.

---

## Core Philosophy

**"Plan your life, not your inbox."**

Current calendars are tools of oppression — digital inboxes for other people's demands. They tell you where to be, but not who you are.

Inspired by Jesse Itzler's system:
- Schedule life before work
- Visualize your year at a glance
- Color-code what matters
- Make your calendar your highlight reel, not your to-do list
- **Energy over Activity:** Track not just *what* you did, but *how it felt*
- **Default to "No":** If it isn't on the calendar, it doesn't exist

---

## Target User

**The "Optimize-Out" Crowd:**
- 25-45 year old professionals
- Privacy-conscious but not paranoid
- Already using Google Calendar (can't escape it for work)
- Wants something beautiful that doesn't feel like enterprise software
- Values intentionality over productivity theater

**The "Life Architects":**
- People obsessed with Jesse Itzler, Tim Ferriss, and Joe Rogan
- Want to track "Misogi" attempts, "Date Nights," and "Deep Work" — not just "Standups"

**The Privacy Pragmatists:**
- Can't quit Google (enterprise lock-in) but want to "degoogle" their personal life

---

## Core Features (V1)

### 1. Seamless Google Calendar Sync
- One-click OAuth connection
- Real-time bidirectional sync
- Works with multiple Google accounts
- **Privacy twist:** All sync happens client-side. We never see your events.
- **"Burner Mode":** Sync only Free/Busy status to work calendar, hiding event titles. Your boss sees "Busy," you see "Interview with Competitor."

### 2. Local-First Architecture
- All data stored locally on device
- End-to-end encrypted cloud backup (optional)
- Zero-knowledge architecture — we literally cannot read your calendar
- Export everything anytime (ICS, JSON, CSV)

### 3. Year-at-a-Glance View
- Full 365-day view on one screen (Big Ass Calendar style)
- Color-coded categories you define
- Drag to create multi-day events
- Zoom from year → month → week → day seamlessly
- **Heatmap Mode:** GitHub-contribution-style view of your entire year
  - 🟢 Green: Adventure/Social
  - 🔵 Blue: Work
  - 🔴 Red: Health/Gym
  - ⬜ Gray: Unaccounted time (the enemy)
- **Zoom Physics:** Pinch from Year → Month → Day with 60fps buttery smooth animations. No load times.

### 4. Smart Color Coding
- Auto-categorize events based on keywords (user-defined rules)
- Visual density indicators — see busy vs. free at a glance
- "Life vs. Work" toggle to filter view
- Custom color palettes (not the same 6 colors everyone uses)

### 5. Year-in-Review Auto-Sort (No AI Required)
Pulls your last 12 months from Google Calendar and auto-categorizes using simple, transparent rules:

**Pattern Matching Engine:**
- **Keyword matching:** "standup", "1:1", "sync", "meeting" → Work
- **Keyword matching:** "dinner", "birthday", "wedding", "brunch" → Social
- **Keyword matching:** "gym", "run", "yoga", "doctor", "dentist" → Health
- **Keyword matching:** "flight", "hotel", "airbnb", "vacation" → Travel
- **Keyword matching:** "kids", "school", "soccer", "recital" → Family
- **Time-of-day heuristics:** 9-5 weekday events default to Work
- **Duration heuristics:** 30-60 min recurring = likely meetings, 2+ hours = deep work or personal
- **Calendar source:** Work Google account vs personal account
- **Recurring patterns:** Weekly same-time events get grouped
- **Location data:** If event has location, use Google Places categories (restaurant, gym, airport)

**How It Works:**
```
Event: "Team standup" at 9:30am, 15 min, recurring daily
→ Keywords: "standup", "team" → Work
→ Time: 9:30am weekday → Work  
→ Duration: 15 min recurring → Meeting
→ Result: Work/Meetings (high confidence)

Event: "Dinner with Sarah" at 7pm Saturday
→ Keywords: "dinner" → Social
→ Time: Weekend evening → Personal
→ Result: Social (high confidence)

Event: "Q4 Planning" at 2pm, 3 hours
→ Keywords: "planning", "Q4" → Work
→ Duration: 3 hours → Deep work session
→ Result: Work/Strategy (medium confidence)
```

**User Controls:**
- Review and correct any miscategorized events (one click)
- System learns from corrections (simple frequency counting, not ML)
- Export categorization rules as JSON
- Share rule sets with others
- Manual override always available

**Year-in-Review Dashboard:**
- Pie chart: How you spent your year by category
- Timeline: Category distribution by month (see seasonal patterns)
- Insights: "You had 47 1:1s, 23 social events, 12 travel days"
- Comparison: This year vs last year (if data available)
- "Highlight reel" — auto-surface multi-day events, travel, big meetings

**Privacy Note:** All categorization happens 100% client-side. Rules are just regex/keyword matching in JavaScript. Nothing leaves your device.

### 6. The "Life Resume" — Annual Report (Viral Engine)
**This is the growth engine.**

Once a year (or on demand), FlowCal generates a cinematic, shareable report of your year.

**Why it goes viral:**
- People love sharing data about themselves (Spotify Wrapped, Strava Year in Sport)
- No other app does this for *life events*
- Creates FOMO — seeing a friend's Life Resume filled with travel and adventure makes others want to catch up

**The Output:**
- **The Stats:** "You spent 1,400 hours in meetings. 200 hours in the gym. Traveled to 4 countries."
- **The Streaks:** "Longest streak of 'Deep Work': 5 days."
- **The "Big Ass" Moments:** Auto-generated highlight reel of multi-day events (vacations, retreats, conferences)
- **Year Grade:** Self-assigned A-F grade with reflection prompts
- **The Share Card:** Slick, designed graphic for Instagram/LinkedIn stories: *"I just audited my life with FlowCal. 2025 was a [B+] year."*

**Privacy-Safe Sharing:**
- Share cards show aggregate stats only, never event titles
- User controls exactly what's included
- Can generate private version (full detail) vs public version (stats only)

### 7. Energy Tracking (The Jesse Special)
After an event ends, FlowCal prompts a single question:

**"Did that give you energy or drain you?"** ⚡️ or 🪫

- One tap. Takes 2 seconds.
- Optional — never nags.

**Over time:**
- Calendar colors shift based on *energy levels*, not just categories
- Visually see which months/years burned you out
- Identify energy vampires (recurring meetings that always drain)
- Spot patterns: "Mondays drain me, Fridays energize me"

**The Insight:**
"You spent 340 hours in meetings this year. 78% of them drained you. Here are the 5 recurring meetings that cost you the most energy."

### 8. Focus Mode
- Hide all events except what matters today
- "What deserves my energy?" daily prompt
- Evening planning ritual — 2-minute end-of-day review
- Weekly reflection prompts (optional)

### 9. Keyboard-First Design
- `Cmd+K` command palette for everything
- Vim-style navigation (optional)
- Create events without touching mouse
- **Natural Language Input:** "Dinner with Sarah tomorrow 7pm" creates it instantly
- Power users will love this

### 10. BigAssCalendar Print Integration (Acquisition Bridge)
**The strategic play to get acquired.**

**The "Print" Button:**
- Premium feature that formats your FlowCal Year View specifically for printing on a BigAssCalendar physical poster
- Users visualize their *past* year to plan their *next* year on the physical calendar
- One-click order flow to BigAssCalendar store

**The Pitch to Jesse:**
"We have the software that feeds your hardware. 50,000 users are already using your year-view format digitally. Let's sell them the physical version."

---

## Design Principles

### Visual Identity
- **"Warm Brutalism."** High contrast, bold typography, satisfying clicks.
- **Clean, not sterile.** Warm whites, subtle shadows, intentional color.
- **Typography matters.** Inter or similar. Readable at every size.
- **Animations that feel right.** Smooth 60fps, never gratuitous.
- **Dark mode that's actually good.** Not inverted colors. Designed dark.

### UX Philosophy
- **Zero onboarding friction.** Connect Google, you're in.
- **Progressive disclosure.** Simple by default, powerful when needed.
- **Respect attention.** No notifications unless you ask.
- **Fast.** Sub-100ms interactions. Always.
- **Input Speed:** Creating an event must be faster than writing it on a napkin.
- **Dark mode is default.** Pitch black background (OLED friendly) with neon accents.

---

## Technical Architecture

### Stack
- **Frontend:** React + TypeScript, Tailwind CSS
- **State:** Zustand (simple, fast)
- **Local Storage:** IndexedDB via Dexie.js
- **Sync Engine:** Custom CRDT-based sync for offline-first
- **Encryption:** libsodium (XChaCha20-Poly1305)
- **Google API:** Client-side only, tokens never touch our servers

### Privacy Architecture
```
┌─────────────────────────────────────────────────────────┐
│                     User's Device                        │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐  │
│  │  FlowCal    │◄──►│  IndexedDB  │◄──►│  Encrypted  │  │
│  │  App        │    │  (Local)    │    │  Backup     │  │
│  └──────┬──────┘    └─────────────┘    └──────┬──────┘  │
│         │                                      │         │
│         ▼                                      ▼         │
│  ┌─────────────┐                      ┌─────────────┐   │
│  │  Google     │                      │  Cloud      │   │
│  │  Calendar   │                      │  Storage    │   │
│  │  API        │                      │  (E2E Enc)  │   │
│  └─────────────┘                      └─────────────┘   │
└─────────────────────────────────────────────────────────┘
         │                                      │
         ▼                                      ▼
   Google Servers                    FlowCal Servers
   (They see your                    (We see encrypted
    events anyway)                    blobs only)
```

### What We Store (Server-Side)
- User ID (anonymous, no email required for basic use)
- Encrypted backup blobs (we cannot decrypt)
- Subscription status
- That's it.

---

## Monetization

### Free Tier
- Unlimited local use
- Single Google Calendar sync
- Basic color coding
- Year heatmap view
- 7-day cloud backup retention

### Pro ($9/month or $90/year — "The Partner Price")
- Multiple Google account sync
- Unlimited cloud backup retention
- Advanced keyboard shortcuts
- Custom themes
- Energy tracking + analytics
- Multi-calendar "Life View" (combine work + personal)
- Priority support
- Early access to new features

### Life Resume Unlock
- **$19 one-time** or **free with Pro**
- Full annual report generation
- Shareable cards for social
- Year-over-year comparisons
- Export as PDF/video

### BigAssCalendar Print (Affiliate Revenue)
- One-click formatting for physical calendar
- Direct order flow to BigAssCalendar store
- Revenue share on each sale

### Why This Pricing Works
- $9/mo is impulse purchase territory
- Annual discount ($90 vs $108) drives commitment
- Life Resume as one-time purchase captures non-subscribers
- Free tier is genuinely useful (not crippled)
- Print integration creates affiliate revenue stream

---

## Go-to-Market

### Phase 1: The Privacy Insurgency (Months 1-3)
1. **"Delete Google" Challenge:** Viral video showing someone deleting Google Calendar app and replacing it with FlowCal in 10 seconds
2. **Build in public** — "Day 1 of building a calendar that Google can't read." Document the struggle of client-side encryption.
3. **HN launch** — "Show HN: I built a privacy-first Google Calendar client"
4. **Privacy community** — r/privacy, r/degoogle, privacy-focused newsletters
5. **Productivity community** — r/productivity, Twitter productivity crowd

### Phase 2: The "Life Resume" Drop (Month 4)
- Release Annual Report feature in Q4 (planning season)
- **Influencer Army:** Free lifetime accounts to 50 high-profile "Life Hacker" influencers (Jesse Itzler, Alex Hormozi, etc.)
- *If Jesse tweets his Life Resume, we win.*

### Phase 3: The Acquisition Bait (Month 6+)
- Direct partnership outreach to BigAssCalendar
- Pitch: "We have 50,000 users using your year-view format digitally. Let's sell them the physical version."

### HN Angle
- Open source the sync engine
- Publish detailed privacy architecture
- Be transparent about what we can/can't see
- Technical founder story

### Acquisition Positioning
BigAssCalendar sells physical calendars. They need digital. We're the perfect fit:
- Same philosophy (year-at-a-glance, intentional planning)
- Technical team they don't have
- User base they want
- Brand alignment is perfect
- **The Jesse Pitch:** "We built the digital version of your wall. The Big Ass Digital Calendar."

---

## Success Metrics

### V1 Launch (Month 1-3)
- 10K signups
- 1K daily active users
- #1 on HN for a day
- 100 paying customers

### Growth Phase (Month 4-12)
- 100K signups
- 10K DAU
- 2K paying customers (~$180K ARR)
- Featured in major tech publication
- **Viral Coefficient (K-factor) > 1.0** (driven by Life Resume shares)

### Acquisition Ready (Year 2)
- 500K+ users
- 10K+ paying customers ($900K+ ARR)
- Strong brand recognition in productivity space
- Clean codebase, documented architecture
- **Key Indicator:** Direct mentions of "BigAssCalendar" in user reviews or social shares

---

## Competitive Landscape

| Feature | FlowCal | Fantastical | Cron | Notion Cal | Google Cal |
|---------|---------|-------------|------|------------|------------|
| Privacy-first | ✅ | ❌ | ❌ | ❌ | ❌ |
| GCal sync | ✅ | ✅ | ✅ | ✅ | N/A |
| Local-first | ✅ | ❌ | ❌ | ❌ | ❌ |
| Year view | ✅ | ✅ | ❌ | ❌ | ❌ |
| Year heatmap | ✅ | ❌ | ❌ | ❌ | ❌ |
| Life Resume/Annual Report | ✅ | ❌ | ❌ | ❌ | ❌ |
| Energy tracking | ✅ | ❌ | ❌ | ❌ | ❌ |
| Free tier | ✅ | ❌ | ✅ | ✅ | ✅ |
| Keyboard-first | ✅ | ⚠️ | ✅ | ❌ | ❌ |
| E2E encrypted | ✅ | ❌ | ❌ | ❌ | ❌ |
| Burner mode | ✅ | ❌ | ❌ | ❌ | ❌ |

---

## Roadmap

### V1.0 — Foundation (Weeks 1-8)
- [ ] Core calendar UI (day/week/month/year views)
- [ ] Year heatmap view (GitHub-style)
- [ ] Google Calendar OAuth + sync (client-side)
- [ ] Burner Mode (Free/Busy only sync)
- [ ] Local storage with IndexedDB
- [ ] Basic event CRUD
- [ ] Natural language event creation
- [ ] Color coding system
- [ ] Keyboard shortcuts + Cmd+K palette
- [ ] Dark mode (default)
- [ ] Year-in-Review auto-categorization engine
- [ ] Pattern matching rule system
- [ ] Review dashboard with charts

### V1.1 — Polish (Weeks 9-12)
- [ ] E2E encrypted cloud backup
- [ ] Multiple Google account support
- [ ] Custom themes
- [ ] Mobile-responsive design
- [ ] Offline mode improvements
- [ ] Energy tracking (drain/gain prompts)

### V2.0 — Growth / Life Resume (Months 4-6)
- [ ] **Life Resume annual report generator**
- [ ] Shareable social cards
- [ ] Native mobile apps (React Native)
- [ ] Outlook/iCloud sync
- [ ] Energy analytics dashboard
- [ ] API for integrations
- [ ] Widgets

### V3.0 — Platform (Months 7-12)
- [ ] Planning rituals (weekly review, daily intentions)
- [ ] Goal tracking (Misogi, mini adventures)
- [ ] "Eight Boxes" life categories
- [ ] Habit integration
- [ ] **BigAssCalendar print integration**
- [ ] Team calendars (privacy-preserving)

---

## Risk Mitigation

| Risk | Mitigation |
|------|------------|
| Google API changes | Abstract sync layer, monitor deprecations |
| Privacy claims scrutinized | Open source crypto, third-party audit |
| Low conversion to paid | Iterate on Pro features, test pricing |
| Competition copies features | Move fast, build community, brand loyalty |
| Acquisition doesn't happen | Build sustainable business regardless |

---

## Team Requirements

### Founding Team (3 people)
1. **Technical Founder** — Full-stack, crypto/privacy experience
2. **Design Founder** — Product design, brand, UX
3. **Growth** — Marketing, community, content

### First Hires
- Senior frontend engineer (React, performance)
- Mobile engineer (React Native)
- DevRel / Community manager

---

## Why This Wins

1. **Timing is perfect.** Privacy awareness at all-time high.
2. **Clear differentiation.** No one else does privacy + GCal sync well.
3. **Viral engine built-in.** Life Resume is Spotify Wrapped for your life.
4. **Acquisition path is obvious.** BigAssCalendar needs this.
5. **Technical moat.** Local-first + E2E encryption is hard to copy.
6. **Community potential.** Privacy + productivity = passionate users.
7. **Sustainable business.** Real revenue from day one.
8. **Energy tracking is unique.** No calendar does this.

---

## The Ask

Build this. Ship V1 in 8 weeks. Launch on HN. Get users. Get revenue. Get acquired.

**Immediate Next Steps:**
1. Prototype the "Life Resume" UI first — that's the marketing engine
2. Build the GCal Sync (client-side)
3. Design the Year Heatmap

Let's make calendars private again.

---

*"The calendar is the only thing that tells the truth. Let's make sure you own it."*

*"The calendar is your most honest autobiography."* — Jesse Itzler
