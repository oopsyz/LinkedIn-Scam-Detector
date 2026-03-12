# linkedin-scam-detector

Detect fake recruiter emails and job offer scams before you respond.

> **Requirements:** This plugin requires [Claude Code](https://claude.ai/code) and the [Claude in Chrome extension](https://chromewebstore.google.com/detail/claude-in-chrome/). The browser automation steps (opening your email, visiting LinkedIn, checking the careers page) rely on Claude's ability to control your browser through the Chrome extension.

## What it does

When you receive a suspicious recruiter email or LinkedIn message, this skill runs a full 5-step investigation automatically:

1. **Opens your email** in the browser (Gmail, Outlook, Yahoo, or other)
2. **Analyzes the email content** for red flags — urgency, vague roles, suspicious links, requests for personal data
3. **Verifies the sender's domain and email format** — checks whether the email matches the company's known format (e.g. `first.last@company.com`) using public directories like RocketReach
4. **Opens LinkedIn in the browser** to inspect the recruiter's profile directly — checks tenure, connections, activity, and profile photo
5. **Searches for the job on the company's careers page and LinkedIn Jobs** — verifies the role actually exists
6. **Finds the company's verified phone number** and warns you not to trust caller ID, since scammers spoof legitimate company numbers

## Usage

Just mention the email or message to Claude:

- "Is this recruiter email legit?"
- "Check this job offer for me"
- "Is this a scam?"
- "Verify this recruiter from Amazon"

The skill triggers automatically and walks you through the full investigation.

## Requirements

- [Claude Code](https://claude.ai/code) CLI installed and running
- [Claude in Chrome extension](https://chromewebstore.google.com/detail/claude-in-chrome/) installed in your Chrome browser
- Chrome browser open and connected to Claude Code

The Chrome extension is essential — it allows Claude to open your email in the browser, navigate to LinkedIn, inspect profiles, and check company careers pages automatically.

## Installation

```
/plugin install linkedin-scam-detector
```

## Why this matters

Recruiter impersonation scams are increasingly sophisticated. Scammers:

- Copy real recruiter names and profile photos from LinkedIn
- Use Gmail addresses structured to look official (e.g. `jsmith.recruit.google@gmail.com`)
- Reference your real background from LinkedIn to seem credible
- Follow up with phone calls from spoofed company numbers

This skill cross-references every claim against primary sources — the company's official domain, LinkedIn, their careers page, and public employee directories — so you can verify before you engage.

## Contributing

Scam tactics evolve constantly — new patterns, new platforms, new tricks. Contributions are welcome!

**Ways to contribute:**
- **New red flags** — spotted a scam pattern not covered? Open a PR adding it to the detection checklist
- **New email providers** — add support for webmail services beyond Gmail, Outlook, and Yahoo
- **New verification sources** — know a better directory or job board to cross-reference against?
- **Real scam examples** — share anonymized examples to help improve detection accuracy
- **Bug reports** — if the skill breaks on a particular flow, open an issue

To contribute, open a pull request or issue at **https://github.com/oopsyz/LinkedIn-Scam-Detector**. Please do not include any real personal information in examples.

## Reporting scams

- LinkedIn: <https://linkedin.com/help/linkedin/answer/a1442749>
- FTC: <https://reportfraud.ftc.gov>
