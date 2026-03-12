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

**I built a tool that does this automatically.**

Rather than spend 30 minutes playing detective every time, I created the **LinkedIn-Scam-Detector**—a Claude skill that runs a comprehensive verification in seconds. Ask it to check a recruiter message, and it:

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

This is an open-source project, and I'm actively looking for feedback and PRs. Scam tactics evolve constantly—if you've seen patterns we're missing, help us catch them.

If this tool helps you avoid one bad interaction, I'd consider it a win. If it helps someone in your network? That's the whole point.

The GitHub link is in the comments. If this resonates, a share or star helps keep our professional community a bit more secure.

Stay vigilant out there. 🛡️
