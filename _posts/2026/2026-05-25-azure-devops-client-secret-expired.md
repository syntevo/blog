---
title: "Azure DevOps authentication: please switch to personal access tokens"
date: "2026-05-25"
categories:
  - "smartgit"
tags:
  - "smartgit"
  - "azure-devops"
---

If you are using Azure DevOps with SmartGit and authentication fails, please create an Azure DevOps personal access token and configure SmartGit according to our [setup instructions](https://docs.syntevo.com/SmartGit/Latest/Manual/Integrations/Azure-DevOps#setup-via-personal-access-token).

Microsoft is deprecating Azure DevOps OAuth. According to Microsoft's documentation:

* new Azure DevOps OAuth app registrations are no longer accepted since April 2025
* Azure DevOps OAuth is scheduled for full deprecation in 2026
* existing Azure DevOps OAuth application secrets expire after 60 days and must be rotated regularly

See Microsoft's documentation on [Azure DevOps OAuth deprecation](https://learn.microsoft.com/en-us/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops) and [managing Azure DevOps OAuth application secrets](https://learn.microsoft.com/en-us/azure/devops/integrate/get-started/authentication/azure-devops-oauth?view=azure-devops#managing-app-secrets).

Microsoft recommends [Microsoft Entra OAuth](https://learn.microsoft.com/en-us/azure/devops/integrate/get-started/authentication/entra-oauth?view=azure-devops) as the long-term replacement for Azure DevOps OAuth. However, this is currently not a drop-in replacement for all SmartGit users, because Microsoft also documents that Entra apps do not yet natively support Microsoft account (MSA) users for the Azure DevOps resource.

Because of this, we currently recommend using [personal access tokens](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops) for Azure DevOps authentication in SmartGit. Microsoft describes them as an alternative password for Azure DevOps, and our [SmartGit setup instructions](https://docs.syntevo.com/SmartGit/Latest/Manual/Integrations/Azure-DevOps#setup-via-personal-access-token) explain the required configuration.
