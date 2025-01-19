---
title: Using Lets Encrypt with Cert-Manger locally[WIP]
pubDate: 01/19/2025 14:00
upDate: 01/19/2025 14:00
author: "Brett"
tags:
  - LetsEncrypt
  - CertManager
  - Kubernetes
imgUrl: '../../assets/lets-encrypt.png'
description: Using Lets Encrypt with Cert-Manger locally[WIP]
---


# Using Lets Encrypt with Cert-Manger locally[WIP]

```text
This is a work in progress and are just notes at the moment
```



## What do I want?
I need to be able to use local certificates to secure my services

## What's my approach?

* I want to use cert-manager, metallb, and Lets Encrypt to do this work

## What do I need? 

* I can probably use the [DNS01 Challenge from Lets Encrypt](https://letsencrypt.org/docs/challenge-types/#dns-01-challenge)
    * Pro: `You can use this challenge to domain names whose webservers aren’t exposed to the public internet.`

This works well since my services are not exposed to the internet, I have a few of them, but they all need different
certs

* I can probably use the [DNS01 Challenge Provider](https://cert-manager.io/docs/configuration/acme/dns01/)
* Since I have CloudFlare as my DNS provider I can use the [CloudFlare Issuer](https://cert-manager.io/docs/configuration/acme/dns01/cloudflare/)
* I have a backup domain that I can use for this instead of my main domain
* I'll need to use the staging environment, since production for Let's Encrypt has strict rate limits
* I'll need cert-manager to rotate at the least 30 days and at the most 80 days so if there is an issue I can
figure it out before failure

* It looks like I need a middleware like Traefik or nginx to redirect from http to https in the service definitions



## References

[https://www.howtogeek.com/devops/how-to-install-kubernetes-cert-manager-and-configure-lets-encrypt/](https://www.howtogeek.com/devops/how-to-install-kubernetes-cert-manager-and-configure-lets-encrypt/)

[https://cyber-engine.com/blog/2023/07/21/k3s-kubernetes-with-metallb-traefik-rancher-longhorn-and-extras/](https://cyber-engine.com/blog/2023/07/21/k3s-kubernetes-with-metallb-traefik-rancher-longhorn-and-extras/)
