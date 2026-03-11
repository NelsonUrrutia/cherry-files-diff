# 🍒 Cherry Diff Files (CDF) 🔎

> Cherry Diff Files is a local Git tool that helps you cherry-pick only the specific lines or code blocks you want from a source branch into a target branch, so you can avoid conflicts, review the result, and commit a clean, minimal change set.

## Overview

Cherry Diff Files is a local Git helper for transferring selected blocks/lines of code from a source branch file into a target branch file.

## Problem It Solves

Standard merges/cherry-picks often bring along unwanted changes or create conflicts. CDF focuses on moving only the intended parts of files between branches.

## Key Features

- Two-branch file comparison: source (has changes) vs target (receives changes)
- Side-by-side diff view for each file
- Selective block/line transfer (copy/move chosen hunks into target)
- In-place editing on the target result when block transfer is not enough
- Result review before committing
- Batch commit: edit multiple files, then create one commit for the group
- File creation: if a file is missing on target, create it by default

## Supported Content

- Text-based files, including: JavaScript, JSON, HTML, CSS, Python, Markdown (and generally any text file)

## Workflow (High Level)

1. Choose source branch and target branch
2. Compare a file in both branches (diff view)
3. Select and transfer specific lines/blocks into the target version (and/or manually edit)
4. CDF stores the edited content, switches to the target branch, and applies changes
5. Review the final result and commit (locally)

## Implementation Notes (From Spec)

- VCS: Git only
- Language: Python
- Merge approach: uses essential Git commands (mentions `git merge`), with changes applied as selected blocks rather than full-file merges

## MVP Roadmap (Sprints)

1. Branch comparison + file support (diff UI, source/target selection)
2. Selective line/block editing + in-place editing
3. Commit flow + result display/review
4. Batch commit strategy + Git integration + basic error handling/logging
5. UX polish (robust, intuitive UI; clean layout)
