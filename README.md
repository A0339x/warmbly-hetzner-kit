# Warmbly on Hetzner: setup kit

> **This kit has moved.** It is now the cold email part of AI Business Setup: https://github.com/A0339x/ai-business-setup, in the folder `parts/cold-email`. Use that copy. This repo stays here, but it gets no more updates.

This kit lets Claude Code set up your own cold email server. Claude does the technical work. You sign up, pay, and approve a few things.

## What you get

- Your own server at Hetzner, running Warmbly. Warmbly is an open-source tool for cold email and inbox warmup.
- A web address for it: `https://app.warmbly.<your-domain>`.
- 2 new domains for sending email.
- 10 Google Workspace mailboxes on those domains, 5 on each.
- All 10 mailboxes connected to Warmbly and warming up.

Warmup means the mailboxes send ordinary emails to each other and reply, so Google learns to trust them. Plan on 3 to 4 weeks of warmup before you send real campaigns.

## What it costs

Prices as checked in November 2026. Claude shows you each price again before you pay.

| Item | Price | Billed |
|---|---|---|
| Hetzner CX33 server (4 CPUs, 8 GB memory) | about $10.59 ($9.99 server + $0.60 IPv4 address) | monthly |
| Zapmail Starter plan, 10 Google Workspace mailboxes | $39 | monthly |
| 2 sending domains at Zapmail | about $12.99 each for a .com | yearly |

- First month: about $76.
- After that: about $50 a month, plus about $26 a year for the 2 domains.
- Hetzner may add sales tax or VAT for your country.
- Skip the add-ons Zapmail offers. You do not need them for this setup.

## How long it takes

- About 1 to 2 hours with you nearby. Most of that is waiting on Claude.
- Then up to 3 hours while Zapmail creates the mailboxes. You can walk away.
- Some mailboxes may need a retry about 3 hours after they are first connected. Claude handles it.
- Plan for most of one day. You can stop and pick up later. Claude saves its progress.

## What you do yourself

Claude does the clicking in a browser for you. It stops and says "Your turn" only when it needs you to:
- Choose a password, or sign in. Claude never types your passwords.
- Type a two-step code, or solve a "not a robot" check.
- Enter your card and click Pay. Claude takes you to the checkout page, and you check the total first.
- Click the button that shows a new key, then its Copy button. You do this twice: once at Hetzner and once at Cloudflare. Claude doesn't look at the page until you say "done".
- Pass Hetzner's identity check.

You also choose the 10 sender names and the 2 sending domain names.

## What you need before you start

- A Mac with Claude Code installed.
- A credit or debit card.
- A domain you already own, with access to its DNS settings. Warmbly's web address lives under it, for example `app.warmbly.yourcompany.com`. This domain is not used to send email.
- Your phone, for sign-in codes.
- A way for Claude to click for you. Pick one:
  - **Easier:** the Claude desktop app. It has a browser built in, so there's nothing to install.
  - **Or:** Claude Code in Terminal, plus the Claude extension for Google Chrome: https://chromewebstore.google.com/detail/claude/fcoeoabgfenejglbffodgkkbkcdhcgfn. Sign in to it with your Claude account. This needs a Claude Pro plan or higher, and doesn't work with an API key.
- Without either one, you do every click yourself while Claude tells you what to press.

## What to know about sending

- US law (CAN-SPAM) requires an honest sender name and subject line, your real postal address in every email, and a working unsubscribe link.
- Do not use domains that imitate someone else's brand.
- Warmbly's own documents say warmup on a self-hosted server is weaker than on Warmbly's paid cloud service. Your 10 mailboxes warm up only with each other.
- Warmbly cannot send its own emails yet, such as password resets. If you forget your Warmbly password, ask Claude to reset it on the server.

## Where things are kept

- On your Mac: `~/.config/warmbly-kit/`. Only your user account can read it. It holds your tokens, the mailbox passwords, and a backup of Warmbly's two encryption keys.
- On the server: `/opt/warmbly`.
- **Keep the key backup safe.** If both copies of Warmbly's two encryption keys are lost, every mailbox password stored in Warmbly becomes unreadable.

## How to start

**In the Claude desktop app (easier):**
1. Open the Claude desktop app and go to Claude Code.
2. Choose this folder.
3. Say: "Read CLAUDE.md and set up Warmbly. Take control of the browser and do the clicks for me. I'll only handle sign-ins and payments."

Keep the app's Browser pane showing when Claude says "Your turn". If it's hidden, press Cmd+Shift+B.

**Or in Terminal, with Chrome:**
1. Open Terminal in this folder.
2. Run: `claude --chrome`
3. Say the same sentence as above.

If Claude asks whether it may act on a website, allow it for this session.

## For Claude

Start with `CLAUDE.md`, then `RUNBOOK.md`.
