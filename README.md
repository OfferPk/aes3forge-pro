\# AES3Forge Pro (v1.0.0)  
\> \*\*AES3 / AES-EBU / S/PDIF Digital Audio Protocol Engineering Suite\*\*

\---

\#\# Overview  
\*\*AES3Forge Pro\*\* is an open-standard engineering studio, 32-bit subframe assembler, and 192-frame channel status block validator designed for professional broadcast engineers, recording studios, and digital audio equipment designers conforming to AES3 and IEC 60958\.

\#\#\# Normative Standards Covered:  
\- \*\*AES3-2009 (r2019):\*\* Serial transmission format for two-channel linearly represented digital audio data.  
  \- Subframe format: 32 bits per channel subframe (4-bit Preamble, 24-bit Audio LSB first, Validity, User, Channel Status, and Even Parity).  
  \- Preamble codes: B (start of 192-frame block / Channel 1), M (normal Channel 1), W (normal Channel 2).  
  \- Channel Status Block: 192 bits (24 bytes) per channel accumulated across 192 consecutive audio frames.  
\- \*\*IEC 60958-3 (Consumer S/PDIF) & IEC 60958-4 (Professional AES3):\*\* Professional vs Consumer channel status bit 0 discrimination.  
\- \*\*Physical Layers:\*\* 110-ohm balanced twisted pair (XLR), 75-ohm coaxial (BNC / RCA), and optical (TOSLink).

\---

\#\# Key Modules  
1\. \*\*Subframe Telemetry & Bitrate Calculator:\*\*  
   \- Real-time carrier data rates (3.072 Mbps @ 48 kHz, 6.144 Mbps @ 96 kHz) and biphase symbol rates (6.144 Mbaud @ 48 kHz).  
   \- Dynamic preamble code assignment (B, M, W).  
2\. \*\*192-Frame Channel Status Block Generator:\*\*  
   \- Synthesizes 24-byte metadata blocks encoding professional mode, sampling frequencies (44.1k, 48k, 96k), emphasis, and word length.  
3\. \*\*Subframe Assembler & Even Parity Engine:\*\*  
   \- Real-time parity calculation over 28 bits (Audio \+ V \+ U \+ C).  
4\. \*\*10-Point Normative Protocol Auditor:\*\*  
   \- Verifies preamble sync violations, block boundaries, parity calculations, validity flags, and physical impedance matching.  
5\. \*\*Standalone Python 3 CLI Suite:\*\*  
   \- \`build/aes3-cli.py\`: Production CLI with JSON output for automated audio pipeline verification.

\---

\#\# Automated Verification  
Run the unit test suite:  
\`\`\`bash  
python3 test\_aes3.py  
\`\`\`  
\*Result: 10/10 unit tests passed (100% pass rate).\*

\---

\#\# License  
Commercial Proprietary License (v1.0.0). Built for Broadcast & Recording Studio Audio Engineers.  
