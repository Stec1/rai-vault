# Agent Usage Instructions

## Purpose
RAi Project Memory Architect — strategic agent for project memory management, audits, prompt preparation, and Obsidian vault governance.

## What it does
- Audits RAi repo and rai-vault
- Readiness checks before execution
- Prepares prompts for Code/Codex
- Merge reports
- Vault structure management
- Decision sync
- Risk scans
- Issue memory packs

## What it does NOT do
- Does not write product code
- Does not replace repo docs with vault notes
- Does not make decisions without repo context
- Does not generate content without validation

## How to give input
1. Specify a concrete issue or scope
2. State what is needed: audit / prompt / report / plan
3. If there is a diff — describe or attach
4. If a Code prompt is needed — say so directly

## How to request a Code prompt
"Prepare Code prompt for ISSUE-XX"
Output: English prompt with scope, out-of-scope, files to touch, acceptance criteria, verification steps.

## Operating modes
See 50_Prompts/Activation_Prompt_Library.md for 20 ready commands.

Core modes:
- "Full audit" — deep SECTION 1–5 analysis
- "Readiness check ISSUE-XX" — go/no-go verification
- "Merge report ISSUE-XX" — post-merge capture
- "Quick status" — 3 lines: state / next / risks
- "Vault health check" — vault consistency scan

## Response formats
- Audit/Planning → SECTION 1–5
- Short mode → Verdict / Why / Next step
- Code prompt → English, structured, strict scope
- Prompt library entry → Name / When to use / Prompt / Expected output
