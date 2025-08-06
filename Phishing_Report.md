# phishing-email-analysis

## Introduction

This report presents an analysis of a sample phishing email to identify key indicators of a phishing attempt. The objective of this task is to develop awareness of phishing techniques, improve detection skills, and document findings in a structured, evidence-based format. This forms part of a cybersecurity internship project focused on real-world threat recognition.

---

## Sample Email

Below is the raw content of the phishing email analyzed:

From: support@amaz0n-customers.com
Subject: Urgent: Your Amazon Account is Suspended

Dear Customer,

We noticed suspicious activity in your Amazon account. Please confirm your identity to avoid permanent suspension.

Click the link below to verify your account:
https://amaz0n.verify-now-security.com

Failure to act within 24 hours will lead to account termination.

Thank you,
Amazon Security Team.


---

## 1. Spoofed Email Address

- Sender: `support@amaz0n-customers.com`
- Analysis:
  - The domain name closely imitates a legitimate service (Amazon), but includes a zero (`0`) in place of the letter `o` in `amazon`.
  - This form of domain spoofing is known as **typosquatting**, a common technique used in phishing to deceive users by exploiting visual similarities.
  - The domain `amaz0n-customers.com` is not associated with the real Amazon service and was confirmed to be unrelated upon WHOIS inspection.

---

## 2. Email Header Analysis

Tool Used: [MXToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)

Key Observations:

- SPF (Sender Policy Framework): **Fail** – Indicates that the domain is not authorized to send email on behalf of the real Amazon servers.
- DKIM/DMARC: **Not configured or fail** – Lack of proper authentication records increases likelihood of spoofing.
- Return-Path and Received-From fields do not match the displayed sender, further indicating possible tampering or impersonation.

A screenshot of the full header analysis has been saved in the `screenshots` directory for reference.

---

## 3. Malicious Link Analysis

Displayed Link: `https://amaz0n.verify-now-security.com`  
Actual Destination: Same, confirmed by hovering over the link in the email body.

Steps Taken:

- The domain was submitted to [VirusTotal](https://www.virustotal.com) and [URLScan.io](https://urlscan.io) for analysis.
- Results indicated:
  - The domain is **recently registered** (new domains are often used in phishing).
  - The site lacks HTTPS certificate authority verification and has no known business registration.
  - Flagged by multiple threat intelligence providers as suspicious.

A screenshot of the scan result is provided in the `screenshots` directory.

---

## 4. Urgency and Psychological Triggers

The email employs urgency-based language to manipulate user behavior:

- Subject line uses words like **“Urgent”** and **“Suspended”** to invoke fear.
- The body contains threats of **account termination within 24 hours**, creating pressure for the user to act immediately without scrutiny.
- This is a classic psychological manipulation technique used in social engineering attacks.

---

## 5. Spelling and Grammar Issues

- The domain name contains a substitution error: `amaz0n` instead of `amazon`.
- The email lacks professional formatting and branding commonly used in legitimate Amazon communication.
- The email is generic and does not address the recipient by name, which is typical of mass phishing attempts.

---

## 6. Summary of Phishing Indicators

| Indicator                     | Detected | Details                                                         |
|------------------------------|----------|-----------------------------------------------------------------|
| Spoofed/Lookalike Email      | Yes      | Domain closely resembles 'amazon.com' but uses 'amaz0n'         |
| Urgent/Threatening Language  | Yes      | Claims account will be terminated within 24 hours               |
| Suspicious URL               | Yes      | Fake domain registered recently, flagged in multiple scanners   |
| Header Authentication Issues| Yes      | SPF failed, DKIM/DMARC missing or invalid                       |
| Generic Language & Typos     | Yes      | No personalization; vague and unprofessional tone               |

---

## Conclusion

This analysis demonstrates several clear indicators of a phishing attempt. The use of a spoofed domain, urgent call to action, suspicious link, and lack of technical email authentication all point to malicious intent. Phishing emails like this are designed to exploit user trust and urgency to steal personal or financial information.

Understanding how to recognize these signs is a fundamental skill in cybersecurity defense, and continuous awareness is essential for reducing human-based vulnerabilities.

---

## Supporting Files

- `sample-email.txt`: Plain text version of the phishing email.
- `screenshots/header_analysis.png`: Email header analysis result from MXToolbox.
- `screenshots/link_scan_result.png`: URL scan result showing domain risk level.
- `screenshots/email_view.png`: View of the full email layout.

---

## Author

Noor Hafsa  
Cybersecurity Enthusiast. 
GitHub: [https://github.com/NoorHafsa17](https://github.com/NoorHafsa17)

This analysis is created as part of a cybersecurity learning task to demonstrate professional phishing email investigation workflow.


