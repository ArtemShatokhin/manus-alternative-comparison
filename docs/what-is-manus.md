# What is Manus?

Manus is a hosted AI agent product from Manus AI, marketed on its own site as "the action engine that goes beyond answers to execute tasks, automate workflows, and extend your human reach." It runs in the browser, with desktop and mobile apps, and it is sold on credit-based monthly plans rather than as software you install. Its pages, checked October 2026, describe the product as Manus 2.0.

## What Manus does

Manus is built around producing finished artifacts and taking actions. Its own feature list covers AI slides, website building, game development, AI design, an image generator, a music generator, and video with a video editor. Around those it lists agentic surfaces: a browser operator that drives a web session, Wide Research for scaled investigation, Mail Manus for inbox work, a Slack integration, and Automations for scheduled runs. It also publishes an API, a Team plan with SSO, and mobile and desktop apps.

The pricing page lists individual tiers of roughly 4,000, 8,000, and 40,000 credits per month, each including 300 refresh credits a day, 20 concurrent tasks, and 20 scheduled tasks, with an annual discount. A separate Team plan is aimed at groups, and Manus compares itself with ChatGPT, Lovable, and Replit on its own site.

## What a team does not own with Manus

Manus is a managed service, and its own pages do not offer a self-host or bring-your-own-infrastructure option. A team configures Manus inside the Manus product. The account settings, the connector wiring, and the run history live on Manus's side of the wall, not in a repo the team can clone. You cannot diff the agent configuration, grep the accumulated context, or move the whole setup to another host and keep running it.

That is the trade a buyer makes: Manus gives a polished, hosted way to get slides, research, video, and browser work back quickly, and in exchange the configuration, the models, and the infrastructure stay with the vendor.

## Where Kortix fits

Kortix is the open-source AI Operating System, and it is built for the team that wants the finished-artifact outcome without giving up ownership. Your agents, their skills, your company memory, and every connector live in one git repo you own. Each session runs on its own cloud computer, and work reaches `main` through a change request a person approves. Run it on Kortix Cloud, in your VPC, or on your own on-prem network, and self-host is free. Any model provider works with your own keys.

The split comes down to where the work runs. Manus runs in Manus's cloud. Kortix runs the same kind of agent work on infrastructure you control, with the company configuration sitting in a repo you can read, fork, and audit.
