# 03-plan — Stage Context

## Purpose
Convert the folder design into a concrete, file-by-file cleanup preview. Surface duplicates and junk before anything moves. Define the execution order for approved actions.

## Place in the flow
Third and final stage. Receives the folder tree from 02-design and the tagged inventory from 01-scan. Produces the preview the user approves before execution.

## What this stage does NOT do
- Does not execute moves, renames, or deletions before explicit confirmation.
- Does not re-open the design (if something looks wrong, flag it as a note for the user, don't change the tree).
- Does not change files until the approved execution step.
