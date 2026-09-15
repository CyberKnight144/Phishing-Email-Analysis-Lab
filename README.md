# Phishing Email Analysis Lab

## Project Overview

This project demonstrates a Tier 1 SOC Analyst workflow for investigating a suspicious phishing email. The investigation included analyzing email headers, identifying indicators of compromise (IOCs), examining authentication results, researching suspicious infrastructure using threat intelligence tools, and documenting the findings in an incident report.

## Objectives

- Analyze a suspicious email for phishing indicators
- Examine sender and email header information
- Review SPF, DKIM, and DMARC authentication results
- Identify suspicious domains, IP addresses, and URLs
- Investigate IOCs using threat intelligence tools such as VirusTotal
- Determine the severity and final verdict of the email
- Document the investigation using a professional SOC incident report

- ## Email Details

The suspicious email was designed to impersonate Microsoft support and create a sense of urgency for the recipient.

### Observed Indicators

- **Spoofed Domain:** `micros0ft-support.example`
- **Suspicious Sender Infrastructure:** `mail.micros0ft-support.example`
- **Sender IP Address:** `192.0.2.45`
- **SPF:** Reviewed during header analysis
- **DKIM:** `none`
- **DMARC:** `fail`
- **Return-Path / SMTP Sender:** `micros0ft-support.example`

### Initial Triage

Several indicators suggested that the message was potentially malicious:

- The domain used `micros0ft` instead of `microsoft`, replacing the letter **o** with the number **0**.
- The email used urgency to pressure the recipient into taking action.
- The sender domain appeared unusual and did not match Microsoft's legitimate domain.
- DKIM authentication was absent.
- DMARC authentication failed.
- The message contained suspicious infrastructure requiring further threat-intelligence analysis.

- ## Email Header Analysis

The email headers were examined to determine whether the message originated from legitimate infrastructure and whether standard email authentication mechanisms validated the sender.

### Key Findings

- **Received From:** `mail.micros0ft-support.example`
- **Source IP:** `192.0.2.45`
- **SMTP Mail From:** `micros0ft-support.example`
- **DKIM Result:** `none`
- **DMARC Result:** `fail`
- The sender domain used the number `0` in `micros0ft` to visually imitate the legitimate Microsoft name.
- The DMARC failure indicated that the message did not successfully authenticate against the domain's DMARC policy.
- The absence of a DKIM signature provided another reason to treat the message as suspicious.

### Analyst Assessment

The combination of a lookalike domain, failed DMARC authentication, missing DKIM authentication, and social-engineering language strongly indicated an impersonation-based phishing attempt.

## IOC and Threat Intelligence Analysis

Indicators of Compromise (IOCs) were extracted from the suspicious email and investigated using threat intelligence resources.

### Indicators Investigated

| IOC Type | Indicator | Analysis |
|---|---|---|
| Domain | `micros0ft-support.example` | Lookalike domain designed to imitate Microsoft |
| Hostname | `mail.micros0ft-support.example` | Suspicious mail infrastructure |
| IP Address | `192.0.2.45` | Investigated during threat intelligence analysis |
| Email Authentication | `DKIM=none` | No DKIM authentication present |
| Email Authentication | `DMARC=fail` | Sender failed DMARC authentication |

### Threat Intelligence

VirusTotal was used as part of the investigation to research the extracted indicators and determine whether additional threat intelligence information was available.

The investigation demonstrated an important SOC analyst principle: threat intelligence results should be evaluated together with email headers, authentication results, domain characteristics, and social-engineering indicators rather than being used as the sole basis for determining whether an email is malicious.

### IOC Assessment

The strongest indicators were the deceptive lookalike domain, failed DMARC authentication, missing DKIM authentication, and the social-engineering techniques used in the message.

## Final Verdict

**Classification:** Phishing / Credential Theft Attempt

**Severity:** High

The email was determined to be a phishing attempt based on multiple indicators observed during the investigation. The sender used a lookalike domain designed to impersonate Microsoft, email authentication checks showed suspicious results, and the message used urgency to influence the recipient into taking action.

The combination of these indicators provided sufficient evidence to classify the message as malicious.

## Recommended Response Actions

As a Tier 1 SOC Analyst, the recommended response would include:

- Escalate the phishing email according to the organization's incident response procedures.
- Block the identified malicious or suspicious sender/domain where appropriate.
- Search the environment for additional emails containing the same indicators.
- Determine whether other users received or interacted with the message.
- Investigate any affected endpoint if a user clicked the suspicious link.
- Reset credentials if there is evidence that credentials were entered into a phishing page.
- Document the investigation, IOCs, findings, and actions taken.
- Preserve relevant evidence for further investigation or escalation.

- ## SOC Analyst Skills Demonstrated

This project demonstrates practical Tier 1 SOC Analyst skills, including:

- Phishing email triage and investigation
- Email header analysis
- SPF, DKIM, and DMARC analysis
- Identification and extraction of Indicators of Compromise (IOCs)
- Lookalike domain and impersonation detection
- URL, domain, and IP address analysis
- Threat intelligence research using VirusTotal
- Social engineering identification
- Incident classification and severity assessment
- Documentation of investigation findings
- Development of remediation and escalation recommendations
- SOC incident reporting

## Tools Used

- **VirusTotal** — Threat intelligence and IOC investigation
- **Email Headers** — Sender and authentication analysis
- **Windows 11 VM** — Isolated investigation environment
- **Notepad** — Investigation notes, IOC documentation, and incident reporting
- **GitHub** — Project documentation and portfolio presentation
## Investigation Evidence

The following screenshots document key stages of the phishing email investigation.

### 1. Suspicious Email Analysis
Evidence of the phishing email, including the impersonation attempt, suspicious sender information, and social-engineering language.

### 2. Email Header Analysis
Analysis of the email headers revealed the lookalike `micros0ft-support.example` domain, missing DKIM authentication, and failed DMARC authentication.

### 3. IOC Analysis
Indicators including the suspicious domain, hostname, IP address, and URL were extracted and documented for further investigation.

### 4. Threat Intelligence Analysis
VirusTotal was used to investigate the identified indicators and gather additional threat-intelligence information.

### 5. Incident Report
A SOC incident report was created documenting the initial triage, email details, header analysis, threat-intelligence findings, final verdict, and recommended response actions.
- 
