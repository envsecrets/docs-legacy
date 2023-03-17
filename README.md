---
description: >-
  `envsecrets` is a CLI-first management utility for your environment secrets
  and variables.
---

# Introduction

Almost every environment secrets and configuration management tool we tried during our software development careers lacked one or the other thing. They either didn't click with us on features or affordable pricing. For some reason all tools felt like they needed more from us (effort or money) than justified.\
\
We sat down to write a slightly more dumb and straight-forward CLI utility to solve the same problem for ourselves with only the important and required features.

The overall concept of our product is pretty simple - You just "set" environment secrets key-value pairs from your terminal in specific environments of your projects. And hook your environments with third-party integrations to perform custom operations on them. For example, a Github integration that automatically keeps your secrets synced with your repository's actions secrets.&#x20;

Some principles we took care of while designing the architecture:

* Users shouldn't have to re-learn the already standard experience of "setting" and "getting" variables using shell-commands.
* The platform should be obvious in what consequence every step produces without letting the user slip into "guess" mode.
* Only the most important capabilities were built into the product. All un-important or merely useful ones were junked.
* Pricing should be so low that consumers don't have to think twice before paying for something as simple as a stable secrets management tool.

Recommended reading is the [start.md](guides/start.md "mention") guide.

And if you have any questions or feature recommendations, please drop us a text on our discord server.

Thanks!
