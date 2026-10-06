# AI Chat and Agent Interface Branch

Use for chat, assistant, and agent interfaces: conversational input, streaming responses, and tool or agent execution surfaces.

## Required context

Missing facts to collect:

- what the assistant or agent does and its intended user;
- primary interaction: open-ended chat, task-specific assistant, or agent that takes actions;
- whether the agent calls tools, browses, or executes multi-step work visibly;
- input types supported: text only, attachments, voice;
- existing product surface this is embedded in, if any.

Do not invent: assistant capabilities, tools, data access, or sources.

## Branch decisions

### Layout

- Centered single column
- Sidebar with conversation history
- Embedded panel within a larger product
- Full-page dedicated experience

### Entry state

- Greeting with suggested prompts
- Blank input, no prompting
- Task or template picker

### Message presentation

- Simple bubble-style messages
- Flat text with sender labels, no bubbles
- Rich message cards (structured content, actions, previews)

### Input and control

- Text input with send button
- Multiline input with keyboard-shortcut send
- Attachment and voice input support

Requirement, not a choice: a visible stop control that stays reachable at all times during generation.

### Streaming presentation

- Token-by-token streaming text
- Chunked streaming with visible progress
- Non-streaming, full response on completion

### Agent transparency

- Response only
- Collapsed step summary with a reasoning summary, expandable
- Expanded step timeline (tool calls, inputs, results) with reasoning summaries

Models expose reasoning as summaries, not raw chain of thought; design for summaries.

### Action approval (for agents that take actions)

- Confirm every consequential action
- Auto-run safe actions, confirm consequential ones
- Autonomous with undo and an audit log

### Output surface

- Inline in the conversation
- Side panel or canvas for long artifacts
- Both

### Citations and sourcing

- No citations
- Inline citation markers
- Expandable source list

Never present generated content as sourced without a real, verifiable citation.

## Required states

- Greeting or empty conversation
- Streaming in progress
- User-initiated stop
- Tool or agent step running
- Tool or agent step failed
- Awaiting user approval
- Long-running task progress
- User message sent mid-run (queue or steer)
- Conversation or context limit reached
- Refusal or stated limitation
- Rate-limited or unavailable
- Network error and retry
- Scroll-to-latest when the user has scrolled up
- Unsupported attachment type

## Emphasis

Make limitations and failures visible rather than silently hidden.
