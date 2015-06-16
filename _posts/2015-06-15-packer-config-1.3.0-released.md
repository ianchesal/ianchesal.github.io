---
layout: post
title: packer-config v1.3.0 gem released!
---

The 1.3.0 release of [packer-config](https://github.com/ianchesal/packer-config) is [live on rubygems.org](https://rubygems.org/gems/packer-config).

This release adds support for the [VMWare ISO](https://www.packer.io/docs/builders/vmware-iso) builder courtesy [Matasano Security](https://github.com/tduehr).

`packer-config` is a Ruby interface to the [Packer](https://packer.io/) project from [HashiCorp](https://hashicorp.com/). Packer lets you build different kinds of virtualized machine images (Docker, Vagrant, VirtualBox, Amazon AMI, etc.) from standardized and shared configuration code bases and the `packer-config` gem lets you write your Packer configurations in Ruby instead of in that hybrid JSON, custom config language that Packer sports. You can use the full power of the Ruby programming language to drive `if/then/else` decisions when constructing your Packer configurations and it simplifies the creation of macros and envvar references in your Packer configurations.

There's [a working example in the README for the project](https://github.com/ianchesal/packer-config#examples) that shows you how to provision a customized CentOS 6.6 Vagrant basebox using Packer and the `packer-config` interface.

The 1.3.0 release supports the following builders:

* amazon-ebs
* amazon-instance
* docker
* virtualbox-iso
* vmware-vmx
* vmware-iso
* null

The following provisioners:

* file
* shell
* ansible
* chef-client
* chef-solo
* salt
* puppet server
* puppet masterless

And the following post-processors:

* docker-import
* docker-push
* vagrant

As always, pull requests are more than welcome for the project. Please open pull requests against the `develop` branch and not the `master` branch. Thanks!
