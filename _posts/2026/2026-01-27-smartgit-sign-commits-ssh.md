---
title: "ssh commit signing for your SmartGit environment"
date: "2026-01-27"
categories:
  - "smartgit"
tags:
  - "smartgit"
  - "GitHub"
  - "GitLab"
---
SSH commit signing is the preferred option on **GitHub** and **GitLab** because it’s simpler, more secure by default, and better aligned with modern developer workflows. Unlike GPG, SSH keys don’t require complex keyrings, manual trust management, or fragile local configuration, making them easier to set up and maintain across machines. SSH keys are already widely used for repository access, benefit from strong hardware-backed support (like security keys), and integrate cleanly with both platforms’ verification systems—reducing friction while still providing clear, cryptographically verifiable proof of authorship.

SmartGit supports signed commits by visually indicating their presence in the commit graph: when a cryptographic signature exists, a subtle grey pen icon appears to the left of the commit, signaling that the commit is signed.

**Disclaimer:** Operations such as rebasing, amending commits, or other force-push actions rewrite commit history and generate new commit hashes, even if the code changes remain the same. As a result, original commits—and their associated authorship or signatures—are replaced, which can alter or obscure accountability and audit trails. As a path forward, history-rewriting operations should be limited to local work before pushing to a shared repository, and teams should consider workflows that favor merge commits, which preserve original commit identities and maintain clearer traceability over time.

To get started, you simply need to set up your local environment in a few straightforward steps.

