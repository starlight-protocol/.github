> [!IMPORTANT]
> **Current platform: [v5.0.0-alpha.4](https://github.com/starlight-protocol/starlight/releases/tag/v5.0.0-alpha.4).**
> GitHub's **Latest** badge still points to legacy v1.3.4, the old browser implementation.
> Use the **5.x alpha** for the current general-purpose agent platform.

# Starlight

**A general-purpose agent platform for turning goals into inspectable outcomes.**

Give your agents a goal, context, constraints, and ordered mission steps. Starlight routes the
work, coordinates execution, and returns reports with agent identity, attempts, results, and evidence.
Your agents supply the tools, models, planning, and domain knowledge.

[Website and narrated demo](https://starlight-protocol.github.io/starlight/) ·
[Current release](https://github.com/starlight-protocol/starlight/releases/tag/v5.0.0-alpha.4) ·
[Source code](https://github.com/starlight-protocol/starlight) ·
[Build an agent](https://github.com/starlight-protocol/starlight/blob/main/docs/AGENTS.md)

## What you can use today

- **AgentPlatform SDK:** register agents, compose sequential missions, pass results between steps,
  and optionally verify completion before continuing.
- **Local CLI:** run missions, discover agents, stream progress, and search saved run history.
- **Progress storage:** atomic checkpoints before and after steps, with optional SDK file storage.
- **API integration:** an HTTP JSON agent with origin restrictions, bounded responses, and optional verification.
- **Mission preflight:** validate a plan before loading or executing agents.
- **Remote agents:** connect Sentinels through a token-authenticated JSON-RPC/WebSocket Hub.
- **Execution controls:** capacity limits, deadlines, cooperative cancellation, and explicit outcomes.

The supported implementation is **JavaScript/Node.js 22+**. The language-neutral wire protocol
remains **1.0**, independently versioned from the implementation package.

## Run the example

From a fresh checkout:

```bash
git clone https://github.com/starlight-protocol/starlight.git
cd starlight
npm ci
npm run demo
node bin/starlight-platform.js demo --example service-health
```

Two agents read three orders, independently verify a total of **5500 cents**, write a Markdown
summary, and read it back. Each run saves a fresh artifact and report under `.starlight/runs/`.
No browser, Python environment, model, or API key is required for this example.

The service-health demo fetches three health records from a temporary local HTTP fixture,
verifies them, and saves a Markdown report. The same HTTP agent factory can connect your APIs.

For an installable package, download the tested `.tgz` and checksum from the
[current release](https://github.com/starlight-protocol/starlight/releases/tag/v5.0.0-alpha.4).

## Scope and documentation

This is an alpha runtime. Agents are trusted code with host permissions; cancellation is cooperative.
SDK history supports optional file storage; the CLI saves progress checkpoints without automatic replay or resume. Domain agents
implement planning and enforce business constraints. The public website displays recorded runs;
it does not execute agents for visitors.

- [Project objective and next steps](https://github.com/starlight-protocol/starlight/blob/main/docs/OBJECTIVE.md)
- [Agent, mission, CLI, and remote integration guide](https://github.com/starlight-protocol/starlight/blob/main/docs/AGENTS.md)
- [Progress storage, mission deadlines, and interrupted runs](https://github.com/starlight-protocol/starlight/blob/main/docs/RUNS.md)
- [HTTP agents, service-health demo, and mission validation](https://github.com/starlight-protocol/starlight/blob/main/docs/HTTP_AGENTS.md)
- [Wire protocol 1.0](https://github.com/starlight-protocol/starlight/blob/main/spec/STARLIGHT_CORE_PROTOCOL.md)
- [Network security responsibilities](https://github.com/starlight-protocol/starlight/blob/main/spec/SECURITY_PROFILE.md)
- [Technical audit and verification evidence](https://github.com/starlight-protocol/starlight/blob/main/docs/AUDIT.md)
- [Migration from the browser-era project](https://github.com/starlight-protocol/starlight/blob/main/docs/MIGRATION.md)
- [Contributing](https://github.com/starlight-protocol/starlight/blob/main/CONTRIBUTING.md)

[MIT licensed](https://github.com/starlight-protocol/starlight/blob/main/LICENSE).
