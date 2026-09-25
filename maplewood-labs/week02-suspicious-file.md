# Week 2: Suspicious File on a Nurse's Workstation

**Course:** CPSC 4584 | Special Topics in Information Security  
**Date:** September 7, 2026  
**Analyst:** Jevorne Francisrichards  
**Incident ID:** INC-2026-0907-001

---

## Incident Summary

A suspicious file named `patient_notes.txt` was identified in the `/home/nurse01/` directory on a clinical workstation. The file required additional investigation because it was located in a nurse's home directory and had permissions that included the execute bit even though it had a `.txt` extension.

---

## Key Findings

**Permission Finding:** The permission string was `-rwxr--r--`, which showed that the owner had read, write, and execute permissions while the group and other users had read-only access. The execute permission was unusual for a file presented as a text file and required further investigation.

**File Type Finding:** The `file` command helped determine the file's actual type instead of relying only on the `.txt` extension. This is important because a filename or extension does not always accurately represent the contents of a file.

**Timestamp Finding:** The `stat` command displayed metadata such as the file's size, ownership, permissions, and access, modification, and change timestamps. These timestamps helped establish information about the file's history, although timestamps alone do not identify who created or used the file.

**Strings Finding:** The `strings` command was used to look for readable text within the file without executing it. Any readable commands, URLs, paths, usernames, or other recognizable information could provide clues for additional investigation.

---

## Terminal Commands Used

| Command | Purpose |
| --- | --- |
| `pwd && ls -la` | Verified my current directory and displayed the files, including hidden files, along with their permissions, ownership, and other basic information. |
| `file [filename]` | Identified the actual file type instead of assuming the file was a normal text file based on its extension. |
| `stat [filename]` | Displayed detailed metadata such as file size, permissions, ownership, and access, modification, and change timestamps. |
| `strings [filename]` | Extracted readable character sequences that could provide clues about the contents without executing the file. |
| `find . -mtime -1 -type f` | Searched for regular files modified within approximately the last day, which could help identify other recent files that may be relevant to the investigation. |

---

## Escalation Recommendation

I would escalate this finding to Tier 2 because the file was located on a clinical workstation and had an unusual execute permission for a file with a `.txt` extension. The strongest evidence at this stage is the combination of the file's location and its unexpected permissions, but those facts alone do not prove that the file is malicious. Tier 2 should continue investigating the file's actual contents, origin, timestamps, ownership, and whether there is evidence that it was executed or associated with suspicious process or network activity. I would document and preserve the available evidence rather than deleting, modifying, or executing the suspicious file.

---

*CPSC 4584 | Governors State University | Fall 2026*
