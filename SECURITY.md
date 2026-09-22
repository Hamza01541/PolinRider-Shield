# Security Policy

PolinRider Shield is a defensive scanner for the **PolinRider npm supply chain attack** (DPRK Lazarus Group / BlueNoroff). This document covers how to report issues with the tool itself, and how to report new indicators of compromise.

---

## Reporting a vulnerability in this tool

If you find a flaw in the scanner or lockdown scripts — a false negative that lets an infection through, a command injection in the scan logic, or a lockdown step that weakens a system — please report it privately first.

Use [GitHub Security Advisories](https://github.com/Hamza01541/polinrider-shield/security/advisories/new) so the issue is not public before a fix exists.

Please include:
- Which script and which scan step (for example `A6` in the Windows scanner)
- Your OS and shell version
- What the scanner reported, and what it should have reported
- A minimal reproduction if you have one

---

## Reporting a new indicator of compromise

New IoCs are the most useful contribution to this project. **Open a public issue** using the *Report a new IoC* template — these are not vulnerabilities in the tool and benefit from being visible and searchable.

Useful IoCs include:
- New malicious filenames or paths
- New malware signatures in config files
- New C2 IP addresses or domains
- New persistence or payload-execution artifacts

Please include a source — an advisory, a writeup, or the infected repository — so the signature can be verified before it is added. Unverified signatures cause false positives, which erode trust in the scanner.

---

## Scope

**In scope:** the Windows scanner, the macOS scanner, and the GitHub Actions workflow in this repository.

**Out of scope:** the PolinRider malware itself. This repository tracks the campaign but is not a place to report infections of third-party repositories — report those to the affected repository owner and to GitHub.

---

## Safe use

These scripts scan filesystems and, on Windows, modify firewall and editor settings. Review any script before running it with elevated privileges. The Windows scanner requires Administrator rights for full lockdown; the macOS scanner is read-only and changes nothing.
