---
title: "Dispelling concerns about SmartGit's automatic connection setup to your GitHub, Bitbucket or GitLab account"
date: "2019-06-11"
categories: 
  - "smartgit"
---

We have been contacted by a user who has concerns about the link setup procedure between SmartGit and Bitbucket (Preferences, Hosting Providers). While the procedure is actually inscrutable on first glance, following it step-by-step we can see that it's safe with respect to the protection of your Bitbucket account:

As you can see from the **Request Access Token** dialog, your browser will directly open a _bitbucket.org_ **Link**. If you prefer, you may copy&paste the URL yourself to your browser.

The URL is about _OAuth_ authorization and specifies two parameters _client\_id_ and _response\_type_ which we can assume. We can assume that _client\_id_ is pretty much what it says: the Client ID of SmartGit -- otherwise that would be a significant design flaw of the Bitbucket API for such a central end point. We can also assume that Bitbucket is very much interested in telling you exactly for which access rights the _OAuth_ request is asking and that it would warn you about strange requests, to protect its users from malicious applications.

After confirming access, Bitbucket will pass an _authorization code_ to Syntevo's website. Again, we can assume that whatever this token is, Bitbucket considers it safe to pass on to the requesting application (the detour over _syntevo.com_ is necessary because Bitbucket can't pass the token directly to your running SmartGit instance).

The authorization token is [short-lived and single-use](https://www.oauth.com/oauth2-servers/authorization/the-authorization-response/); this especially means that once you have successfully authenticated, you can be sure that the token can't be used anymore (e.g. by some attacker who could have gained control over the connection between _bitbucket.org_ and _syntevo.com_ or over the connection between _syntevo.com_ and your browser).
