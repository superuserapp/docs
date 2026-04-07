---
description: A brief introduction to Superuser
---

# Introduction

## What is Superuser?

[Superuser](http://superuser.app/) is team chat with agents that use hosted tools. The easiest way to think about Superuser is like, "Discord or Slack with better bots." Our goal is to integrate AI seamlessly into team chat.

### Team chat

* IRC-inspired social chat you've come to know and love
* Workspace / server support via _organizations_
* Public and private channels
* Direct messages, notifications
* Friends, emojis, reactions, /me messages
* File uploads
* Person-to-person chat is **completely free**

### Agents

* Bots that come with AI tooling pre-packaged
* Use a pre-built agent or create your own
* Choose your LLM, define your system prompt
* Add additional context with notes, file uploads and websites
* Extend with **hosted tools** for custom functionality
* We keep your agents online 24/7, no hosting required
* Agents billed by token consumption

### Hosted tools

* APIs powered by JavaScript
* Use pre-built tools or create your own
* They are exposed via traditional HTTP API and MCP bindings
* They execute custom code on your behalf
* Version control, security and authentication built-in
* Can be **private**, **public** or **open source**
* As the name implies, we host these tools for you
* Tools are billed by compute usage
* [View tool registry](https://superuser.app/toolkits)

## What can I use Superuser agents for?

* Analytics and reporting
  * Hook up to your [PostgreSQL](https://superuser.app/org/superuser/toolkits/postgres) instance and execute queries
* Image generation
  * Generate images with [Nano Banana 2](https://superuser.app/org/superuser/toolkits/nano-banana-2) or [GPT image](https://superuser.app/org/superuser/toolkits/gpt-image)
* Research and web queries
  * [Exa search](https://superuser.app/org/superuser/toolkits/exa-search), [Perplexity search](https://superuser.app/org/superuser/toolkits/perplexity-search) or [Wikipedia](https://superuser.app/org/superuser/toolkits/wikipedia)
* Personal use
  * [Retrieve the weather](https://superuser.app/org/superuser/toolkits/open-meteo) or [find a YouTube video](https://superuser.app/org/superuser/toolkits/youtube)

## How does pricing work?

You can view up-to-date pricing at [Superuser / Pricing](https://superuser.app/pricing). Quick summary;

* All **person-to-person chat** is **completely free**
* We charge a monthly subscription fee for access to agents
  * Starting at $20 / mo for 5,000 messages / month
  * Overage is charged per-token to your credit balance
* We charge per-use for hosted tools at a rate of 50 credits per 1,000 GB-s of usage
  * 200ms execution for a hosted tool with 512MB of RAM is 0.005 credits
  * 1,000 function calls at this rate would be 5 credits
