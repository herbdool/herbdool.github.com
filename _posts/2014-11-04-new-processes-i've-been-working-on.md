---
layout: post
title: "Notable development tools and processes I've been working on"
published: true
tags: 
  - project
---

I've been working on a number of Drupal 6 to Drupal 7 upgrades. When it comes down to it, many of them take just as much work as an entirely new site. But I've been putting a lot of work into getting the firm I'm working for to adopt more efficient and resiliant deployment processes.

### Migrating content
Using the [migrate](https://www.drupal.org/project/migrate) and [migrate_d2d](https://www.drupal.org/project/migrate_d2d) modules to script the mapping of fields from a Drupal 6 site to a fresh Drupal 7 site. This has been invaluable in the upgrade process even though there still ends up being lots of work with menus, dealing with translated content, blocks and views.

### Using better deployment tools
I've had the chance to start using [Pantheon](http://getpantheon.com) for one of our clients and it's pretty awesome. It makes deployment and development much easier. You get three environments in the basic package: dev, testing and live. And Pantheon provides an easy UI for managing the deployment process between each stage. For example, when pulling in code changes to testing Pantheon easily allows you to pull in the live database to see how the new code would work on the live site without exposing any issues to the public.

We've also started using [Beanstalk](http://beanstalkapp.com) to help with deployment on projects where we can't put them on something like Pantheon. This is the only way we've been able to use version control across all projects. There has been some resistance to this at work.

### Using Features and Configuration Management
A key part of improving deployment is putting all configuration changes into code instead of storing it all in the database, which is a big failing of Drupal. For this we've been using [features](https://www.drupal.org/project/features) and have started using [configuration management](https://www.drupal.org/project/configuration). Features is widely used so I don't feel the need to talk about it. The latter is a Drupal 7 module that borrows heavily from the new Drupal 8 Configuration Management Initiative, which is much better at helping with the deployment process than Features. The Drupal 7 module works fairly well but it suffers from a resource-intensive UI and from being a contributed module which can result in poor support from more obscure modules. Still it has drush commands which help quite a bit.

All of these together have really helped improve my development.
