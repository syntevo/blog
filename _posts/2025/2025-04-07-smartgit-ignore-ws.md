---
title: "Enhanced 'Ignore Whitespace' Option in SmartGit 24.1: Benefits and Best Practices"
date: "2025-04-07"
categories:
  - "smartgit"
tags:
  - "smartgit"
---

> **Note:** This post focuses on the temporary nature of the 'Ignore Whitespace' option when reviewing your *working tree*.
> It does not cover how this option functions when examining *commits*, where it remains consistently persistent across all versions.

With the release of SmartGit 24.1, we've revamped the 'Ignore Whitespace' feature to more accurately differentiate between syntactically important and unimportant whitespaces, tailored to specific programming languages. For instance, in Java, a diff between `if (x)` and `if(x)` will no longer flag this whitespace change, as it holds no syntactical significance.

While this improvement helps in reducing unnecessary clutter, it also poses the risk of overlooking significant whitespace changes -- particularly during the commit preparation phase. Conversely, you might end up staging or committing unintended whitespace changes.

For instances like file reformatting, *temporarily* ignoring whitespace changes is a convenient way to concentrate on genuine modifications. Our current approach is to support this by resetting the 'Ignore Whitespace' option when you switch files.

### Persistent Need for 'Ignore Whitespace'

If you frequently wish for the 'Ignore Whitespace' option to persist in SmartGit, there are ways to optimize your development process. Here are two common scenarios where improvements can be made:

1. **Inconsistent Code Styles:** Different coding styles within a team can lead to unnecessary changes. Agreeing on a unified coding style can reduce these issues and can often be saved directly in your repository.

2. **Changes in Code Style or Formatting Tools:** A one-time shift in coding style or the introduction of automatic formatting tools can be more manageable by reformatting all files in a single, dedicated commit, helping to keep future commits clean and focused.

### Why Not Retain the Option?

During implementation, we needed to decide if and when the option should be retained, and we concluded that for most users, resetting the option is more beneficial.
Accidentally committing too many or too few whitespace can obscure the history (Log and Blame) and complicate future repository maintenance.
Conversely, requiring an extra click for each file is a minor inconvenience compared to these potential challenges.

### Practical Example

Imagine the following scenario:

- You have several changes in your working directory that need to be divided into separate commits.
- Your first commit appears to be a single change in a reformatted file, which you stage via the *Changes View* and then commit.
- As you prepare for the second commit, you stage additional files, focusing on specific hunks.
- Finally, you stage the remaining changes for the third commit.
- The Problem: The third commit inadvertently includes reformatting remnants from files in the first and second commits.

### For Those Who Still Need to Retain the Option

We understand that each user operates under unique circumstances, and our recommendations may not be suitable for everyone.
We value our users' requirements, so we've introduced a setting under *Preferences, Low-level Properties, changes.autoResetIgnoreWhitespace* that can be adjusted to `false`.
This option is available starting from the 24.1 build 21156; if you are using an earlier build, please use Help | Check for Latest Build.

### Conclusion

To conclude, the 'Ignore Whitespace' feature in SmartGit is designed to streamline your workflow by reducing unnecessary clutter.
However, it's important to address whether your reliance on this feature is due to underlying team or tooling issues.

