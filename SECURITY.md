# Security Policy

## Goal

This document describes how security vulnerabilities should be reported for the **TARL-Net** repository and outlines the project's disclosure and response process.

> **Research Notice**
>
> TARL-Net is an academic research project developed for experimentation, benchmarking, and scientific evaluation. The code has **not** been designed or certified for production deployment in mission-critical environments. Users are responsible for conducting appropriate security reviews before deploying any component in operational systems.

---

# Scope

| In Scope                                     | Out of Scope                               |
| -------------------------------------------- | ------------------------------------------ |
| Core source code and notebook implementation | Third-party datasets (e.g., UNSW-NB15)     |
| Model architectures and training pipeline    | External cloud infrastructure              |
| Repository configuration files               | User-specific deployment environments      |
| Project dependencies                         | Operating systems and third-party software |

---

# Supported Versions

| Version        | Supported  | Notes                        |
| -------------- | ---------- | ---------------------------- |
| `main`         | ✅ Yes      | Active development branch    |
| Latest release | ✅ Yes      | Best-effort support          |
| Older commits  | ⚠️ Limited | High or Critical issues only |

---

# Reporting a Vulnerability

If you discover a potential security vulnerability, **please do not create a public GitHub Issue.**

Instead, report it through one of the following channels:

### Preferred

Use **GitHub Private Security Advisories** for confidential vulnerability disclosure.

### Alternative

Email:

**[rezahamzeh.sh@gmail.com](mailto:rezahamzeh.sh@gmail.com)**

Subject:

```
[TARL-Net] Security Vulnerability Report
```

---

# Please Include

To help us investigate efficiently, include:

* A description of the vulnerability
* Affected component or file
* Repository version or commit hash
* Operating system and Python version
* Steps to reproduce the issue
* Proof-of-Concept (if available)
* Potential impact
* Suggested mitigation (optional)

---

# Disclosure Process

Our coordinated disclosure process follows these steps:

1. **Acknowledgment**

   Reports are acknowledged within **3 business days** whenever possible.

2. **Assessment**

   Vulnerabilities are evaluated according to the **CVSS v3.1** framework.

3. **Remediation**

   High and Critical vulnerabilities are prioritized for remediation as quickly as reasonably possible.

4. **Disclosure**

   We request that vulnerability details remain confidential until an official fix, mitigation, or advisory has been published.

---

# Security Recommendations

Because TARL-Net is a research implementation, users are encouraged to follow these best practices:

* Execute the notebook only inside isolated environments such as virtual machines or Docker containers.

* Use a dedicated Python virtual environment (`venv` or `conda`).

* Keep dependencies updated.

* Regularly audit installed packages using tools such as:

  * `pip-audit`
  * `safety`

* Never commit API keys, access tokens, credentials, or confidential datasets.

* Store secrets using environment variables or secure credential managers.

* Carefully review custom modifications before deployment.

---

# Production Deployment

The repository is intended primarily for research and educational purposes.

If TARL-Net is deployed in production environments, users should additionally implement:

* Authentication and authorization
* Secure network segmentation
* Access control
* Logging and monitoring
* Dependency vulnerability scanning
* Secure configuration management
* Continuous security testing

These operational controls are outside the scope of this repository.

---

# Security Contact

**Maintainer**

Reza Hamzeh Shalamzari

📧 **Email**

[rezahamzeh.sh@gmail.com](mailto:rezahamzeh.sh@gmail.com)

---

Thank you for helping improve the security and reliability of TARL-Net.
