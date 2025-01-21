---
title: "SmartGit's Strategy on Git Versioning and Security"
date: "2025-01-21"
categories:
  - "smartgit"
tags:
  - "smartgit"
---

## Technical Overview of Git Versioning in SmartGit

SmartGit provides a bundled Git version to streamline initial setup and usage. However, we recognize that some users have specific requirements for security and compliance that necessitate control over the Git version they use. This document outlines our approach to Git versioning and our plans to further enhance flexibility for users.

## Bundled Git: Balancing Convenience and Stability

SmartGit includes a bundled Git version to:

- **Facilitate Setup**: Users can begin working immediately without needing to install Git separately.
- **Ensure Updates with Major Releases**: Major SmartGit releases include a recent and stable Git version, incorporating available security patches and functional improvements.
- **Stability for Bug-Fix Releases**: For bug-fix releases, the bundled major Git version (like 2.47 or 2.48) remains unchanged. Updating Git to a new major version can introduce regressions, such as compatibility issues with existing workflows or unexpected behavior in integrated tools.

## CVEs and the Latest Git Version

Common Vulnerabilities and Exposures (CVEs) in Git are often addressed first in the latest major Git version (e.g., 2.48). Critical fixes for important CVEs might be selectively backported to older versions as part of a bugfix release (e.g., 2.47.1). It's important to note that official binaries for all older bugfix releases may not be available.

Many CVEs impact only specific configurations and are unlikely to affect the majority of users. Consequently, for most use cases, keeping the latest Git version that resolves every CVE is not always necessary.

Therefore, while regularly upgrading to the latest major Git version may resolve recent vulnerabilities for some users, it can also introduce regressions affecting all users. This is why we prioritize delivering a stable and reliable experience over constant updates.

## User-Managed Git Versions

We recommend that users who require the utmost security or control over their Git installation should use their own managed version of Git. This ensures they can independently upgrade to address specific vulnerabilities while maintaining their desired level of security.

### Technical Details

- **Compatibility Requirements**: SmartGit allows users to bring their own Git installation, provided it meets easy-to-achieve minimum version requirements. This guarantees compatibility with SmartGit's core functionality.
- **Enhanced Security Control**: Users can stay ahead of vulnerabilities by upgrading to Git versions tailored to their needs, rather than relying on the bundled version.
- **Mitigating Risks**: This approach mitigates the risks of regressions that could arise from frequent updates to the bundled Git version, ensuring stability for all users.

### Planned Introduction of Git-Free Bundles

To address concerns raised by automated security tools, we plan to offer SmartGit bundles without a bundled Git version. These Git-free bundles are designed for:

- **Minimizing False Positives**: Security tools will no longer flag unused bundled Git versions as potential issues.
- **Simplified Compliance**: Organizations can maintain compliance without requiring modifications to their existing processes.

Users can then configure SmartGit to work with their preferred Git installation, further decoupling Git management from SmartGit.

Linux users can already make use of the Debian package bundles available for SmartGit. These bundles are designed to integrate seamlessly with the system's package management tools, ensuring that an external Git dependency is leveraged.

## Conclusion

SmartGit's Git versioning strategy prioritizes stability, security, and user control. The bundled Git provides a reliable default for most users, while the option to use an external Git version supports those with advanced requirements. Planned Git-free bundles will provide additional flexibility, ensuring SmartGit integrates seamlessly into diverse environments. For further details or to share feedback, please contact our support team or use our feedback platform.
