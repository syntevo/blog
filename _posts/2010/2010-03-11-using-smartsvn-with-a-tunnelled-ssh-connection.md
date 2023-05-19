---
title: "Using SmartSVN with a tunnelled SSH connection"
date: "2010-03-11"
categories: 
  - "smartsvn"
tags: 
  - "smartsvn"
---

Sometimes SVN servers are not directly accessible from the Internet, but hidden behind a corporate firewall. Using SSH tunnels is a way to allow access to such servers.

For such environments, the built-in SSH client of SmartSVN can't be used as it requires direct access to the repository server. However, you can configure and use your system _SSH_ to connect to such repositories.

The easiest way will be to use SSH's _ProxyCommand_ which can be configured in your _.ssh/config_ file ([details](http://benno.id.au/blog/2006/06/08/ssh_proxy_command)).

For my environment, I'm accessing our internal _smartserver_ over the gateway _gateway_. So my configuration looks like:

Host gateway  
 IdentityFile ~/gateway.ssh.key  
  
Host smartserver  
 ProxyCommand ssh gateway nc -w 1 smartserver 22  
 IdentityFile ~/smartserver.ssh.key

I have stripped off the passwords from both private key files, so authentication requires no interaction (refer [here](http://stackoverflow.com/questions/112396/how-do-i-remove-the-passphrase-for-the-ssh-key-without-having-to-create-a-new-key) for details). That's an important step to avoid the _OpenSSH_ password prompt or — even worse — get stuck, if that GUI-prompt does not work. Now I'm able to connect to _smartserver_ via the _gateway_, simply by invoking:

ssh smartserver

In SmartSVN's **Repository Profiles** I have set up following tunnel:

- **Name**: _ssh-gateway_
- **Command**: _ssh_
- **Parameters**: _${host} ${svnserve}_

In the **Add Repository Profile** wizard, I have entered URL _svn+ssh://smartserver/repos/smartsvn_ and on the **Details** page, selected **Tunnel** set to _ssh-gateway_. That's it!
