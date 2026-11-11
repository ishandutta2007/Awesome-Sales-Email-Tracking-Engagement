# Awesome-Sales-Email-Tracking-Engagement

# Awesome Sales Email Tracking & Engagement

> A curated list of top Sales Email Tracking and Engagement platforms — both SaaS/Hosted commercial solutions and open-source alternatives for tracking opens, clicks, and replies to optimize outbound sales efforts.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [HubSpot Sales Hub](#hubspot-sales-hub)
  - [Outreach](#outreach)
  - [Salesloft](#salesloft)
  - [Mixmax](#mixmax)
  - [Yesware](#yesware)
  - [Lemlist](#lemlist)
  - [Streak CRM](#streak-crm)
- [Open-Source Software](#-open-source-software)
  - [OpenTracker (Gmail)](#opentracker-gmail)
  - [email-tracker-go](#email-tracker-go)
  - [Pigeon](#pigeon)
  - [Signal](#signal)
  - [Helio](#helio)
  - [Reloop](#reloop)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Sales Email Tracking and Engagement platforms. These are not open-source but are included as reference points for feature comparison.

### HubSpot Sales Hub
**Type:** CRM-integrated email tracking and sequences
HubSpot Sales Hub combines email tracking (opens, clicks, replies) with CRM integration, sequences, and meeting scheduling. It is the default choice for organizations already using HubSpot CRM, with tracking data automatically associated with contact records. Pricing is per-seat with tiered features.

### Outreach
**Type:** Sales engagement platform with sequence automation
Outreach provides multi-step sales sequences, email tracking, call logging, and analytics. It is a long-standing enterprise standard for sales engagement, with deep CRM integrations and conversation intelligence capabilities.

### Salesloft
**Type:** Sales engagement with cadence and analytics
Salesloft offers email tracking, cadences, and conversation analytics for sales teams. It is a direct competitor to Outreach, with a focus on rep productivity and manager visibility into outbound activity.

### Mixmax
**Type:** Email tracking with interactive content
Mixmax provides email tracking (opens, clicks, downloads), sequences, and interactive email features like polls and scheduling links. It is popular with Gmail users wanting advanced tracking and engagement features without leaving their inbox.

### Yesware
**Type:** Email tracking and prospecting for Gmail/Outlook
Yesware provides email tracking, templates, and prospecting tools directly within Gmail and Outlook. It is a long-standing choice for individual reps and small teams wanting tracking without a full sales engagement platform.

### Lemlist
**Type:** Cold email outreach with personalization
Lemlist specializes in cold email outreach with personalized images, sequences, and tracking. It includes email warm-up and deliverability features, positioned for agencies and sales teams running high-volume outbound campaigns.

### Streak CRM
**Type:** CRM and tracking within Gmail
Streak CRM operates entirely within Gmail, providing email tracking, pipelines, and CRM functionality. It is a lightweight option for teams already living in Gmail who want tracking and deal management without a separate application.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Sales Email Tracking and Engagement tools. The open-source ecosystem spans **privacy-first Gmail trackers**, **API-based tracking services**, **full outreach platforms**, and **AI-powered sales intelligence**.

### OpenTracker (Gmail)
**Stack:** Chrome Extension / Cloudflare Workers / D1 | **License:** Open Source (per repository)
OpenTracker is a self-hosted, privacy-first email open and link-click tracker for Gmail, positioned as a free Mailtrack alternative [citation:4]. Key features include:
- **Self-hosted on Cloudflare's free tier** — data stays in your own Cloudflare account, no third-party services, no ads appended to emails, unlimited tracking
- **Open tracking** with timestamp, count, and email client detection
- **Link click tracking** with automatic link rewriting and HMAC-SHA256 signatures to prevent open-redirect abuse
- **Gmail list indicators** showing ✓/✓✓ read status before subject lines
- **Per-email toggle** and global on/off switch
- **Bot filtering** and self-open exclusion

Deploys via a Chrome extension that injects a tracking pixel and rewrites links, with a Cloudflare Worker handling tracking and a D1 database for storage [citation:4].
**Best for:** Gmail users wanting a free, privacy-respecting Mailtrack alternative that runs entirely on their own Cloudflare account with no tracking limits.

### email-tracker-go
**Stack:** Go / Redis / Gin | **License:** Open Source (per Go package)
email-tracker-go is a Go service for sending and tracking emails, using Redis for storage [citation:2]. Features include:
- **Pixel-based open tracking** with a 1×1 transparent PNG endpoint
- **Custom HTML templates** with variable substitution
- **Tracking status API** returning first open, last open, and total count
- **Configurable tracking expiration** (default 1 day)

Setup requires Go 1.16+, a Redis server, and SMTP credentials. API endpoints include `POST /send`, `GET /pixel/:tracking_id`, and `GET /status/:tracking_id` [citation:2].
**Best for:** Go developers wanting a lightweight, embeddable email tracking service with Redis-backed status persistence.

### Pigeon
**Stack:** Next.js / MongoDB / Docker | **License:** Open Source (per repository)
Pigeon is an open-source cold email outreach and deliverability platform with extensive tracking and warm-up features [citation:10]. Key capabilities include:
- **Multi-step sequences** that stop on reply, bounce, or unsubscribe
- **A/B testing** with auto-selected winners (60% reply rate, 40% open rate weighting)
- **Inbox rotation** across Gmail and SMTP mailboxes
- **Mailbox warm-up** with threaded conversations and realistic engagement rates (30-50%)
- **DNS automation** for SPF/DKIM/DMARC via Cloudflare, GoDaddy, Namecheap, or Google Cloud DNS
- **Custom tracking domains** for branded open pixels and click links
- **Inbox placement testing** through real Gmail and Outlook seed accounts
- **AI writing** using your own OpenAI, Anthropic, or other keys

Deploys via Docker Compose with MongoDB included [citation:10].
**Best for:** Teams wanting a comprehensive self-hosted cold email platform with advanced deliverability, warm-up, and tracking without SaaS fees.

### Signal
**Stack:** Next.js / Supabase / Claude | **License:** Open Source (per repository)
Signal is an open-source AI sales intelligence and outreach automation platform positioned as an alternative to Clay, Apollo, and Outreach [citation:3]. Features include:
- **Signals engine** watching for buying triggers (hiring, funding, product launches)
- **Contact enrichment** pulling LinkedIn, GitHub, and company pages
- **Outreach sequences** with multi-step emails sent from your own Gmail, including reply and bounce tracking
- **Chat-driven campaign workspace** backed by Claude

**Important:** Signal is designed for single-tenant self-hosting, and migrations have been destructive across versions (Clerk auth migration wipes user data). Requires Supabase, Anthropic API key, and Gmail app password [citation:3].
**Best for:** Technical teams wanting AI-assisted sales intelligence and outreach with full data ownership, accepting that the project is evolving rapidly with breaking changes.

### Helio
**Stack:** TypeScript / PostgreSQL / ClickHouse / Temporal | **License:** AGPL-3.0
Helio is an open-source, AI-native growth platform combining a CDP, visual journey orchestration, and marketing automation . Tracking features include:
- **Email open-pixel and HMAC-signed click tracking**
- **Event-stream funnel analytics** via ClickHouse
- **Multi-channel delivery** (email, SMS, WhatsApp, web push, in-app)
- **AI copilot** for segments, journeys, and emails
- **CRM-lite** with pipelines and deal boards

Helio is free forever with no contact caps or metering . It is a broader marketing platform rather than a pure sales email tracker.
**Best for:** Teams wanting an open-source marketing automation platform with built-in email tracking, multi-channel journeys, and CRM capabilities.

### Reloop
**Stack:** Node.js / PostgreSQL / Docker | **License:** Apache 2.0 (with use restrictions)
Reloop is an open-source transactional email API and self-hostable Resend alternative [citation:5]. Features include:
- **Transactional email** via REST API and SMTP
- **Email campaigns** with audience segmentation
- **Real-time analytics** (open rates, click rates, bounces) stored in PostgreSQL
- **Webhooks** for delivery events
- **Visual template editor**

Deploys via a one-command installer on Ubuntu/Debian [citation:5]. It is email infrastructure rather than a sales-specific tracking tool.
**Best for:** Developers wanting a self-hosted email sending platform with built-in open/click analytics, rather than a dedicated sales tracking extension.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Tracking Type | Sales-Specific | Self-Hosted | Best For |
|----------|---------|-------|---------------|----------------|-------------|----------|
| **HubSpot Sales Hub** | Proprietary | Cloud | Opens/clicks/replies | ✅ | ❌ | CRM-integrated tracking |
| **Outreach** | Proprietary | Cloud | Opens/clicks/replies | ✅ Sequences | ❌ | Enterprise sales engagement |
| **Mixmax** | Proprietary | Cloud | Opens/clicks/downloads | ✅ | ❌ | Gmail power users |
| **OpenTracker** | Open Source | Chrome/Cloudflare | Opens/clicks | (Gmail) | ✅ | Free Mailtrack alternative |
| **email-tracker-go** | Open Source | Go/Redis | Opens | ❌ | ✅ | Embeddable tracking service |
| **Pigeon** | Open Source | Next.js/MongoDB | Opens/replies/bounces | ✅ Cold email | ✅ | Self-hosted outreach + warm-up |
| **Signal** | Open Source | Next.js/Supabase | Replies/bounces | ✅ AI outreach | ✅ | AI sales intelligence |
| **Helio** | AGPL-3.0 | TS/Postgres | Opens/clicks (signed) | (Marketing) | ✅ | Marketing + CRM-lite |
| **Reloop** | Apache 2.0 | Node.js/Postgres | Opens/clicks | ❌ | ✅ | Email infra + analytics |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Sales Email Tracking or Engagement tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** between **privacy-first Gmail trackers** (OpenTracker, running on Cloudflare's free tier with no tracking limits [citation:4]), **lightweight tracking APIs** (email-tracker-go for Go developers [citation:2]), **full outreach platforms** (Pigeon with warm-up and DNS automation [citation:10], Signal with AI intelligence [citation:3]), and **broader marketing platforms with tracking** (Helio , Reloop [citation:5]). No open-source project fully replicates the sales-specific sequence analytics and CRM integration of Outreach or Salesloft, but Pigeon and Signal cover meaningful subsets of the cold outreach workflow.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
