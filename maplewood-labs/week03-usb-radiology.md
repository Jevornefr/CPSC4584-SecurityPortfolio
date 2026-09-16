# Week 3: Unauthorized USB Drive in Radiology
**Course:** CPSC 4584 | Special Topics in Information Security
**Date:** September 14, 2026
**Analyst:** Jevorne Francisrichards
**Incident ID:** INC-2026-0914-001

---

## Incident Summary

An unauthorized and unmarked USB drive was discovered connected to workstation MHS-RAD-WS-03 in the Radiology Imaging Suite. The workstation is used by radiology staff to access the PACS imaging system and Maplewood EHR.

---

## Chain of Custody

Chain of custody is important because it provides a clear record of who handled the USB and what actions were taken with it. The device was removed without files being opened, logged and tagged by IT, and transferred to SOC custody while the original device remained preserved for approved forensic examination.

---

## Key Encoding Finding

**String Found:** Y3VybCAtcyAtbyAvZGV2L251bGw=
**Encoding Type:** Base64
**Decoded Content:** `curl -s -o /dev/null`
**Significance:** The decoded text is a curl command that uses silent mode and directs output to `/dev/null`. This type of command should be documented and investigated further, but the fragment alone does not prove that the command was executed, identify a destination URL, or establish that malicious activity occurred.

---

## Terminal Commands Used

| Command | Purpose |
|---------|---------|
| echo "..." \| base64 | I learned that Base64 changes plain text into another representation that can be safely converted back to the original data. Base64 is an encoding method and not encryption. |
| echo "..." \| base64 -d | I used Base64 decoding to convert encoded data back into readable text. The practice string decoded to `curl -s -o /dev/null`, allowing me to identify the command stored in the encoded string. |
| xxd .bashrc \| head -6 | I used `xxd` to view the beginning of the `.bashrc` file as hexadecimal values alongside its readable ASCII representation. This demonstrated how file contents can be inspected without executing the file. |
| strings .bashrc \| grep -i "..." | I used `strings` to extract readable text and `grep` to narrow the output to specific patterns such as `path`, `export`, and `alias`. This demonstrated how an analyst can quickly filter a large amount of file content for information relevant to an investigation. |

---

## Escalation Recommendation

I would escalate this incident to Tier 2 because an unauthorized USB was discovered connected to MHS-RAD-WS-03, a Radiology workstation with access to the PACS system and Maplewood EHR. Although no outbound alerts were flagged, overnight monitoring coverage was limited, so the absence of alerts does not prove that no activity occurred. Important questions still remain, including who connected the USB, why it was connected, how long it was present, what was stored on it, and whether any files or commands were executed. The original USB should remain preserved for approved forensic examination while Tier 2 continues the investigation.

---
*CPSC 4584 | Governors State University | Fall 2026*
