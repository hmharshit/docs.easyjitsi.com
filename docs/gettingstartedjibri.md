---
id:docker
title: Jitsi Meets Docker 
sidebar_label: Jitsi Meets Docker
---

<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-163579416-2"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-163579416-2');
</script>

In order to record conferences the following are required;

## Prerequisites

- An Ubuntu 18.04 LTS x64 server with an [IPv4 address](https://en.wikipedia.org/wiki/IPv4).

### Ubuntu Server Specific Prerequisites

- A [root]("https://geek-university.com/linux/root-account/") user
- A sub domain **recorder.easyjitsi.com** being pointed to the server mentioned above.

NB: **_Our example server will be using 8GB of RAM_**

## Setting Up The Server

On our local system, we login into our Ubuntu server

```bash
ssh root@recorder.easyjitsi.com -p 22
```

We then run the following command to setup a hostname, recorder, and an FQDN, recorder.easyjitsi.com, for the machine:

```bash
 hostnamectl set-hostname recorder
 sed -i 's/^127.0.1.1.*$/127.0.1.1 recorder.example.com recorder/g' /etc/hosts
```

To verify it was set properly we run these commands

```bash
hostname
hostname -f
```

**_If you encounted any errors or you found it difficult while following these steps, you can head [here](https://docs.easyjitsi.com/docs/help) to seek help from us._**