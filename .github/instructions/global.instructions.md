---
applyTo: "**"
---

# Global Instructions

These rules apply to every agent working anywhere in this repository.

## Comments in Source Files

Document exported symbols and non-trivial fields with JSDoc that says
what they are and how to use them: purpose, inputs, outputs, units,
allowed values, invariants. Brief inline comments only where the
logic is non-obvious.

Do not write rationale or history comments (why a shape was chosen,
what a refactor did), comments that restate what the code literally
does, or stub placeholders. Apply the removal test: cover the comment
and re-read the code; if the reader loses nothing but justification,
delete the comment. Scope each comment to its own symbol -- what it
is, never what it is not or what a neighbor does.

## Plan-Only Names

Never embed plan or work-item names -- phases, milestones, tickets --
in code, identifiers, strings, or docs. Name things for the behavior
or domain concept they represent.

## ASCII-Only Text

Use only keyboard-typable ASCII in code comments, markdown, and any
string a person may read. Substitute `->` for arrows, `--` for em
dashes, `-` for bullets, `[x]`/`[ok]` for checkmarks.

## Temporary Files and Deletion Discipline

Never run `rm -rf`, `rm -r`, or any recursive or wildcard deletion.
Create temporary files outside the repo tree, track each by exact
path, and delete each individually when done. Never delete a file you
did not create in the current session.

## After Making Changes

There is no local check tooling here. Run `git diff --check`, keep
the manifest `files` list consistent with the tree, and report what
a consuming application must verify.

## Report Every Issue With a Proposed Time

A problem you notice but do not fix gets one line saying what it is
and a proposed slot: fix now, fold into named work, its own change
later, or leave permanently with the reason. A finding that
undermines your own change is a blocker: stop and resolve or report
it, never record it and proceed.

## Broad View Before Acting

Before a change touching more than one tile, module, or doc page,
read the involved files end to end and name the invariants the
change must preserve -- shared modifier namespaces, doc/manifest
pairing, the served-description stability rule. Leave the code more
coherent than found.
