# LinkedIn Scam Detector

## Overview

The **LinkedIn-Scam-Detector** is a Claude skill that automates the verification of recruiter messages and job offers. Modern recruitment scams are sophisticated—they clone legitimate profiles, use official-looking email addresses, and exploit your career history to build false trust. This tool helps identify suspicious communications through automated investigation.

## How It Works

When you ask Claude to verify a recruiter message, the skill performs the following checks:

1. **Pattern Analysis:** Scans for phishing indicators such as artificial urgency, vague job descriptions, and suspicious attachments.
2. **Domain Verification:** Cross-references the sender’s email domain against known corporate formats and verifies whether the address format is legitimate.
3. **LinkedIn Profile Assessment:** Examines the sender’s LinkedIn profile for red flags such as new accounts, low engagement, or inconsistent tenure.
4. **Job Role Validation:** Checks the company’s official careers page and LinkedIn Jobs to confirm whether the advertised position exists.
5. **Official Contact Verification:** Retrieves the company’s verified contact information so you can independently confirm the opportunity through official channels.

## Requirements

To use the LinkedIn-Scam-Detector skill, you need:

- **Claude Code (CLI):** For executing the skill logic and managing the investigation workflow
- **Claude for Chrome Extension:** Enables Claude to navigate your browser, access LinkedIn, email, and company career pages
- **An active LinkedIn account:** Required to perform profile verification checks

## Installation

1. Ensure you have Claude Code and the Claude for Chrome extension installed
2. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/linkedin-scam-detector.git
   ```

3. Follow the skill installation instructions in the Claude Code documentation

## Usage

Once installed, you can ask Claude to verify a recruiter message:

```text
"Verify this recruiter from Amazon"
```

or

```text
"Check this job offer for legitimacy"
```

Provide the recruiter’s email, LinkedIn profile URL, or forwarded message, and Claude will run the verification checks automatically.

## Notes

- No tool is a substitute for careful verification. Always independently confirm opportunities through official company channels.
- This is an open-source project. Contributions and feedback are welcome on GitHub.
- The skill respects your privacy and only accesses information you explicitly share with it.
