# Base vagrant box for ruby development

## Requirements

* [VirtualBox](https://www.virtualbox.org)
* [Vagrant](http://vagrantup.com)
    >= 1.1.2 required

## How To Build The Virtual Machine

    host $ git clone
    host $ cd base-dev-box
    host $ git submodule init
    host $ git submodule update
    host $ vagrant up

## What's In The Box

* RVM
* Ruby 2.0.0
* Bundler
* Postgres
* SQLite
