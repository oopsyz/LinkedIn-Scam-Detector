# linkedin-scam-detector

Verify recruiter messages and job offers before responding to recruitment scams.

## Overview

The **LinkedIn-Scam-Detector** is a Claude skill that automates verification of recruiter communications. Modern recruitment scams are sophisticated—they clone legitimate profiles, use official-looking email addresses, and exploit your career history to build false trust. This skill helps identify suspicious communications through automated investigation.

## How It Works

When you ask Claude to verify a recruiter message, the skill performs the following checks:

1. **Pattern Analysis:** Scans for phishing indicators such as artificial urgency, vague job descriptions, and suspicious attachments.
2. **Domain Verification:** Cross-references the sender's email domain against known corporate formats and verifies whether the address format is legitimate.
3. **LinkedIn Profile Assessment:** Examines the sender's LinkedIn profile for red flags such as new accounts, low engagement, or inconsistent tenure.
4. **Job Role Validation:** Checks the company's official careers page and LinkedIn Jobs to confirm whether the advertised position exists.
5. **Official Contact Verification:** Retrieves the company's verified contact information so you can independently confirm the opportunity through official channels.

## Usage

Ask Claude to verify a recruiter message:

- "Is this recruiter email legit?"
- "Check this job offer for me"
- "Is this a scam?"
- "Verify this recruiter from Amazon"

## Requirements

- [Claude Code](https://claude.ai/code) CLI installed and running
- [Claude for Chrome extension](https://chromewebstore.google.com/detail/claude-in-chrome/) installed in your Chrome browser
- Active LinkedIn account for profile verification checks

## Installation

1. Ensure you have Claude Code and the Claude for Chrome extension installed
2. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/linkedin-scam-detector.git
   ```

3. Follow the skill installation instructions in the Claude Code documentation

## Why This Matters

Modern recruiter scams are increasingly sophisticated:

- Clone real recruiter names and profile photos from LinkedIn
- Use official-looking Gmail addresses (e.g., `recruiter.google@gmail.com`)
- Reference your actual career history to build false trust
- Spoof legitimate corporate phone numbers

This skill helps you verify claims against primary sources—the company's official domain, LinkedIn profiles, and careers pages—before you respond.

## Notes

- No tool is a substitute for careful verification. Always independently confirm opportunities through official company channels.
- Report confirmed scams to LinkedIn and the FTC (see links below).
- The skill respects your privacy and only accesses information you explicitly share with it.

## Contributing

Contributions are welcome! To contribute, open a pull request or issue on GitHub.

**Ways to contribute:**

- Report new scam patterns or red flags
- Add support for additional email providers
- Improve detection accuracy with real scam examples (anonymized, no personal information)
- File bug reports for issues encountered

## Resources

- **Report to LinkedIn:** <https://linkedin.com/help/linkedin/answer/a1442749>
- **Report to FTC:** <https://reportfraud.ftc.gov>
