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

SSH commit signing requires **Git version 2.34.0 or newer**, which introduced native support for signing commits and tags using SSH keys. Earlier Git versions only support GPG-based signing, so upgrading is necessary to use SSH-based commit signing reliably on platforms like GitHub and GitLab.

To get started, you simply need to set up your local environment in a few straightforward steps.

Open a Git Bash (e.g. via the SmartGit - Tools menu) and execute the following steps:

```bash
git --version
ssh-keygen -t ed25519 -C "$(git config user.email)"
git config --global gpg.format ssh
git config --global user.signingkey ~/.ssh/id_ed25519.pub
git config --global commit.gpgsign true
```
This will set it up for your current user, if you just want to have repo level commit signing remove the `--global` from the steps that alter the git config.

From now on every commit will be signed with your SSH key - to enable the hosting provider to verify them you need to expose your public key to them.

You can print said public ssh key in your bash via 

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy it and expose it to the backend.

For GitHub you navigate to https://github.com/settings/ssh/new and add a new SSH key of type "Signing Key".

For GitLab you navigate to https://gitlab.com/-/user_settings/ssh_keys and add a new SSH sey of type "Authentication & Signing" or "Signing".

In case you want to validate your times signed commits locally maintain a `~/.ssh/allowed_signers` file and add the keys of your team members and add a pointer to said file to your git config.

```bash
git config --global gpg.ssh.allowedSignersFile ~/.ssh/allowed_signers
```

You can add your own key by simply running an echo command from the bash.

```bash
echo "$(git config user.email) $(cut -d' ' -f1-2 ~/.ssh/id_ed25519.pub)" >> ~/.ssh/allowed_signers
```

You are all set and will be able to see cryptographically verified commtis by executing git log with an additional parameter.

```bash
git log --show-signature -1
```

As of version 25.1, **SmartGit** does not display commit verification details by default. If this is important for your workflow, you can use a lightweight PowerShell script provided by **Daniel Siegl** ([https://github.com/danielsiegl/checksshsign/](https://github.com/danielsiegl/checksshsign/)), which downloads the public keys of all contributors, verifies the authenticity of signed commits, and attaches the results as Git Notes. After running the script from the SmartGit Tools menu, the verification status becomes easily visible directly within the SmartGit UI for the current repository.