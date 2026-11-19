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
| My-Locked-PDF2.pdf    | (via persistence)| Cracked         |
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
