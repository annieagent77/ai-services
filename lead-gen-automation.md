# Lead Gen Automation - Service Template

## Overview
This is the deliverable for the Lead Gen Automation service. It includes:
1. AI Chatbot for website (Tidio)
2. Missed Call → Text Back (Google Voice / NextPhone)
3. Auto follow-up sequence (Make + Gmail)
4. Calendar booking integration (Calendly)

---

## Part 1: AI Chatbot Setup (Tidio)

### Step 1: Create Tidio Account
1. Go to https://tidio.com and sign up
2. Add your website domain
3. Install the chat widget code

### Step 2: Configure Chatbot
Navigate to Apps → Lyro (AI) → Enable

### Step 3: Training Q&A
Add these common responses:

**Q: What services do you offer?**
A: We offer [list your services]. Would you like me to schedule a free consultation?

**Q: How much does it cost?**
A: Our services start at $297. Can I send you a detailed price list?

**Q: Do you offer free estimates?**
A: Yes! We offer free consultations. Would you like to schedule one?

**Q: Are you available this week?**
A: We have availability! What's the best time to reach you?

### Step 4: Lead Collection
Set up Tidio to collect:
- Name
- Email
- Phone
- Service interest
- Best time to contact

---

## Part 2: Missed Call Text Back

### Option A: Google Voice (Free)
1. Set up Google Voice number
2. Enable voicemail transcription
3. Create auto-reply via Google Scripts

### Option B: NextPhone ($9/mo)
1. Sign up at https://nextphone.com
2. Configure "Missed Call Text Back"
3. Set custom message:

```
Thanks for calling [Business Name]! We missed your call but got your number. Reply YES to schedule a callback, or visit [website] to book online.
```

---

## Part 3: Auto Follow-Up Sequence (Make)

### Scenario: New Lead from Website

**Trigger:** New form submission in Tidio / Website form

**Action 1:** Create Google Sheet row (lead tracking)
- Sheet: Lead Database
- Columns: Name, Email, Phone, Source, Date, Status

**Action 2:** Send welcome email (Gmail)
```
Subject: Thanks for reaching out!
Body:
Hi {{name}},

Thanks for contacting us! We've received your inquiry and a team member will reach out within 2 hours.

In the meantime, you can:
- Book a time directly: [calendly-link]
- Learn more about our services: [website]

See you soon!
[Business Name]
```

**Action 3:** Add to email sequence (wait 2 days)
- Send "Following up" email
- Add phone call task to Google Calendar

**Action 4:** If no response after 5 days
- Send final "Last chance" email
- Mark as "Cold Lead"

---

## Part 4: Calendar Integration

### Calendly Setup
1. Create Calendly account
2. Set up event types:
   - "Free Consultation" (15 min)
   - "Quote Request" (30 min)
3. Configure:
   - Buffer time between meetings
   - Custom confirmation email
   - Reminder emails (24h, 1h before)

### Embed in Website
Add to contact page:
```html
<!-- Calendly inline widget begin -->
<div class="calendly-inline-widget" data-url="https://calendly.com/YOUR_LINK/30min" style="min-width:320px;height:630px;"></div>
<script type="text/javascript" src="https://assets.calendly.com/assets/external/widget.js" async></script>
<!-- Calendly inline widget end -->
```

---

## Part 5: Complete Integration Flow

```
Website Visitor
    ↓
Tidio Chatbot (24/7)
    ↓ (qualifies lead)
Lead → Make.com
    ↓
1. Add to Google Sheet
2. Send welcome email
3. Create follow-up task
4. Add to email sequence
    ↓
2 hours: Human follow-up call
    ↓
Schedule via Calendly
    ↓
CRM → Client
```

---

## Monthly Cost

| Tool | Cost | Purpose |
|------|------|---------|
| Tidio (Free tier) | $0 | Chatbot |
| Make.com (Free tier) | $0 | Automation |
| Gmail | $0 | Email |
| Calendly (Free tier) | $0 | Booking |
| Google Sheets | $0 | Database |
| **Total** | **$0** | Full system! |

---

## Deliverable Checklist for Client

- [ ] Tidio account created + chatbot configured
- [ ] Website chat widget installed
- [ ] Missed call text back configured
- [ ] Make.com automation set up
- [ ] Calendly integrated
- [ ] Test lead capture flow
- [ ] Client training (15 min video)