# That "Recruiter" in Your Inbox Might Be a Scammer

In 2026, I've stopped trusting recruiter messages at face value. And honestly? You probably should too.

It started innocuously enough—a message from "Sarah Chen, Talent Acquisition Manager at Microsoft." The profile looked real. The message was personalized. The salary range made me pause. But something felt off.

So I did what I always do: I started digging. LinkedIn profile? New account, barely any activity. Email domain? Not actually microsoft.com, but something close. The job opening? Doesn't exist on their careers page.

This has become the norm. Modern scammers—whether they're automated systems or strategic impostors—have evolved past broken English and obvious red flags. They now:

- Clone real recruiter profiles down to the pixel
- Craft official-looking email addresses
- Reference your actual career history to build credibility
- Even spoof company phone numbers

The threat isn't whether you're talking to a human or a bot. The threat is whether you're being scammed. Manual vetting used to be a chore. Now it's a security necessity.

**I built a tool that does this automatically—and it's free and open-source.**

Rather than spend 30 minutes playing detective every time, I created the **LinkedIn-Scam-Detector**—a Claude skill that runs a comprehensive verification in seconds. It's free, it's open-source, and it's designed to help everyone stay safer.

But here's the important part: **scam tactics evolve constantly.** Every time you encounter a suspicious recruiter, you're seeing a new variation—a new angle scammers are using. If we're going to stay ahead, we need your feedback. Have you seen a pattern we're missing? Does the tool miss a red flag you'd expect it to catch? Your insights directly improve the detection logic for everyone else.

Ask it to check a recruiter message, and it:

1. **Analyzes the message** for phishing indicators—artificial urgency, vague descriptions, red-flag language
2. **Verifies the sender's domain** against known corporate formats
3. **Inspects their LinkedIn profile** for suspicious patterns (new accounts, low engagement, fake tenure)
4. **Confirms the job exists** on the company's official careers page and LinkedIn Jobs
5. **Finds official contact information** so you can verify through legitimate channels

It's not a silver bullet. No tool is. But it adds friction for scammers who rely on your speed and excitement.

**The setup is simple:**

- You need Claude Code and the Claude for Chrome extension (so Claude can actually see and navigate your browser)
- You ask Claude: *"Verify this recruiter from Amazon"* or *"Check this job offer"*
- Claude does the legwork

**You get peace of mind.**

**Help us protect everyone.** This is a free, open-source project. If you encounter a scam pattern we're missing or think of a better way to detect fraud, open an issue or submit a PR. Every improvement you contribute makes the tool better for thousands of people.

**Get started here:** <https://github.com/oopsyz/LinkedIn-Scam-Detector>

If this tool helps you avoid one bad interaction, I'd consider it a win. If it helps someone in your network? That's the whole point. If you find it useful, a share or star helps bring more people into a safer professional community.

Stay vigilant out there. 🛡️
