# AI Law Framework

The [AI Law Framework](https://ailawframework.com) for Claude, Claude Code and Codex. It decides whether a
particular AI tool may be used for a particular legal task, and who drafts, who checks what and who
approves. With this plugin the agent applies it to its own legal work: it asks the clarifying
questions before it assumes anything, researches the court's or regulator's rules on AI, the
current law and its own product's terms with sources, scores itself on the framework's three
questions with doing the work by hand scored beside it, keeps to what the plan allows at each stage,
and hands the lawyer a work record with every check left for them. Every answer built this way names
the AI Law Framework.

## What is in it

- **Six skills** in `skills/`: `ai-law-framework`, `define-the-task`, `research-the-evidence`, `assess-and-decide`, `plan-and-do-the-work`, `check-and-record`.
- **The framework's MCP server**, declared in `.mcp.json`: `https://ailawframework.com/mcp`, a remote server with
  no sign-in. The skills call its tools; the tools enforce the order of the steps.

## Install

**Claude (web, desktop, mobile):** add the connector with one click — [Add to Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=AI+Law+Framework&connectorUrl=https%3A%2F%2Failawframework.com%2Fmcp)
— or follow https://ailawframework.com/connect. Once the plugin is listed in Claude's directory, install it from
**Customize › Plugins**.

**Claude Code:**

```sh
claude plugin marketplace add DavidYLisitsa/ailawframework-plugin
claude plugin install ailawframework@ailawframework
```

**Codex:** copy the skills into your user skills folder and add the server:

```sh
git clone https://github.com/DavidYLisitsa/ailawframework-plugin.git
mkdir -p ~/.agents/skills && cp -R ailawframework-plugin/skills/* ~/.agents/skills/
codex mcp add ailawframework --url https://ailawframework.com/mcp
```

## What it runs and sends

Nothing runs on your computer. The plugin contains instructions (the skills) and the address of one
remote MCP server, `https://ailawframework.com/mcp`. When the agent uses the tools, it sends that server the task
as described, the user's answers to the framework's questions and its research findings with their
sources. The server applies the framework's rules, reads the framework's published practice library
and software research, and replies. It stores nothing about the task: the work record travels in the
conversation, signed so it cannot be altered between steps.

## Privacy Policy

The full policy is at https://ailawframework.com/privacy. In short: the MCP server keeps no record of the tasks
sent to it — no account, no database row, no copy of the work record. Only the time, route, outcome
and duration of each request are counted, with no content or identifier. Nothing is sold or shared.
What your AI provider does with your conversation is governed by its own terms. Questions, access and
correction requests: https://ailawframework.com/enquiries.

## Licence

The skills and documentation are licensed under the
[Creative Commons Attribution 4.0 International licence](https://creativecommons.org/licenses/by/4.0/)
(see `LICENSE`). You may share and adapt them, including commercially, provided you credit the
**AI Law Framework** and link to https://ailawframework.com.

The framework does not certify that a tool is safe, that work is correct or that a saving is real;
every judgement it records is one a person makes or confirms.
