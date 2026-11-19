Personal Project Intelligence

An evidence-driven project management system for AI coding agents.

A personal project management system that turns AI coding activity into structured, reviewable project progress.

Built for developers working across multiple projects with AI coding agents such as Claude Code and Codex.

The long-term vision is to evolve from passive progress tracking into a Personal SuperAgent capable of understanding project goals, proactively managing tasks, and coordinating multiple coding agents.

Motivation

AI coding agents are becoming increasingly capable, but managing development across multiple agents and projects remains fragmented.

When working with Claude Code and Codex, I found myself repeatedly facing the same problems:

* Development progress is scattered across different agent sessions.
* Important decisions and completed work are difficult to track over time.
* Updating project plans and documentation requires manual effort.
* Agent-reported completion does not necessarily mean a task is actually finished.
* There is no unified view of project status, milestones, blockers, and next steps.

The goal of this project is to make project progress a continuously maintained state, rather than something reconstructed manually from conversation history.

What It Does

The current prototype integrates Claude Code, Codex, and DingTalk through an event-driven, human-in-the-loop workflow.

1. Capture Agent Activity

Hooks capture relevant development activity from AI coding sessions, including prompt submissions and tool execution events.

2. Generate Evidence-Backed Progress Updates

The system analyzes agent interactions and produces structured progress proposals containing:

* What was accomplished
* Supporting evidence
* Current conclusions and task status
* Remaining work and next steps

3. Human-in-the-Loop Review

Instead of directly modifying project records, the system generates proposed changes for review.

Only approved changes are written to the project ledger.

4. Update and Verify Project Records

Approved changes are synchronized to DingTalk project documents, followed by readback verification.

The project model supports:

* Projects and work items
* Subtasks and milestones
* Evidence and supporting artifacts
* Linked documentation
* Progress updates and next actions

Architecture

The current workflow can be summarized as:

Claude Code / Codex
        |
        v
   Lifecycle Hooks
        |
        v
 Activity Collection
        |
        v
 Progress Extraction
        |
        v
 Proposed State Changes
        |
        v
   Human Approval
        |
        v
 DingTalk Project Ledger
        |
        v
 Readback Verification

The key principle is to separate agent activity, proposed progress, and verified project state.

An agent reporting that work is complete is not sufficient evidence that the corresponding project milestone has been achieved.

Real-World Example

In a real workflow on November 19, the system processed progress related to a component upgrade.

The agent identified that a change request had been submitted and was awaiting approval.

The system generated a progress proposal that:

* Recorded the change request submission
* Associated supporting evidence with the relevant work item
* Preserved the pending approval status
* Maintained subsequent upgrade and verification steps

After human approval, the changes were written to the project ledger and verified through readback.

Submitting a change request is not the same as completing an upgrade.

This distinction is fundamental to the system’s approach to reliable project state management.

Current Status

Early working prototype — used in real development workflows.

Implemented:

* [x]	Claude Code and Codex hook integration
* [x]	Agent activity-based progress extraction
* [x]	Evidence-backed progress proposals
* [x]	Human approval before project state changes
* [x]	DingTalk project record synchronization
* [x]	Readback verification
* [x]	Structured work items, subtasks, milestones, evidence, and document associations

Roadmap

Phase 1 — Project Intelligence

* [ ]	Unified cross-agent session and task tracking
* [ ]	Cross-project progress dashboard
* [ ]	Improved progress extraction and evidence validation
* [ ]	Automatic blocker and risk detection
* [ ]	Timeline and milestone tracking

Phase 2 — Proactive Project Management

* [ ]	Long-term project memory
* [ ]	Goal-aware task planning
* [ ]	Proactive progress monitoring and reminders
* [ ]	Task dependency analysis
* [ ]	Context-aware next-action recommendations

Phase 3 — Personal SuperAgent

* [ ]	Multi-agent task orchestration
* [ ]	Managed execution across coding agents
* [ ]	Execution isolation and conflict detection
* [ ]	Automated validation and feedback loops
* [ ]	Controlled autonomous task execution

Design Principles

Evidence over claims. Agent-generated summaries are proposals, not automatically verified facts.

Human control over project state. Important updates require explicit approval.

Projects over sessions. Project goals, milestones, and decisions should persist independently of individual agent conversations.

Incremental autonomy. Start with reliable observation and progress tracking, then introduce planning and execution capabilities.

Agent-agnostic architecture. Project intelligence should not depend on any single coding agent.

Vision

Most AI coding tools focus on making individual coding sessions more productive.

This project explores a complementary question:

What if AI could continuously understand and manage the progress of everything we are building?

The ultimate goal is a personal AI system that not only helps write code, but also remembers project context, tracks progress, identifies what needs attention, and coordinates work toward long-term goals.

⸻

Built to solve a real personal workflow problem, evolving toward a Personal SuperAgent.
