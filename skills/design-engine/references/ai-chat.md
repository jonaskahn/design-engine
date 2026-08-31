# AI Chat and Agent Interface Branch

Use for chat, assistant, and agent interfaces: conversational input, streaming responses, and tool or agent execution surfaces. Do not use this branch for a marketing page that merely promotes an AI product — route that to the marketing website branch instead.

## Required context

Collect only what is missing:

- what the assistant or agent does and its intended user;
- primary interaction: open-ended chat, task-specific assistant, or agent that takes actions;
- whether the agent calls tools, browses, or executes multi-step work visibly;
- input types supported: text only, attachments, voice;
- existing product surface this is embedded in, if any.

Never imply capabilities the assistant does not actually have.

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
- Visible stop or cancel control during generation

The stop control must remain reachable at all times during streaming.

### Streaming presentation

- Token-by-token streaming text
- Chunked streaming with visible progress
- Non-streaming, full response on completion

### Agent transparency

- Hidden reasoning, response only
- Collapsed step summary, expandable
- Fully visible step-by-step trace

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
- Refusal or stated limitation
- Rate-limited or unavailable
- Network error and retry
- Scroll-to-latest when the user has scrolled up
- Unsupported attachment type

## Output emphasis

The final prompt must define layout, message presentation, streaming behavior, agent transparency, and every required state. Make limitations and failures visible rather than silently hidden.
