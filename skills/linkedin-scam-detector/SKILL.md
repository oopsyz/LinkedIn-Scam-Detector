---
name: linkedin-scam-detector
description: Analyze a recruiter email or LinkedIn message to detect scams, phishing attempts, and fraudulent job opportunities. Use this skill whenever the user pastes a recruiter email, LinkedIn message, or job offer and wants to know if it's legitimate. Trigger on phrases like "is this legit", "check this recruiter", "verify this job offer", "is this a scam", "LinkedIn message", "recruiter email", or any time the user shares unsolicited job communication for review.
---

# Recruiter Scam Detector

Detect scam recruiter emails and job offers through a 5-step investigation: open the user's email, analyze the message, verify the sender's domain and email format, cross-reference the recruiter and job on LinkedIn and the company website, and find a verified phone number for the user to call directly.

## Your Goal

Walk the user through a complete scam investigation using their browser. Start by opening their email, then systematically verify every claim in the recruiter's message. Be direct and specific — vague warnings aren't helpful.

---

## Step 0: Open the User's Email

Before anything else, ask the user which email service they use:

> Which email provider should I open?
> - Gmail
> - Outlook / Hotmail
> - Yahoo Mail
> - Other

Then navigate the browser to the appropriate webmail site:
- Gmail → `https://mail.google.com`
- Outlook → `https://outlook.live.com`
- Yahoo → `https://mail.yahoo.com`
- Other → ask the user for the URL

Once the inbox loads, ask the user to point out the suspicious email (or find it based on their description). Open the email and use `read_page` or `get_page_text` to extract:
- Sender name and full email address (expand headers if needed)
- Subject line
- Full message body
- Any links in the message (hover to reveal actual URLs)

---

## Step 1: Email Content Analysis

Read the extracted message carefully and scan for red flags.

**Language & Content Red Flags**
- Salary/compensation unrealistically high for the role or industry
- Urgency pressure ("respond within 24 hours", "this offer expires soon")
- Vague job description — no specific responsibilities, team, or product mentioned
- Generic flattery ("we've been watching your profile closely")
- Requests for personal data upfront (SSN, bank info, ID documents, login credentials)
- Links to external sites that differ from the company's known domain
- Poor grammar, inconsistent capitalization, or odd phrasing for professional communication
- Claims of remote work with unusually high pay and minimal requirements
- Mentions of cryptocurrency, gift cards, or wire transfers for any reason
- The role doesn't match the sender's claimed title or company
- Asks you to download software, install apps, or join unfamiliar platforms
- Requests payment for training, equipment, or background checks

**Tone & Structure**
- Does it read like a real recruiter wrote it, or a template/AI fill-in?
- Is the company name mentioned specifically, or kept vague?
- Does the message reference anything specific about the recipient's background?
- Is the email a reply to an application the user actually submitted, or completely unsolicited?

**Email Header Clues** (if available)
- Reply-To address differs from the From address
- Sent via unusual mail servers or bulk email services
- Missing or suspicious SPF/DKIM/DMARC indicators

Score: **Low / Medium / High**

---

## Step 2: Sender Domain & Email Format Verification

Extract the sender's full email address from the message.

### 2a. Domain Check

1. **Check the domain**: A legitimate recruiter at `Google` should email from `@google.com`, not `@google-careers.net` or `@gmail.com`. Free email providers (Gmail, Yahoo, Hotmail, Outlook personal) are a major red flag for enterprise recruiters.

2. **Look for domain spoofing**: Domains like `amazon-jobs.com`, `microsoft-hiring.net`, `meta-careers.org` are NOT official. The only legitimate domain is the company's primary domain (e.g., `amazon.com`, `microsoft.com`, `meta.com`).

3. **Check domain age**: Use WebSearch to look up the domain. Recently registered domains (less than a year old) impersonating well-known companies are a strong scam signal.

4. **If no email is visible**: Note this as a gap and advise the user to check the sender's full email header before replying.

### 2b. Company Email Format Lookup

Search for the company's known employee email format to see if the sender's address matches:

1. **Search**: Use WebSearch for `"[company name]" email format site:rocketreach.co` or `"[company name]" email format site:hunter.io` or `"[company name]" employee email format`.
2. **Common formats**: Most companies use patterns like `first.last@company.com`, `flast@company.com`, `firstl@company.com`, etc.
3. **Compare**: Does the sender's email address match the known format? For example, if Anduril uses `jwallace@anduril.com` but the email came from `jwallace.recruit.anduril@gmail.com`, that's a mismatch.

### 2c. Employee Directory Check

Search for the recruiter in public employee directories:

1. **Search**: Use WebSearch for `"[recruiter name]" "[company name]" email` on sites like RocketReach, Hunter.io, ZoomInfo, or SignalHire.
2. **Check**: Does the recruiter appear in the directory? Does their listed email match the one in the message?
3. **If found with a corporate email**: The sender should be using that corporate email, not a free provider. A mismatch is a strong red flag.

Score: **Low / Medium / High / Unknown**

---

## Step 3: Recruiter & Company Cross-Reference (Browser-Based)

Investigate the recruiter and company by opening sites directly in the browser.

### 3a. LinkedIn Profile Verification

1. **Find the profile**: Use WebSearch to find the recruiter's LinkedIn URL: `"[recruiter name]" "[company name]" site:linkedin.com`. Extract the profile URL.

2. **Open the profile in a new browser tab**: Navigate to the LinkedIn profile URL. Use `read_page`, `get_page_text`, or take a screenshot to extract profile details.

3. **Inspect the profile for these signals**:
   - **Current employer**: Does the profile show the claimed company as their current role? Check job title matches.
   - **Tenure**: How long have they been at this company? Brand new = red flag.
   - **Work history**: Do they have a credible career progression, or did the profile appear recently with sparse history?
   - **Connections**: Check the connection count — real recruiters at major companies typically have 500+ connections.
   - **Activity**: Scroll down or check for recent posts/comments. Real recruiters actively post about job openings and engage with content.
   - **Profile photo**: Take a screenshot and visually inspect — does the photo look like a real person or an AI-generated/stock image?
   - **Recommendations**: Real professionals accumulate endorsements and recommendations over time.

4. **Check the company's LinkedIn page**: Navigate to the company's LinkedIn page and verify:
   - The recruiter appears in the "People" section when filtered by the recruiting/HR department
   - The company page is verified and has a substantial follower count

### 3b. Job Posting Verification (Browser-Based)

**Search for the specific job mentioned in the email** to see if it actually exists.

1. **Company careers page**: Navigate to `[company domain]/careers` or the careers URL found via search. Use the site's search to look for the role or role type mentioned in the email.

2. **LinkedIn Jobs**: Navigate to LinkedIn Jobs and search for the job title + company name. Check if the listing exists and matches what the email describes.

3. **Other job boards**: Search on Indeed, Glassdoor, or other major boards for the same role at the same company.

4. **Compare**: Does the job actually exist on official channels? If the email mentions a role that doesn't appear anywhere on the company's own postings, that's a significant red flag.

### 3c. Scam Reports

Search for `"[company name]" recruiting scam` or `"[recruiter email domain]" scam`. Check if:
- Others have reported similar scam outreach from this company name or domain
- The company name appears on scam warning sites (BBB, FTC, ScamAdviser, Reddit)

### 3d. Cross-Check Summary

- Does the recruiter's LinkedIn (verified in browser) show the claimed company as their current employer?
- How long have they been there?
- Does the sender's email match the company's known email format?
- Does the job mentioned in the email appear on the company's careers page or LinkedIn Jobs?
- Does the company's LinkedIn "People" section include this recruiter?

Score: **Low / Medium / High / Unknown**

---

## Step 4: Verified Phone Number Lookup

This step is critical — scammers often call from spoofed phone numbers that appear to be from the real company.

1. **Find the company's official phone number**: Use WebSearch to find the phone number from the company's **official website** (look for Contact Us, Careers, or HR pages). Cross-reference with Google Business listing or LinkedIn company page.

2. **Find the company's HR/Recruiting department number**: If available, locate the specific number for their talent acquisition or HR team.

3. **Present the verified number to the user** and instruct them:

> **IMPORTANT: Do NOT trust caller ID.** Scammers can spoof any phone number, including the real company's number, so an incoming call that *looks* like it's from the company proves nothing. If someone calls you claiming to be from [company name], hang up and call the company back yourself using the verified number below. A legitimate recruiter will understand.

4. **If no phone number can be found**: Advise the user to navigate to the company's official website themselves and look for a contact number, or reach out to the company via their official LinkedIn page.

---

## Output Format

ALWAYS structure your response using this exact format:

---

## Recruiter Scam Analysis

### Message Analyzed
> [Quote first 2-3 lines of the message, or "[No message provided — analysis based on user description]"]

---

### Step 1: Email Content Analysis
**Risk: [Low / Medium / High]**

[2-4 bullet points of specific observations — cite exact phrases where possible]

---

### Step 2: Sender Domain & Email Format
**Risk: [Low / Medium / High / Unknown]**

- **Sender email**: [full email address]
- **Company's official domain**: [domain]
- **Known email format**: [format if found, e.g. first.last@company.com]
- **Match**: [Yes/No — does the sender's email match?]
- **Directory check**: [Found/Not found — does the recruiter appear in employee directories with a corporate email?]

---

### Step 3: Recruiter & Company Verification
**Risk: [Low / Medium / High / Unknown]**

- **LinkedIn profile**: [Summary of what was found — tenure, connections, activity]
- **Job posting exists**: [Yes/No — was the role found on the company's careers page or LinkedIn Jobs?]
- **Scam reports**: [Any reports found?]

---

### Step 4: Verified Contact Number
**Official number found: [number] (source: [where you found it])**
— or —
**No verified number found — see instructions below.**

> **Do NOT trust caller ID.** Phone numbers can be spoofed. If you receive a call from this "recruiter," hang up and call the company back yourself using the verified number above. If you can't find a number, contact the company through their official website or LinkedIn page. A real recruiter will not be offended.

---

### Overall Verdict

**[LIKELY LEGITIMATE / SUSPICIOUS — PROCEED WITH CAUTION / HIGH PROBABILITY SCAM]**

[2-3 sentence summary of why you reached this verdict]

---

### Recommended Actions

- [Specific, actionable step 1]
- [Specific, actionable step 2]
- [Specific, actionable step 3 if needed]
- If suspicious: Call the company directly at the verified number above to confirm the recruiter and opportunity are real
- Never send money, gift cards, crypto, or personal financial information to a recruiter

*Report scams to LinkedIn at linkedin.com/help/linkedin/answer/a1442749 and to the FTC at reportfraud.ftc.gov*

---

## Handling Missing Information

- If the user hasn't identified the suspicious email yet, ask them to point it out in their inbox or describe it.
- If no email address is visible, expand the email headers in the browser to reveal the full sender address.
- If you can't verify the recruiter (e.g., the name is too common), note the limitation and advise the user to manually search LinkedIn.
- If no verified phone number can be found, instruct the user to find it themselves from the company's official website.
- Never fabricate search results, phone numbers, or email formats. If a search doesn't return clear confirmation, say so honestly.

## Tone

Be direct but not alarmist. False positives (calling a legit recruiter a scammer) cause real harm. If evidence is mixed, say so clearly and explain what the user should verify themselves before deciding.
