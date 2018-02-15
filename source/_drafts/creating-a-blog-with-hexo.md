---
title: Creating a blog with Hexo
tags:
- hexo
---

an attempt to document and keep track of what I did to set up this blog

## initial steps

* [Install hexo](https://hexo.io/docs/index.html#Installation)
* [Create a new blog](https://hexo.io/docs/setup.html)

## create a git repo

Hexo creates a node.js project and I want to maintain this in a dedicated git repo

## tweak config

## add Hexo plugins

## create some content

## deploy to github pages

## register domain

## configure dns

### Create an apex domain

To set up an apex domain, such as example.com, you must configure an `ALIAS`, `ANAME`, or `A` record with your DNS provider.

As documented in [_Customizing GitHub Pages_][customizing-github-pages]:

> Follow your DNS provider's instructions to create two A records that point your custom domain to the following IP addresses:
> \> 192.30.252.153
> \> 192.30.252.154
> <cite>-- [Setting up an apex domain: Configuring `A` records with your DNS provider](https://help.github.com/articles/setting-up-an-apex-domain/#configuring-a-records-with-your-dns-provider)</cite>

* dig `jayrgee.net`

  ```cmd
  C:\>dig +noall +answer jayrgee.net
  ```

  Apex domain should point to the two IP addresses you configured.

  ```cmd
  jayrgee.net.            3599    IN      A       192.30.252.154
  jayrgee.net.            3599    IN      A       192.30.252.153
  ```

### Create a www subdomain

To set up a www subdomain you must configure a `CNAME` record with your DNS provider.

Again, as documented in [_Customizing GitHub Pages_][customizing-github-pages]:

> Follow your DNS provider's instructions to create a `CNAME` record that points to your default pages domain, such as `YOUR-GITHUB-USERNAME.github.io` to your subdomain.
> Your DNS changes can take over a full day to update and the wait varies among DNS and hosting providers.
> <cite>-- [Setting up a www subdomain: Configuring a `CNAME` record with your DNS provider](https://help.github.com/articles/setting-up-a-www-subdomain/#configuring-a-cname-record-with-your-dns-provider)</cite>

* dig `www.jayrgee.net`

  ```cmd
  C:\>dig +noall +answer www.jayrgee.net
  ```

  ```cmd
  www.jayrgee.net.        3599    IN      CNAME   jayrgee.github.io.
  jayrgee.github.io.      3599    IN      CNAME   sni.github.map.fastly.net.
  ```

### useful dns links

* [DIG Manual pages](ftp://ftp.isc.org/isc/bind9/9.12.0/doc/arm/man.dig.html)
* [BIND (includes DIG dns tool)](https://www.isc.org/downloads/bind/)
* [How to install DIG dns tool on windows 10](http://nil.uniza.sk/linux-howto/how-install-dig-dns-tool-windows-10)
* [Global DNS Propation Checker - What's my DNS?](https://www.whatsmydns.net/)

[customizing-github-pages]: https://help.github.com/categories/customizing-github-pages/

## Hexo

[Hexo](https://hexo.io/) is a _fast, simple & powerful blog framework, powered by Node.js_.

### Useful Hexo References

* [Hexo documentation](https://hexo.io/docs/)

* [Getting Started with the Hexo Blogging Framework](https://www.cgmartin.com/2016/01/03/getting-started-with-hexo-blog/)

* [Hexo.io - Static Site Generator & Blog Platform](http://jr0cket.co.uk/hexo/)