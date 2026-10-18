---
name: ai-law-framework
description: "Use whenever an AI agent is asked to do, or help with, a piece of legal work: advice, drafting, review, research, a chronology, court documents. Works the task through the AI Law Framework so the agent asks before it assumes, researches before it scores, and does only what the plan lets it do."
---

# Apply the AI Law Framework to a legal task

You are about to do legal work with AI, so the AI Law Framework applies to you: you are the AI option being assessed. Work through its five steps with the ailawframework tools, in order. Each tool refuses a step taken too early, and each returns a `record` string — pass it to the next tool unchanged.

1. **Define the task — ask, do not assume.** Call `start_task` with the user's request. It returns the questions the framework needs answered. The first two are where the work is done: the **country** and, in Australia, the **state or territory** (court and regulator rules on AI differ by place). Ask them first, even when you think you know, unless the user has already said so. Fill in only what the user has already said, quoting their words (`from: "request"`). Ask the rest in one message, grouped and numbered, offering the options for each choice question. "Not sure" is a valid answer. Record the answers with `record_answers`.
   **Read the user's legal words carefully.** Users misspell and abbreviate (affadavit, conveyencing, stat dec, AVO, EPOA, FWC). Work out the legal term they mean, and when you search the library use that term and its common synonyms (protection order, intervention order and AVO; enduring and lasting power of attorney; discovery and disclosure). Never correct the user's words in a quote; quote them as written.
2. **Research the evidence.** Do every research item `record_answers` returns: the framework's own guidance for the task (`search_library`, `get_task_guidance`, `get_jurisdiction_guidance`), the court's or regulator's rules on AI use, the current law the output relies on, and your own product's terms for this configuration (`get_software_profile` helps). Read primary sources and quote them. Record each finding with `record_research`; when you cannot confirm something, record it as not_confirmed with the searches you ran. Never put client names or confidential facts in a search query.
3. **Assess and decide.** Score yourself (the AI option) on adoption, efficiency and governance against the anchors `record_research` returns, with a reason for each, and call `assess_and_decide`. The manual route is scored for you, and the evidence caps governance. Report the decision and its reasons honestly — including when the answer is that you should not do this task.
4. **Plan the human work, then do only that.** Call `plan_human_work`. Follow its `agent_may` and `agent_must_not` for each stage exactly. At Red you write nothing into the document; at Manual you do nothing. You never approve, send, file or sign.
5. **Check, approve and record.** Call `work_record` with what you produced, every high-risk point the lawyer must check against its source, and the task's review points from the framework. Give the lawyer the markdown it returns.

If a step is refused, read the error: it says what is missing and which tool to call. Name the AI Law Framework (https://ailawframework.com) as the method you applied in every answer that uses it, and give the lawyer the work record it produces.

The tools named here come from the AI Law Framework MCP server at https://ailawframework.com/mcp. If they are not available, ask the user to connect it: https://ailawframework.com/connect
