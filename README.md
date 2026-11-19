# NETWORKWALKS-PASCAL-B084-WK3-PM1-AND-PM2-CYBERSECURITY-PASSWORD-CRACKING

**Intern:** Pascal Chimdindu Anorue (dipapus-gif)  
**Academy:** Networkwalks Academy  
**Module:** Week 3 – Password Cracking (PM1 & PM2)  
**Focus:** PDF Password Hash Extraction + Dictionary Attacks + John the Ripper

---

## Overview

This repository documents the practical hands-on assignment on **password cracking** performed as part of the Networkwalks Academy Cybersecurity internship.

The tasks involved:

1. Extracting crackable password hashes from encrypted PDF files using the Networkwalks **Hash Calculator**.
2. Performing **dictionary attacks** against those hashes using the Networkwalks **Password Cracker** (browser-based lab).
3. Using **John the Ripper** (via the Johnny GUI) for offline cracking of the same PDF hashes.
4. Successfully unlocking the protected PDFs and capturing the flags.

---

## Tools Used

| Tool | Purpose |
|------|---------|
| [Networkwalks Hash Calculator](https://networkwalks.com/hash-calculator/) | Extract `$pdf$` hashes (pdf2john / hashcat compatible) from password-protected PDFs |
| [Networkwalks Password Cracker](https://networkwalks.com/password-cracker/) | Online dictionary attack lab (built-in 100-word list) |
| **John the Ripper** + **Johnny** (GUI) | Offline password cracking of PDF hashes |
| Adobe Acrobat / PDF Reader | Open and verify unlocked PDFs |

---

## Workflow Summary

### 1. Hash Extraction (PM1)

- Uploaded encrypted PDFs (`My-Locked-PDF1.pdf`, `My-Locked-PDF2.pdf`, `My-Locked-PDF3.pdf`) to the Networkwalks Hash Calculator.
- The tool parsed the PDFs **locally** (nothing uploaded to a server) and extracted `$pdf$` format hashes.
- Example hash format observed:

```
$pdf$4*4*128*-1060*1*16*55d1a5c14175da449753199e44971d32*32*777fd021a7f3c5ae598c0c6495c7f76e00000000000000000000000000000000*32*ceecdac74b19b5a62688d3b3524e1374c955cbb9cc3c45316494d9446ef81af1
```

- Revision: R4 | Version: V4 | Key Length: 128 bit

### 2. Dictionary Attack (Browser Lab)

- Pasted the extracted `$pdf$` hash into the Networkwalks Password Cracker.
- Used the built-in 100-password wordlist.
- Successful cracks:

| PDF File              | Password Cracked | Status          |
|-----------------------|------------------|-----------------|
| My-Locked-PDF1.pdf    | `password1`      | Cracked         |
| My-Locked-PDF2.pdf    | (persistence)    | Cracked         |
| My-Locked-PDF3.pdf    | `1qaz2wsx`       | Cracked         |

### 3. John the Ripper (Johnny GUI)

- Loaded the same `$pdf$` hash into Johnny (John the Ripper GUI).
- Confirmed successful crack of `password1` for the first PDF hash.
- Demonstrated offline cracking capability using the classic John the Ripper approach.

---

## Captured Flags

After unlocking the PDFs with the cracked passwords:

**Flag 1 (PDF1):**
```
nw{networkwalks_flag1_jtr_270521_1}
```

**Flag 2 (PDF2):**
```
nw{networkwalks_persistence_jtr_270521}
```

**Flag 3 (PDF3):**
```
nw{networkwalks_flag_260821_1}
```

---

## Proof of Work – Screenshots

All original screenshots from the assignment session are documented below (timestamps match the captured evidence):

### Hash Calculator – PDF Upload & Hash Extraction
- `Screenshot 2026-11-18 205750.png` / `205811.png` / `205838.png`  
  → Hash Calculator interface showing `My-Locked-PDF1.pdf` (65.2 KB) loaded, encrypted status confirmed, and full `$pdf$` hash extracted (pdf2john / hashcat compatible). Revision R4, Version V4, 128-bit key.

### Password Cracker Lab – Dictionary Attack Setup
- `Screenshot 2026-11-18 210605.png` / `211003.png` / `211055.png`  
  → Networkwalks Password Cracker (Dictionary Attack Lab). Hash pasted, built-in 100-password wordlist active, ready to start cracking.

### Successful Crack – password1
- `Screenshot 2026-11-18 211204.png`  
  → Dictionary attack progress (91/100 tried). **MATCH: password1** found. “PASSWORD CRACKED SUCCESSFULLY” screen displayed.

### Unlocking PDF1 & Capturing Flag 1
- `Screenshot 2026-11-18 211346.png`  
  → Password prompt for `My-Locked-PDF1.pdf`.
- `Screenshot 2026-11-18 211425.png` / `211450.png`  
  → PDF unlocked. Congratulations screen + **Flag1: `nw{networkwalks_flag1_jtr_270521_1}`** highlighted.

### PDF2 Unlock & Flag 2
- `Screenshot 2026-11-18 211923.png` / `211942.png`  
  → `My-Locked-PDF2.pdf` opened. “Congratulations! You have captured another flag.”  
  **Flag: `nw{networkwalks_persistence_jtr_270521}`**

### PDF3 Crack – 1qaz2wsx & Flag 3
- `Screenshot 2026-11-18 213555.png`  
  → Dictionary attack on third hash. **MATCH: 1qaz2wsx**.
- `Screenshot 2026-11-18 213624.png`  
  → PDF3 unlocked. **Flag: `nw{networkwalks_flag_260821_1}`**

### John the Ripper (Johnny GUI) – Offline Confirmation
- `Screenshot 2026-11-19 105225.png`  
  → Johnny (John the Ripper GUI) showing the PDF hash successfully cracked with password `password1`. Status: 100% (1/1 cracked).
- `Screenshot 2026-11-19 105405.png`  
  → Confirmation of unlocked PDF1 content and Flag1 after using the password obtained via John the Ripper.

> **Note on binary screenshots:** The original PNG files (16 screenshots, ~8 MB total) were captured during the session. Due to platform constraints on binary file uploads via this interface, the full image files should be uploaded manually from the local machine into a `screenshots/` folder for complete visual proof. The detailed descriptions above serve as structured evidence of every step completed.

---

## Key Learning Outcomes

- Understanding how PDF encryption stores password verification data that can be extracted into a crackable format (`$pdf$`).
- Practical experience with dictionary attacks (both online lab and offline with John the Ripper).
- Recognizing the importance of strong, unique passwords and the risks of weak/common passwords.
- Using industry-standard tools (John the Ripper) alongside educational platforms.

---

## Notes

- All PDF parsing in the Hash Calculator was performed **client-side** (local browser processing).
- The built-in wordlist of 100 common passwords was sufficient for these educational challenges.
- Real-world cracking would typically use much larger wordlists (rockyou.txt, etc.) and rulesets.

---

**Completed as part of Networkwalks Academy Internship – Week 3 (PM1 & PM2)**  
*Cybersecurity & Ethical Hacking with AI*
