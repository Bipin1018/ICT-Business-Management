# Mohar — landing page and interactive prototype

A white-label subscription feature that a bank embeds inside its own mobile banking app.
University artefact for ICT Business Management (Artefact 3).

- **Landing page (for banks):** https://bipin1018.github.io/ICT-Business-Management/
- **Live prototype (for customers):** https://bipin1018.github.io/ICT-Business-Management/prototype/

| Folder | What it is |
|---|---|
| `index.html` | Bank-facing product landing page. All statistics link to their original sources in the footer. |
| `prototype/index.html` | The working prototype — the customer's critical journey. |
| `assets/` | Screenshots taken from the working prototype, used on the landing page. |

## What it does

1. **Warns before the money leaves** — 3 days before every renewal, 7 before a free trial converts, 14 before a yearly charge.
2. **Covers what card data can't see** — app store, PayPal and family-plan subscriptions are added in a few taps.
3. **Points to the exit** — where each subscription is managed, its cancellation page, and the deadline.
4. **Confirms it stopped** — next month it checks the charge really disappeared, and flags it if not.

It never cancels anything for the customer, never blocks a payment, and gives no budgeting advice.

## Try it

Open `prototype/index.html` in a browser — no build step, no server, no dependencies (one Google Fonts link).
On a computer it opens as a phone in a frame, with the tester guide beside it (a full-screen laptop view is one click away);
on a phone it fills the screen, the tester guide sits behind the **Test guide** button, and a **Demo: jump a month ahead** button appears when task 3 needs it.
Progress survives an accidental refresh (sessionStorage); **Reset demo** clears it.

Tester tasks (shown in the demo controls):

1. You've been notified about a charge. Stop it before Friday.
2. Your music is billed by your phone's app store. Add it so the total is real.
3. A month has passed. Check whether your cancellation worked. (Use **Fast-forward one month**.)
4. Optional: jump one more month. A charge you stopped came back — sort it out.

Press **Reset demo** before each new tester.

## How the code is organised

Everything is in `index.html`: design tokens and CSS at the top, then one script.

- **One state object** (`state`) holds subscriptions, the demo clock and every decision.
- **Each screen is a function** that reads `state` and returns HTML; `refresh()` redraws from state,
  so numbers on screen can never disagree with the data.
- **Buttons carry `data-action`**; one click listener looks the action up in the `actions` object.
- **Hash routes** (`#/hub`, `#/detail/pixelcraft`, …) keep the browser back button working.
- Amounts are stored in **cents** so totals are exact (€68.95 → €79.94 → €56.94).

## Team

Bipin Bhandari · Suyog Acharya · Aayush Darlami · Dhrumil Patel · Kshitij Banarjee

All banks, services, people, figures and data are fictional.
