# Week 4: Unencrypted Patient Records on a Shared Drive
**Course:** CPSC 4584 | Special Topics in Information Security
**Date:** September 24, 2026
**Analyst:** Jevorne Francisrichards
**Audit ID:** AUD-2026-0921-001

---

## Incident Summary
During a routine IT infrastructure audit, a shared folder containing archived patient records was discovered on a clinical file server. The folder contained 847 Excel and CSV files representing 8,247 unique patient records and included sensitive information such as names, dates of birth, Social Security numbers, diagnosis codes, and insurance information.

---

## HIPAA Compliance Assessment

| Requirement | Status | Finding |
|-------------|--------|---------|
| Encryption at Rest | REQUIRES REVIEW | HIPAA treats encryption as an addressable implementation specification. Maplewood must determine whether encryption is reasonable and appropriate based on its risk assessment and evaluate an equivalent safeguard when appropriate. In this scenario, storing sensitive ePHI in plaintext while allowing broad access creates a substantial confidentiality risk. |
| Access Controls | CONTROL FAILURE | Read and write access was granted to all authenticated users on the clinical network segment instead of being limited to users whose job responsibilities required access to the archived patient information. |
| Audit Controls | CONTROL FAILURE | Historical access logs were not retained for the folder, so Maplewood cannot reconstruct who previously accessed the archived patient information or when the access occurred. |

---

## Cryptographic Controls Evaluated

**Base64 encoding:** Base64 would not provide appropriate protection for the patient information because Base64 is an encoding method rather than encryption. It changes the representation of information but can easily be reversed without a secret key.
**Caesar cipher:** A Caesar cipher would also be inappropriate for protecting sensitive patient information. It is a classical cipher that shifts characters by a fixed amount and does not provide modern cryptographic security.
**Modern encryption at rest:** Maplewood leadership should evaluate recognized encryption methods or other reasonable and appropriate safeguards for stored ePHI based on its risk assessment. Proper encryption at rest could help protect confidentiality by making stored information unreadable to an unauthorized person who obtained the files without the required decryption key.

---

## Hashing Commands Practiced

| Command | Purpose | Output Length |
|---------|---------|---------------|
| echo -n "..." \| sha256sum | Generated a SHA-256 digest for a known string | 64 hexadecimal characters |
| echo -n "..." \| md5sum | Generated an MD5 digest so I could compare its length and security with SHA-256 and understand why MD5 should not be relied on when collision resistance is required. | 32 hexadecimal characters |
| sha256sum .bashrc | Generated a SHA-256 hash of an actual file. An analyst can compare the file's current hash with a known baseline hash to determine whether the file contents have changed. | 64 hexadecimal characters |

---

## Escalation Summary

The confirmed findings are that the PATIENT_DATA_ARCHIVE contained 847 Excel and CSV files with 8,247 unique patient records, including names, dates of birth, Social Security numbers, diagnosis codes, and insurance information. The information was stored without encryption at the file, folder, or disk level, and read and write access was available to all authenticated users on the clinical network segment. Historical access logs were not retained, so it is unknown whether unauthorized users actually accessed, modified, or removed any of the patient information, and prior access cannot be reconstructed from the available logs. I would document these findings and escalate them for further review. Leadership, security, privacy, and legal personnel should determine the appropriate safeguards, evaluate whether a reportable breach occurred, and determine whether notification or other actions are required. As a Tier 1 analyst, I would not conclude that a breach definitely occurred because the available evidence does not establish that.

---
*CPSC 4584 | Governors State University | Fall 2026*
