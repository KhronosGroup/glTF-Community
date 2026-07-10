<!--
SPDX-FileCopyrightText: The Khronos Group Inc.
SPDX-License-Identifier: CC-BY-4.0
-->

# Vendor Extensions

This directory contains vendor prefix registrations for the glTF-Community
repository. A vendor prefix identifies your organization and namespaces your
extensions within the repository.

## Overview

Contributing an extension requires two things: a registered vendor prefix and
one or more extension specifications placed under that prefix. If you do not yet
have a prefix, you must register one before submitting any extensions.

All contributions are made via GitHub Pull Requests (PRs). The first PR
submitted by a GitHub account triggers an automated Contributor License
Agreement (CLA) signing request. The CLA must be completed before that PR can be
merged. Subsequent PRs from the same account do not require re-signing.

## Step 1 — Register a Vendor Prefix

A vendor prefix is a short, unique identifier that represents your organization.
All extension folders and extension names must begin with your prefix.

### Prefix naming rules

- All capital letters (e.g., `ACME`)
- Must not conflict with any prefix already registered in `./vendors/`
- Must comply with Khronos naming policy
    - The prefix `KHR` is reserved for glTF Specification Ratified Extensions.
      Create an issue in the [glTF repo](https://github.com/KhronosGroup/glTF/issues)
      for further handling of those types of extensions.
    - The prefix `EXT` is reserved. Create an issue if you feel that you need
      to use `EXT` as a prefix.
- The term `PREFIX` as a standalone item, as part of `PREFIX.txt` or in
  `PREFIX_extension_name` is the prefix string for your organization. It is
  always an uppercase string.

### How to register

1. Copy the template file `PREFIX_TEMPLATE.txt` from the vendors folder and
   rename it `PREFIX.txt`.

2. Fill in the three required fields using the format `Name: value`:

    ```
    Prefix: ACME
    Owner: Acme Corporation
    Contact: https://www.example.com/gltf
    ```

    - **Prefix** — your requested prefix
    - **Owner** — the full legal name of your organization
    - **Contact** — a URL is preferred; an email address is acceptable

3. Place the completed file in the vendors folder as `PREFIX.txt`.

4. Open a PR containing only this file. Do not include any extensions in a
   prefix registration PR.

5. If this is your first PR to this repository, complete the CLA
   signing when the automated request is generated.

6. If there are no naming conflicts or policy issues, the PR will be reviewed
   and approved by a Khronos maintainer.

An organization may hold more than one prefix. Each prefix requires its own
registration PR following the same process.

## Step 2 — Add an Extension

Once your prefix is registered, you may submit extensions under it.

### Naming conventions

- Extension folder: `extensions/PREFIX/PREFIX_extension_name/` — prefix in all
  caps, remainder in all lowercase with words separated by underscores
- Extension name follows the same pattern: `PREFIX_extension_name`
- Documentation files: uppercase filename with `.md` extension (e.g.,
  `README.MD` → `README.md`)

Example: an extension named `smooth_joints` from vendor `ACME` would live at:

`extensions/ACME/ACME_smooth_joints/`

### PR rules

- A single PR may contain **multiple extensions** provided that **every
  extension in the PR is new**. Do not mix new extensions and updates in the
  same PR.
- A PR that **updates** an existing extension must contain **only that one
  extension**.
- PRs that modify extensions not owned by your organization will be denied.
  Contact the extension's copyright owner directly for any changes to their
  work.

### Extension folder structure

At minimum, each extension folder must contain a specification document. A
`README.md` is the standard choice:

```
extensions/ACME/ACME_smooth_joints/
    README.md        # Extension specification
    LICENSE.md       # Optional folder-level license (see below)
```

### Copyright Notice and License Template

We use a short license in each file consisting of just the copyright statement
and the SPDX license identifier of the license applying to that file, rather
than including the full license text in each file.

The full license text for each license used must be included in the LICENSES
directory. The REUSE tool is used in CI to verify that all files in this
repository are appropriately licensed.

For example, this file uses the license:

    SPDX-FileCopyrightText: The Khronos Group Inc.
    SPDX-License-Identifier: CC-BY-4.0

License and Copyright requirements apply to every file contributed to this
repository. The CLA grants Khronos the necessary permissions to redistribute
your contribution; ensure your chosen license is consistent with the CLA terms.

### Folder-level license

You may place a `LICENSE.md` at the root of your extension folder. This file can
serve two purposes:

- **Explicit coverage** — it states the license that applies to all files in the
  folder
- **Default coverage** — it provides a fallback license for any file in the
  folder that does not carry its own license statement

### Intellectual Property (IP) Status

A statement of the terms under which the extension may be used and implemented,
or how to contact the submitting organization for details. Royalty-free terms
are normal practice for glTF extensions.

### Trademark notices

If any material in the submitting document is trademarked, it should be so
indicated.

## Step 3 — Summary Checklist

**Registering a prefix**

- [ ] Copy `PREFIX_TEMPLATE.txt` from the vendors folder and rename to
      `YOURPREFIX.txt`
- [ ] Fill in `Prefix`, `Owner`, and `Contact` fields
- [ ] Open a PR with only this file
- [ ] Complete CLA signing if this is your first PR to this
      repository (you will be automatically prompted if you need to sign the CLA)
- [ ] Await maintainer approval

**Submitting an extension**

- [ ] Prefix is already registered
- [ ] Folder named `extensions/PREFIX/PREFIX_extension_name/` (all caps prefix,
      lowercase remainder)
- [ ] PR contains only new extensions, or only a single extension update
- [ ] Specification document present (e.g., `README.md`)
- [ ] License and Copyright stated and present, with per-file notices included
- [ ] Intellectual Property (IP) Status present
- [ ] All trademarks identified
