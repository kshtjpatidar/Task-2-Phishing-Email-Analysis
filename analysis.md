# Phishing Email Analysis Report

## Summary
This report analyzes a sample suspicious email and lists phishing indicators found, the reasoning behind each finding, and recommended actions.

---

## Sample Email (short)
See `sample_email.eml` for the full raw text.

**Subject:** Action Required: Verify Your Account Immediately  
**From (display):** Support <support@bank-example.online>  
**To:** victim@example.com

---

## Observed Phishing Indicators

1. **Sender address vs display name mismatch**
   - Display name claims to be "Support" while the email address `support@bank-example.online` uses an unusual domain (`bank-example.online`) rather than the bank's official domain (e.g. `bank.example.com`). This is a common spoofing technique.

2. **Suspicious headers**
   - Received headers show origin from an unexpected IP and an `HELO` mismatch. Headers indicate the sending server is not an authorized mail server for the claimed domain. See `headers.txt` for the sample.

3. **Mismatched URLs**
   - The email contains links with misleading anchor text (e.g., `https://bank.example.com/verify`) that point to a different domain (`http://example-verify[dot]online/verify`). Always hover or inspect link targets before clicking.

4. **Urgent and threatening language**
   - Phrases such as "Action Required", "verify within 24 hours" or "your account will be suspended" try to provoke an emotional (fear) response and rush the target into making mistakes.

5. **Attachments or download prompts**
   - The sample email asks the user to download a "verification form" (attachment). Attachments from unknown senders may contain malware—do not open.

6. **Spelling, grammar, and formatting errors**
   - The email body contains minor grammar and punctuation issues which are common in phishing emails.

7. **Generic greeting**
   - Uses "Dear Customer" instead of the user's real name which may indicate mass phishing.

8. **Tracking/redirect services**
   - Use of URL shorteners or redirection domains to hide the final destination.

9. **Social engineering tactics**
   - The attacker references a plausible scenario (account verification) to lower suspicion and prompt action.

---

## Recommended Actions (for recipients)
- Do not click links or open attachments.
- Verify the sender by checking official channels (bank website or phone number).
- Inspect email headers using online header analyzer tools.
- Report the email to your IT/security team or the organization being spoofed.
- Mark the email as phishing/spam in your email client.
- If credentials were entered, change passwords and enable MFA; monitor for suspicious activity.

---

## Tools & Commands used in analysis
- Online header analyzer (example): MXToolbox / Google Message header tool
- Browser: hover link and copy link address
- Email client: view raw source

---

## Appendix
- `sample_email.eml` — raw text used for analysis.
- `headers.txt` — sample headers that illustrate Received/From/Return-Path anomalies.
- `screenshot_analysis.png` — visual annotated screenshot.

