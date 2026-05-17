# code

`code` is a placeholder name for an open source web UI built around the [pi coding agent](https://pi.dev) SDK.

I'm building it as a personalized developer workbench: a fast, thoughtful interface for working with coding agents across real projects, with the tools and workflows I reach for every day.

## Vision

I want `code` to wrap the pi SDK with a web-first experience for human-in-the-loop software development. Instead of forcing every workflow through a terminal chat UI, I want a dedicated workspace for reviewing changes, managing sessions, steering the agent, and connecting project context to concrete actions.

The app should feel like a focused developer cockpit where I can:

- review code changes visually
- leave notes and comments for the agent
- ask the agent to act on selected files, hunks, comments, or tasks
- track sessions across projects and worktrees
- manage git state without switching tools constantly
- keep the workflow personalized, scriptable, and extensible

## Core ideas

### Web UI for the pi SDK

Use pi as the agent runtime and expose it through a custom web interface.

I want to preserve pi's strengths:

- model/provider support
- tool execution
- sessions and branching
- extensions and skills
- project context
- local-first development

while adding a UI designed around how I actually work.

### File tree and diff review

A first-class changed-files view for reviewing agent-authored changes.

Planned capabilities:

- project file tree
- changed-file tree
- unified and side-by-side diffs
- hunk navigation
- inline comments
- comment-to-agent handoff
- syntax highlighting
- search and filtering
- refresh as the working tree changes

Potential building blocks:

- `@pierre/diffs` for rich diff rendering
- `@pierre/trees` or a custom React tree for file navigation
- git diff/status APIs from the backend

### Git integration

The app should understand and expose common git workflows without becoming a full Git client clone.

Potential capabilities:

- status overview
- staged/unstaged changes
- branch and commit info
- staging and unstaging
- commit creation
- diff review by file/hunk
- PR-oriented summaries
- safe action confirmations

### Session and project management

Make pi sessions visible and manageable.

Potential capabilities:

- list and resume sessions
- session names and metadata
- project dashboard
- active model/thinking level/tools
- session tree/branch navigation
- summaries and checkpoints
- links between sessions, worktrees, branches, and tasks

### Worktree support

I often work across branches and projects. The UI should make worktrees easy.

Potential capabilities:

- list worktrees for a repo
- create/switch/remove worktrees safely
- associate sessions with worktrees
- launch agent sessions in specific worktrees
- compare worktrees or branches

### Actions

The UI should support reusable workflow actions that combine context, tools, and prompts.

Examples:

- review current diff
- fix selected comments
- summarize branch changes
- prepare PR description
- run checks
- investigate failing tests
- refactor selected file
- create follow-up tasks

Actions should be customizable and eventually extensible.

## Initial architecture sketch

```text
web app
  ├─ chat / agent panel
  ├─ project + session dashboard
  ├─ file tree
  ├─ diff viewer
  ├─ comments / notes
  └─ action palette

backend
  ├─ pi SDK runtime
  ├─ session manager
  ├─ git service
  ├─ filesystem service
  ├─ worktree service
  └─ websocket/event stream
```

## Design principles

- Local-first by default.
- Human-in-the-loop review should be easy.
- Agent actions should be inspectable and reversible.
- Prefer focused workflow primitives over giant feature surfaces.
- Keep it personal first, then generalize what proves useful.
- Extensions and skills should remain part of the system where they make sense.

## Status

Very early. This repository starts as a placeholder and project brief.
