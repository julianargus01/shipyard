# 02-design — Stage Context

## Purpose
Using the tagged inventory from 01-scan and the rules in context.md, propose a folder tree and naming convention. This is the judgment stage — the quality of the output depends entirely on how well context.md encodes the user's preferences.

## Place in the flow
Second stage. Receives the tagged inventory. Its output (the proposed folder tree + naming rationale) feeds into 03-plan.

## What this stage does NOT do
- Does not produce the move/rename list (that is 03-plan's job).
- Does not flag individual duplicates for action (03-plan does).
- Does not access the file system.

## Why context.md matters here
The grouping strategy (project vs. type vs. date) and naming convention in context.md are applied directly in steps 2-4 of the Process. If context.md is uncustomized, the output uses sensible defaults — but customizing it is what makes the tool *yours*.
