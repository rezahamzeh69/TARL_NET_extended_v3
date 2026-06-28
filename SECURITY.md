# Security Policy

## Goal
This document describes how to report vulnerabilities and how we respond for the **TARL-Net** repository. 

> [!WARNING]
> This project is academic research code. Please thoroughly evaluate security risks before deploying it in production Industrial Control Systems (ICS) or Operational Technology (OT) environments.

---

## Scope

| In-Scope | Out-of-Scope |
| :--- | :--- |
| • Core source code and model architectures<br>• Project dependencies (`requirements.txt`)<br>• Example configurations and pipeline run scripts | • Third-party datasets (e.g., Kaggle, UNSW-NB15, WADI)<br>• External hosting services or infrastructure |

---

## Supported Versions
We officially provide security review and support for the following versions:

| Version / Branch | Supported | Notes |
| :--- | :---: | :--- |
| `main` branch |  Yes | Active development and latest tagged releases (Best Effort). |
| Older Versions | ⚠️ Case-by-Case | Reviewed only for **High** or **Critical** security issues. |

---

## Reporting a Vulnerability
If you discover a security vulnerability, please do not open a public GitHub Issue. Instead, use one of the following secure channels:

1. **Preferred:** Open a private **GitHub Security Advisory** directly through this repository.
2. **Alternative:** Email the security contact at **rezahamzeh.sh@gmail.com** with the subject line: `[ics-ot-wadi-hybrid-ids] Vulnerability Report`.

### What to include in your report:
To help us triage and fix the issue quickly, please include:
* **Component:** The affected file, module, or dependency with a brief description.
* **Environment:** Version/commit hash, Operating System, and Python environment details.
* **Proof of Concept (PoC):** Step-by-step instructions or a minimal script to reproduce the issue.
* **Impact:** Potential attack vectors and the severity of the impact.
* **Mitigation:** Any temporary workarounds or fix ideas (if available).

---

## Disclosure Process
* **Acknowledgment:** We will acknowledge receipt of your report within **3 business days**.
* **Assessment:** We evaluate the severity using the CVSS v3.1 framework.
* **Remediation:** We aim to patch **High** or **Critical** vulnerabilities within **14 business days** whenever feasible.
* **Coordinated Disclosure:** We kindly ask to keep all vulnerability details confidential until an official patch or workaround is released. Public disclosure will be coordinated mutually with the reporter.

---

## Risk Mitigations
* **Research-Oriented:** This is a research repository; it does not implement host or network hardening mechanisms by default.
* **Sandboxing:** Always execute this notebook/code within isolated, sandboxed environments (e.g., restricted Docker containers or virtual machines) and avoid processing sensitive corporate data.
* **Secrets Management:** Never commit API keys, Kaggle tokens, or system credentials to the repository. Utilize environment variables or local configuration managers.

---

## Security Best Practices
* Use a dedicated virtual environment (`venv` or `conda env`) for running the pipeline.
* Keep dependencies up to date and regularly audit them using automated tools like `pip-audit` or `safety`.
* Enable automated GitHub CI/CD workflows to run unit tests and dependency scans on new Pull Requests.

---

## Security Contact
* **Contact:** Reza Hamzeh Shalamzari
* **Email:** rezahamzeh.sh@gmail.com
