# Cascade-onboard



🎯 GOAL OF THE MVP

Build a seamless onboarding system for Avalanche Cascade where:
	1.	Builders complete onboarding tasks digitally
	2.	Verification is mostly automated
	3.	Builders receive:
	•	a physical ticket (proof of attendance)
	•	an NFT airdropped to Core Wallet (digital proof of attendance)
	4.	All data flows into one dashboard

⸻

🧠 CORE DESIGN PRINCIPLE

One QR → One Flow → One Wallet → One NFT

No jumping between platforms without context. Everything starts from a single scan.

⸻

🧱 MVP ARCHITECTURE OVERVIEW

Components

Layer	Tool
Frontend	Simple Web App (Next.js / React)
Backend	Node.js + Express / Firebase
Database	Firebase / Supabase
Event Check-in	Luma
Wallet	Core Wallet
NFT Minting	Avalanche C-Chain
Airdrop	Core Airdrop Tool
Admin	Simple dashboard


⸻

🔁 END-TO-END USER FLOW (BUILDER EXPERIENCE)

STEP 1: ENTRY POINT (QR ON PHYSICAL TICKET)

QR Code on Ticket → onboard.avaxcascade.xyz

This is critical:
The QR code does NOT go to Luma directly.

It goes to your onboarding app, which then orchestrates everything.

⸻

STEP 2: CONNECT CORE WALLET (MANDATORY)

Page 1: “Welcome to Avalanche Cascade”
	•	Button: Connect Core Wallet
	•	Detect Core Wallet (browser or mobile)
	•	If not installed → show download link
	•	Once connected:
	•	Save wallet address
	•	Generate a unique Onboarding Session ID

📌 This ensures every attendee is wallet-bound from step one

⸻

STEP 3: EVENT CHECK-IN (LUMA INTEGRATION)

Page 2: “Event Check-in”

Options (pick MVP-friendly):

MVP Option A (Recommended)
	•	Embed:
	•	“Open Luma Check-in” button
	•	After check-in:
	•	Attendee clicks “I’ve checked in”
	•	Staff visually confirms OR
	•	Luma webhook updates backend

MVP Option B (More Automated)
	•	Luma registration requires:
	•	Wallet address
	•	Backend matches:
	•	wallet → checked-in attendee

✅ Once verified:
	•	Mark checked_in = true

⸻

STEP 4: TASK COMPLETION MODULE

Page 3: “Complete onboarding tasks”

Each task is a card with action + verification

Task List
	1.	Follow @AvaxAfrica on X
	2.	Join Telegram
	3.	Join WhatsApp
	4.	(Optional) Join Discord
	5.	Install Core Wallet (auto-completed if already connected)

⸻

Task Verification (MVP-friendly)

Task	Verification Method
X Follow	Manual confirmation checkbox
Telegram	Join link + checkbox
WhatsApp	Join link + checkbox
Discord	Optional
Core Wallet	Auto-detected

📌 Do NOT over-automate in MVP
Manual confirmation + random spot checks work initially.

⸻

STEP 5: COMPLETION CONFIRMATION

When all required tasks are completed:

Page 4: “You’re officially onboarded 🎉”
	•	Show:
	•	Event name
	•	Date
	•	Wallet address (shortened)
	•	Status:
	•	Physical Ticket: READY
	•	NFT Ticket: PENDING AIRDROP

⸻

STEP 6: PHYSICAL TICKET ISSUANCE (ON-SITE)

Staff dashboard shows:
	•	Name / wallet
	•	Completion status
	•	Button: Issue Physical Ticket

Once clicked:
	•	Status updated
	•	Builder receives physical ticket

📌 This ties digital + physical attendance

⸻

STEP 7: NFT MINTING (POST-EVENT OR LIVE)

NFT Structure
	•	ERC-721 on Avalanche C-Chain
	•	Metadata:
	•	Event name
	•	Date
	•	Location
	•	Artwork (same as physical ticket)
	•	“Avalanche Cascade Adoption Ticket”

You can:
	•	Mint NFTs in bulk after event
	•	OR mint live and airdrop later

⸻

STEP 8: CORE WALLET AIRDROP

Admin Flow
	1.	Export wallet list from dashboard
	2.	Upload CSV to Core Airdrop Tool
	3.	Select NFT
	4.	Airdrop

Wallets receive NFT → Proof of Attendance unlocked

⸻

🧑‍💻 ADMIN DASHBOARD (MVP SCOPE)

Must-have features only:

Dashboard Views
	•	Total attendees
	•	Checked-in
	•	Completed onboarding
	•	Physical tickets issued
	•	NFT airdropped

Export
	•	Wallet addresses (CSV)
	•	Attendance report

⸻

🧩 MVP BUILD PHASES (REALISTIC TIMELINE)

PHASE 1 (Week 1): Foundation
	•	Landing + QR flow
	•	Core Wallet connect
	•	Database schema
	•	Manual task completion

PHASE 2 (Week 2): Event Ops
	•	Luma integration (basic)
	•	Admin dashboard
	•	Physical ticket tracking

PHASE 3 (Week 3): NFT Layer
	•	NFT contract
	•	Metadata design
	•	Core airdrop flow

⸻

🔥 WHAT THIS DOES BETTER THAN ZEALY

Zealy	Your Solution
Generic quests	Event-specific onboarding
Wallet optional	Wallet-first
No physical link	Physical + NFT
Multi-chain clutter	Avalanche-native
Delayed rewards	Instant attendance proof


⸻

🚀 FUTURE UPGRADES (POST-MVP)
	•	Automated X follow verification
	•	Telegram bot verification
	•	Soulbound NFTs
	•	Tiered NFTs (Gold / Builder / Mentor)
	•	Reputation-based rewards
	•	Avalanche Passport integration



🎨 FIGMA READY LAYOUT SPEC

Project: Avalanche Cascade Onboarding MVP
Platform: Mobile-first Web App
Primary Device: iPhone 14 (390 × 844)

⸻

1️⃣ FIGMA FILE STRUCTURE

Avalanche Cascade – Onboarding MVP
│
├── 🎨 Design System
│   ├── Colors
│   ├── Typography
│   ├── Spacing & Grid
│   ├── Buttons
│   ├── Inputs
│   ├── Cards
│   ├── Progress Indicators
│
├── 🧍 Builder Flow (Mobile)
│   ├── 01 – Landing
│   ├── 02 – Wallet Connected
│   ├── 03 – Event Check-In
│   ├── 04 – Tasks
│   ├── 05 – Success
│   ├── 06 – NFT Received
│
├── 🧑‍💼 Admin Dashboard (Desktop)
│   ├── 01 – Overview
│   ├── 02 – Attendees Table
│   ├── 03 – Export
│
└── 🔁 Components (Reusable)


⸻

2️⃣ DESIGN SYSTEM (TOKENS)

🎨 COLORS

Token	Hex	Usage
Primary	#E84142	CTAs, highlights
Primary Dark	#B72E2F	Hover / active
Background	#0B0B0F	Dark mode bg
Surface	#16161D	Cards
Text Primary	#FFFFFF	Headings
Text Secondary	#A1A1AA	Body text
Success	#22C55E	Completed
Warning	#F59E0B	Pending


⸻

✍️ TYPOGRAPHY

Style	Font	Size	Weight
H1	Inter	28	Bold
H2	Inter	22	Semibold
Body	Inter	16	Regular
Small	Inter	14	Regular
Micro	Inter	12	Medium

Line height: 140%

⸻

📐 GRID & SPACING
	•	Frame width: 390px
	•	Horizontal padding: 24px
	•	Vertical spacing scale: 8 / 16 / 24 / 32

⸻

3️⃣ COMPONENT DEFINITIONS

⸻

🔘 BUTTON (Primary)

Auto Layout
	•	Height: 52px
	•	Radius: 12px
	•	Padding: 16px horizontal
	•	Background: Primary
	•	Text: White, 16px semibold

States
	•	Default
	•	Disabled (Opacity 40%)
	•	Loading (Spinner center)

⸻

🧱 CARD
	•	Radius: 16px
	•	Padding: 16px
	•	Background: Surface
	•	Shadow: subtle (optional)

⸻

📊 PROGRESS BAR
	•	Height: 6px
	•	Radius: 6px
	•	Background: #2A2A32
	•	Fill: Primary

⸻

4️⃣ SCREEN-BY-SCREEN FIGMA LAYOUTS

⸻

🧍 SCREEN 01 – LANDING

Frame: 390 × 844

[ Logo ] (Top center, margin 48)

H1: Welcome to Avalanche Cascade
Body: Become an Avalanche Builder in minutes

[ Primary Button ]
Text: Connect Core Wallet

Secondary Text:
“New to Core Wallet?”
Link Button: Download Core Wallet

Spacing:
	•	Logo → H1: 32px
	•	Body → Button: 32px

⸻

🧍 SCREEN 02 – WALLET CONNECTED

✅ Icon (Success green)

H2: Wallet Connected
Text: 0xAbC...91f2

Card:
- Event Name
- Event Date

Primary Button:
Continue


⸻

🧍 SCREEN 03 – EVENT CHECK-IN

Progress Text: Step 1 of 4

H2: Event Check-In
Body: Please check in using Luma

Primary Button:
Open Luma Check-In

Secondary Button (Outline):
I’ve Checked In


⸻

🧍 SCREEN 04 – TASKS

Each task is a reusable component

Progress Text: Step 2 of 4

Task Card:
[ Checkbox ] Follow @AvaxAfrica
[ Action Button ] Follow on X

Task Card:
[ Checkbox ] Join Telegram
[ Action Button ] Join Telegram

Task Card:
[ Checkbox ] Join WhatsApp
[ Action Button ] Join WhatsApp

Task Card (Disabled):
[ ✅ ] Core Wallet Installed

Progress Bar: 75%

Primary Button:
Continue (disabled until complete)


⸻

🧍 SCREEN 05 – SUCCESS

🎉 Icon

H2: You’re Onboarded!

Card:
- Role: Avalanche Builder
- Wallet: 0xAbC...91f2

Status Chips:
🟢 Physical Ticket – READY
🟡 NFT Ticket – PENDING

Text:
Please see a staff member to receive your ticket


⸻

🧍 SCREEN 06 – NFT RECEIVED

🎟 Icon

H2: NFT Ticket Received!

NFT Image (Square, 240px)

Text:
Avalanche Cascade Adoption Ticket
Date

Primary Button:
View in Core Wallet


⸻

5️⃣ ADMIN DASHBOARD (DESKTOP)

Frame: 1440 × 900

⸻

🧑‍💼 ADMIN OVERVIEW

Sidebar (left):
- Overview
- Attendees
- Export

Main Area:
Stat Cards (4):
- Total Attendees
- Checked In
- Completed
- Tickets Issued


⸻

🧑‍💼 ATTENDEE TABLE

Columns:
	•	Name
	•	Wallet
	•	Check-in
	•	Tasks
	•	Ticket
	•	NFT
	•	Action

Row Actions:
	•	Issue Ticket
	•	Mark Complete

⸻

🧑‍💼 EXPORT

Card:
Export Wallet Addresses

Dropdown:
CSV

Primary Button:
Download CSV


⸻

6️⃣ PROTOTYPING NOTES (FIGMA)
	•	Use Smart Animate
	•	Tap → Navigate
	•	Disabled states clearly visible
	•	Prototype flow:
Landing → Wallet → Check-In → Tasks → Success

⸻

7️⃣ HANDOFF CHECKLIST

Give your designer:
	•	This spec
	•	Avalanche brand assets
	•	Physical ticket artwork
	•	Logo SVG
	•	Core Wallet brand guide (optional)


