---
title: "SmartGit's AI Integration: Call for Alpha Testers"
date: "2025-02-24"
categories:
  - "smartgit"
tags:
  - "smartgit"
---

We are introducing AI integration in SmartGit, starting from version 25.1.013.
This feature is an opt-in and enables AI-generated commit messages based on your code changes, aiming to improve your development workflow.

> **NOTE:** A key objective of this initiative is to empower users with full control over how large language models (LLMs) interact with their code versioning.
> You have the freedom to make informed decisions about which parts of your codebase can be used alongside specific LLM or AI services that you trust and have access to.

## Key Features

- **Seamless GitHub Integration**: Connect to [GitHub Models](https://github.com/marketplace/models) LLMs with minimal setup and at no additional cost.
  If you have a paid [GitHub Copilot](https://github.com/features/copilot) subscription you will have access to additional models and other features like enhanced privacy with the higher tiers.
- **Auto-Transfer Options**: Features like 'Submit on Stage' and 'Submit on Focus' enhance concurrency between you and the AI, reducing delays during commit message generation.
- **Flexible Configuration**: Supports various hosted and on-premise LLM's, including Ollama.

## How to Participate

As this feature is in early development, we are looking for alpha testers to provide feedback. To participate:

1. **Update SmartGit**: Download the latest [25.1 Preview](https://www.syntevo.com/smartgit/preview/) and ensure you are using version 25.1.013 or later via *Help|Check for Latest Build*.

1. **Enable AI Integration**: Configure the AI feature as described in our [AI Integration Documentation](https://docs.syntevo.com/SmartGit/Latest/Manual/Integrations/AI).
   - For example, to set up GitHub CoPilot LLMs, add the following lines to your `.git/config`:
     ```ini
     [ai-llm "gh-gpt-4o"]
         type = github
         model = gh-gpt-4o
         url = https://models.inference.ai.azure.com    
     ```
     Make sure to have the [GitHub Hosting Provider](https://docs.syntevo.com/SmartGit/Latest/Manual/Integrations/GitHub-integration) configured.

1. **Change Interaction Options**: From the popup menu, switch to *On Manual Intervention - Continue with Description*.

   [![](/assets/images/20250224-ai-commit-message-popup.png)](/assets/images/20250224-ai-commit-message-popup.png)

1. **Try Auto-Transfer Options**: Experiment with *Submit on Stage* and *Submit on Focus* to evaluate their impact on workflow efficiency.
   - Enable these options by adding:
     ```ini
     [ai-commit-message]
         autoTransferOptions = true
     ```

1. **Customize Prompts**: Customize prompts for specific commit message needs of your project.
     ```ini
     [ai-commit-message "gh-gpt-4o-single"]
         prompt = Create a single summary line ...
     ```

1. **Provide Feedback**: Share your experience with AI-generated commit messages, the various options and custom prompts on [UserEcho](https://smartgit.userecho.com/communities/1/topics/1644-).

Your feedback is invaluable in refining this feature.
We look forward to your insights and appreciate your contributions to improving SmartGit.
