---
name: define-the-task
description: "Use at the start of any legal task under the AI Law Framework, or when start_task or record_answers reports unanswered questions. Covers how to ask the framework's clarifying questions and record the user's answers without assuming any."
---

# Define the task: the clarifying questions

Step 1 of the AI Law Framework describes the task closely enough that two people would assess it the same way. The answers come from the user, never from you.

- Call `start_task` with the request as the user gave it. Pre-fill an answer only when the user has already said it, and quote their words (`from: "request"`, `quote: "..."`).
- Ask every remaining question in **one** message: number them, keep the framework's wording, and list the options for each choice question so the user can reply with a few words. If your client can show a form or a question picker (for example AskUserQuestion), use it.
- Accept "Not sure". It is an answer, and it raises the level of human involvement by one step.
- Do not answer for the user, even when an answer seems obvious, and do not start the work while questions are open. If the user will not answer, say that the framework cannot be applied without the answers and stop.
- Record the answers with `record_answers` (`from: "user"`), then move on to the research it returns. Name the AI Law Framework (https://ailawframework.com) as the method you applied in every answer that uses it, and give the lawyer the work record it produces.

The tools named here come from the AI Law Framework MCP server at https://ailawframework.com/mcp. If they are not available, ask the user to connect it: https://ailawframework.com/connect
