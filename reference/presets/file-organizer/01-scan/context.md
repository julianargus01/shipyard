# 01-scan — Stage Context

## Purpose
Audit the folder path or fallback listing and produce a tagged inventory. This is a classification pass — no judgment about where things should go yet.

## Place in the flow
First stage. Receives the user's folder path when live file access is available; otherwise receives the user's pasted listing. Its output (the tagged inventory) feeds directly into 02-design.

## What this stage does NOT do
- Does not propose folders or structure (that is 02-design's job).
- Does not flag duplicates or junk definitively (it notes candidates; 03-plan confirms).
- Does not move, rename, or delete files.
