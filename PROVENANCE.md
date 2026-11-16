<!--
SPDX-FileCopyrightText: The Khronos Group Inc.
SPDX-License-Identifier: CC-BY-4.0
-->

<!-- REUSE-IgnoreStart -->

# Provenance: glTF-Community

How AI was used in this repository's documentation, and where the full record
is kept. This follows the Khronos AI provenance recommendations.

## Responsibility

- **Responsible person:** Leonard Daly, 3D Formats Tooling TSG chair — directs
  the work, makes the decisions, and reviews and approves everything
  published.
- **Other contributors:** Repository contributors are listed in the Git
  history. This file covers only work done with AI help.

## AI tools

| Tool | Model | Period | Used for |
|---|---|---|---|
| Claude Code 2.1.325 | claude-opus-5-5 | 2026-11-16 – | Drafting and editing repository documentation |

## Sessions

The full transcripts are the primary record. Each is a Claude Code JSONL file
(plus its `<session id>` folder, if any), archived by Khronos.

| Session ID | Dates | Summary | Archive location | SHA-256 |
|---|---|---|---|---|
| `edaffa5f-f7cc-42d9-a0e0-cd6e4d83560b` | 2026-11-16 | Excluded sample assets from the repository; limited license storage to in-file headers and `REUSE.toml`; created this file; set default and vendor ownership in `REUSE.toml`; reordered `README.md` | Archived privately by Khronos | — |

**Redaction:** None needed.

## How the work was done

Leonard Daly asked for each change. Claude drafted the wording and placed it
in the affected files; Leonard reviewed the changes before they were
committed.

## Files

| File or folder | Origin |
|---|---|
| `vendors/README.md` | Human-written, with sections edited by Claude at Leonard Daly's direction (see Decisions) |
| `README.md` | Human-written; sections reordered by Claude at Leonard Daly's direction |
| `LICENSE.md`, `.github/PULL_REQUEST_TEMPLATE.md` | Human-written, with one item edited by Claude at Leonard Daly's direction |
| `PROVENANCE.md` | Drafted by Claude at Leonard Daly's direction |
| `REUSE.toml` | Annotations rewritten by Claude to Leonard Daly's ownership rules (see Decisions) |
| `extensions/TEMPLATE.md` | Human-written; REUSE ignore markers added by Claude |

## Decisions

This section is the decision log. Each entry records the decision, who made
it, and what the AI proposed that was changed or rejected.

| Date | Decision | Made by | AI proposal, if different |
|---|---|---|---|
| 2026-11-16 | Sample models and assets must not be added to this repository. Vendors host them, with a viewer that can display the extension, and link to them from the specification. | Leonard Daly | — (Claude suggested only where in the documentation the rule should go) |
| 2026-11-16 | Copyright and license information is stored only in the file itself or in a `REUSE.toml` annotation; separate `.license` files are not used. | Leonard Daly | — (the documentation previously allowed `.license` files) |
| 2026-11-16 | Create this `PROVENANCE.md` with the decision log in it. | Leonard Daly | Proposed by Claude |
| 2026-11-16 | Default for files without their own notice: CC-BY-4.0, copyright 2026 The Khronos Group Inc. Godot Foundation's notice applies only to files in `extensions/GODOT`. Each `vendors/*.txt` prefix file is owned by the organization it names, except `PREFIX_TEMPLATE.txt`, which is owned by Khronos under the default license. | Leonard Daly | — (`REUSE.toml` previously named Godot Foundation in its own header) |
| 2026-11-16 | In `README.md`, put Overview first and remove the Scope section, moving its statement into Overview. | Leonard Daly | — |
| 2026-11-16 | Give the transcript archive location in this public file as "Archived privately by Khronos", without naming the private archive. | Leonard Daly | Proposed by Claude |

## Commits

Commits made with AI help carry `Co-Authored-By: Claude
<noreply@anthropic.com>`, `AI-Model:` and `AI-Session:` trailers. Commits
before this file was added do not carry these trailers.

<!-- REUSE-IgnoreEnd -->
