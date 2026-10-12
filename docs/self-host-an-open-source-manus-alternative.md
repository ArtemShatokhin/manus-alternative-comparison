# Self-host an open-source Manus alternative

If you want a Manus-style agent that returns finished work, but your data, models, and configuration have to stay in your own infrastructure, the deciding question is whether the platform can run outside the vendor's cloud at all. Manus is a hosted product: its own pages describe web, desktop, and mobile apps and offer no self-host path. Kortix is the open-source AI Operating System, and it is the one in this comparison that self-hosts the whole thing: the repo, the agents, the sessions, the connectors, and the review gate.

## The self-hosting decision

Self-hosting an agent platform is worth it when three things matter. You need the configuration to live in a repo you own, you need to bring your own model keys, and you need the compute to run in your VPC or on-prem network. It costs you the setup time and the upkeep that a hosted product absorbs for you. The hosted field, including Manus, is the right call when you want the artifacts fast and you do not need to own the stack.

The open-source projects each self-host a different amount. OpenHands is a self-hosted developer control center for coding agents, MIT-licensed, and runs agents in Docker, on a VM, or on a server. OpenWork is a free, open-source desktop app that runs agents on your own files. Hermes is an MIT-licensed agent runtime with built-in memory that installs on a small VPS. Open WebUI self-hosts a chat interface for local and cloud models. n8n is a fair-code workflow canvas you can self-host. Kortix is the one that self-hosts the operating-system layer: agents, skills, memory, connectors, triggers, and the reviewed path back to `main` in a single stack.

## The Kortix mechanism

A Kortix project is a git repo with `kortix.yaml` at its root. Agents, skills, memory, tools, triggers, and connectors are all files in it. Starting a session boots an isolated sandbox that clones the repo and works on a new branch. When the agent wants to keep its work, it commits, pushes, and opens a change request; a person merges it. That is the whole loop, and it runs the same on your own box as it does in the managed cloud.

To bring it up on your own infrastructure, install the CLI and then run the self-host command:

```bash
curl -fsSL https://kortix.com/install | bash
kortix self-host start   # one Docker Compose stack on your own box
```

The first run asks six things and no model key. GitHub connects in the dashboard under Settings, then Git. Models are BYOK in the app, and Pipedream is optional. The stack has no Redis and no separate worker, so there is one service to run and one place to look when something fails. You can host it on Kortix Cloud, in your VPC, or on your own on-prem network, and self-host is free.

## What you get to own

Once it is running, the parts that stay with you are the ones the hosted products keep. The configuration is a repo you can clone, diff, and roll back. The memory is files that accumulate. The models are your keys, from any provider. Sessions run on isolated sandboxes, one per session, each on its own branch, and thousands can run in parallel on one config. Every action is recorded, and per-resource permissions cover people and agents, with roles, groups, and an audit trail. On the enterprise path you add SAML 2.0 single sign-on and SCIM 2.0, plus Cloud, VPC, or on-prem deployment. SOC 2 Type I is held; SOC 2 Type II is in progress.

Self-hosting trades setup time for ownership. It is the path a team takes when a security review or a network boundary decides where the work may run.
