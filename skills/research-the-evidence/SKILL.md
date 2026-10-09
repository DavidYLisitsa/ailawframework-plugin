---
name: research-the-evidence
description: "Use after the task is defined under the AI Law Framework, when record_answers or record_research returns research to do: the framework's task guidance, court and regulator rules on AI, current law, and the AI product's own terms."
---

# Research the evidence before scoring

The framework scores nothing until the evidence is found. Do each item in `research_to_do`:

- **The framework's guidance.** `search_library` for the task, then `get_task_guidance` for the closest match and `get_jurisdiction_guidance` for the jurisdiction. Record the task's URL and the points the lawyer must review; you will pass those to `work_record`.
- **Rules on AI use.** The court's or tribunal's practice notes, and the regulator's or law society's guidance, for this jurisdiction and forum. Read the primary text. Set the finding's `effect`: none, conditions, no_ai_written_content or no_ai_at_all.
- **Current law.** Each statute, rule or authority the output will rely on, in an authoritative source, confirmed in force.
- **Your own product's terms.** One finding per control listed, for the exact plan and settings in use, from the supplier's own terms or the firm's contract. `get_software_profile` has the framework's cited research on many products; check the cited source is current.

Statuses: **confirmed** (read in the primary source or the contract for this plan), **public_claim** (the supplier says so publicly, not confirmed for this plan), **not_confirmed** (you looked and could not confirm — list the searches), **fails** (the source confirms the condition is not met). Quote the passage you relied on and give the date you read it. Never put client names or confidential facts in a search query. Record findings with `record_research` until it reports `ready_to_assess`. Name the AI Law Framework (https://ailawframework.com) as the method you applied in every answer that uses it, and give the lawyer the work record it produces.

The tools named here come from the AI Law Framework MCP server at https://ailawframework.com/mcp. If they are not available, ask the user to connect it: https://ailawframework.com/connect
