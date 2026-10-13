<!--
SPDX-FileCopyrightText: The Khronos Group Inc.
SPDX-License-Identifier: CC-BY-4.0
-->

# Vendor Extensions

This directory contains vendor prefix registrations for the glTF-Community
repository. A vendor prefix identifies your organization and namespaces your
extensions within the repository.

This repository is the only place to register a glTF 2.0 vendor prefix or to
publish a glTF 2.0 vendor extension. Khronos (`KHR`) and multi-vendor (`EXT`)
extensions are managed by the Khronos 3D Formats Working Group in the
[KhronosGroup/glTF](https://github.com/KhronosGroup/glTF) repository.

## Overview

Contributing an extension requires two things: a registered vendor prefix and
one or more extension specifications placed under that prefix. If you do not yet
have a prefix, you must register one before submitting any extensions.

If your organization already has vendor extensions in the KhronosGroup/glTF
repository, see
[Migrating an existing extension from KhronosGroup/glTF](#migrating-an-existing-extension-from-khronosgroupgltf).

All contributions are made via GitHub Pull Requests (PRs). The first PR
submitted by a GitHub account triggers an automated Contributor License
Agreement (CLA) signing request. The CLA must be completed before that PR can be
merged. Subsequent PRs from the same account do not require re-signing.

## Step 1 — Register a Vendor Prefix

A vendor prefix is a short, unique identifier that represents your organization.
All extension folders and extension names must begin with your prefix.

### Prefix naming rules

- All capital letters (e.g., `ACME`)
- Must not conflict with any prefix already registered in this folder
- Must not conflict with any prefix in the
  [reserved legacy prefix list](./LEGACY_PREFIXES.md), unless you are the
  organization that holds that prefix (see
  [Registering a reserved legacy prefix](#registering-a-reserved-legacy-prefix))
- Must comply with Khronos naming policy
    - The prefixes `KHR` and `EXT` are reserved for the Khronos 3D Formats
      Working Group and cannot be registered here. To propose a `KHR` or `EXT`
      extension, create an issue in the
      [glTF repository](https://github.com/KhronosGroup/glTF/issues).
- The term `PREFIX` as a standalone item, as part of `PREFIX.txt` or in
  `PREFIX_extension_name` is the prefix string for your organization. It is
  always an uppercase string.

### How to register

1. Copy the template file `PREFIX_TEMPLATE.txt` from the vendors folder and
   rename it `PREFIX.txt`. The filename must match the `Prefix` value exactly,
   including case (e.g., `ACME.txt`).

2. Fill in the four required fields using the format `Name: value`:

    ```
    SPDX-FileCopyrightText: ACME Inc.
    Prefix: ACME
    Owner: Acme Corporation
    Contact: https://www.example.com/gltf
    ```

    - **SPDX-FileCopyrightText** — the copyright holder of this registration
      file, normally your organization
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

### Registering a reserved legacy prefix

Prefixes registered in the KhronosGroup/glTF repository are listed in
[LEGACY_PREFIXES.md](./LEGACY_PREFIXES.md). A reserved prefix can only be
registered here by the organization that currently controls it.

To register a reserved prefix, follow the steps above. In the PR description,
also include:

- a link to the original registration issue or PR in KhronosGroup/glTF (shown
  in the `Request` column of the legacy list), and
- if your organization's name differs from the one in the legacy list (for
  example, after a rename or acquisition), a short explanation of how your
  organization controls the prefix.

Maintainers may ask for confirmation from the contact listed in the legacy
table before approving.

## Step 2 — Add an Extension

Once your prefix is registered, you may submit extensions under it. Start from
the [extension template](../extensions/TEMPLATE.md).

### Naming conventions

- Extension folder: `extensions/PREFIX/PREFIX_extension_name/` — prefix in all
  caps, remainder in all lowercase with words separated by underscores
- Extension name follows the same pattern: `PREFIX_extension_name`
- Documentation filenames are uppercase with a lowercase `.md` extension
  (e.g., `README.md`, `LICENSE.md`)

Example: an extension named `smooth_joints` from vendor `ACME` would live at:

```
extensions/ACME/ACME_smooth_joints/
```

### PR rules

- A single PR may contain **multiple extensions** provided that **every
  extension in the PR is new**. Do not mix new extensions and updates in the
  same PR.
- A PR that **updates** an existing extension must contain **only that one
  extension**.
- PRs that modify extensions not owned by your organization will be denied.
  Contact the extension's copyright owner directly for any changes to their
  work.
- A PR that adds an extension must also add a row for it to the
  [extension index](../extensions/README.md).

### Extension folder contents

At minimum, each extension folder must contain a specification document. A
`README.md` is the standard choice. A typical layout is:

```
extensions/ACME/
    README.md                     # Optional vendor index (see extensions/GODOT/README.md)
    ACME_smooth_joints/
        README.md                 # Required: extension specification
        LICENSE.md                # Optional: folder-level license (see below)
        schema/
            node.ACME_smooth_joints.schema.json
            node.ACME_smooth_joints.schema.json.license
        figures/                  # Optional: images used by the specification
        examples/                 # Optional: example assets
```

### Copyright Notice and License Template

We use a short license in each file consisting of just the copyright statement
and the SPDX license identifier of the license applying to that file, rather
than including the full license text in each file.

The full license text for each license used must be included in the
[LICENSES](../LICENSES) directory. If the license you choose is not already
there, add its text in the same PR as `LICENSES/<SPDX-identifier>.txt` (for
example, by running `reuse download <SPDX-identifier>`). The
[REUSE](https://reuse.software/) tool is used in CI to verify that all files in
this repository are appropriately licensed.

For example, this file uses the license:

    SPDX-FileCopyrightText: The Khronos Group Inc.
    SPDX-License-Identifier: CC-BY-4.0

License and Copyright requirements apply to every file contributed to this
repository. The CLA grants Khronos the necessary permissions to redistribute
your contribution; ensure your chosen license is consistent with the CLA terms.

### Licensing files that cannot carry a header

JSON schema files, images, and binary files cannot contain an SPDX comment.
For each such file, use one of the following:

- A sidecar file named `<filename>.license` next to the file, containing the
  two SPDX lines. For example,
  `node.ACME_smooth_joints.schema.json.license`.
- An `[[annotations]]` entry in [REUSE.toml](../REUSE.toml) covering your
  files, for example `path = ["extensions/ACME/**"]`.

Without one of these, the REUSE compliance check fails.

### Folder-level license

You may place a `LICENSE.md` at the root of your extension folder. This file can
serve two purposes:

- **Explicit coverage** — it states the license that applies to all files in the
  folder
- **Default coverage** — it provides a fallback license for any file in the
  folder that does not carry its own license statement

A `LICENSE.md` is for human readers. The REUSE check still requires each file
to be covered by a header, a `.license` sidecar, or a `REUSE.toml` annotation.

### Intellectual Property (IP) Status

A statement of the terms under which the extension may be used and implemented,
or how to contact the submitting organization for details. Royalty-free terms
are normal practice for glTF extensions.

### Trademark notices

If any material in the submitting document is trademarked, it should be so
indicated.

### Checking your PR locally

CI runs two checks on every PR. Run them before you submit:

- `pre-commit run --all-files` checks file formatting (UTF-8 without BOM, LF
  line endings, no trailing whitespace) and internal Markdown links. See
  [.pre-commit-config.yaml](../.pre-commit-config.yaml) for setup.
- `reuse lint` checks that every file has copyright and license information.

## Migrating an existing extension from KhronosGroup/glTF

glTF 2.0 vendor extensions currently in
[KhronosGroup/glTF/extensions/2.0/Vendor](https://github.com/KhronosGroup/glTF/tree/main/extensions/2.0/Vendor)
must be moved to this repository by the organization that owns them. Khronos
does not move them. The transition period ends **31 December 2026**; this date
may be extended. Vendor extensions that have not been moved will be archived and
removed from the KhronosGroup/glTF repository some time after the transition
period ends.

This does not apply to `KHR` or `EXT` extensions, or to any glTF 1.0
extension. Those remain in KhronosGroup/glTF.

1. **Register your prefix** in this repository (Step 1). If your prefix is in
   the [reserved legacy prefix list](./LEGACY_PREFIXES.md), follow
   [Registering a reserved legacy prefix](#registering-a-reserved-legacy-prefix).
2. **Copy each extension folder.** Copy
   `extensions/2.0/Vendor/PREFIX_extension_name/` from KhronosGroup/glTF to
   `extensions/PREFIX/PREFIX_extension_name/` here. Preserving Git history
   (for example, with `git filter-repo`) is welcome but not required.
3. **Add copyright and license information.** In KhronosGroup/glTF, vendor
   extensions are marked with an undetermined license (`LicenseRef-TBD`). You
   must now state the copyright holder and license for every file, as
   described in Step 2. Add `.license` sidecars or a `REUSE.toml` annotation
   for JSON schemas and images.
4. **Complete the specification.** Add IP Status and trademark information if
   missing. Fix any links that pointed to other files in KhronosGroup/glTF.
5. **Update the index.** Add a row for each extension to the
   [extension index](../extensions/README.md).
6. **Open one PR** with all of your migrated extensions. Extensions being
   migrated count as new extensions in this repository, so they can all go in
   one PR.
7. **Notify the glTF repository.** After your PR is merged, open an issue or PR
   in KhronosGroup/glTF so that the old extension folders are replaced with a
   link to their new location. Do not delete the folders there.

## Step 3 — Summary Checklist

**Registering a prefix**

- [ ] Copy `PREFIX_TEMPLATE.txt` from the vendors folder and rename to
      `YOURPREFIX.txt`
- [ ] Fill in `SPDX-FileCopyrightText`, `Prefix`, `Owner`, and `Contact` fields
- [ ] Prefix is not registered here and is not in
      [LEGACY_PREFIXES.md](./LEGACY_PREFIXES.md) (or you are its legacy holder,
      and the PR description links to the original request)
- [ ] Open a PR with only this file
- [ ] Complete [CLA](../CONTRIBUTING.md#contributor-license-agreement) signing if this is your first PR to this repository
      (you will be automatically prompted if you need to sign the CLA)
- [ ] Await maintainer approval

**Submitting an extension**

- [ ] Prefix is already registered
- [ ] Folder named `extensions/PREFIX/PREFIX_extension_name/` (all caps prefix,
      lowercase remainder)
- [ ] PR contains only new extensions, or only a single extension update
- [ ] Specification document present (e.g., `README.md`), based on the
      [extension template](../extensions/TEMPLATE.md)
- [ ] License and Copyright notices are present on every file (headers,
      `.license` sidecars, or `REUSE.toml`)
- [ ] Text of every license used is present in `LICENSES/`
- [ ] Intellectual Property (IP) Status present
- [ ] All trademarks identified
- [ ] Row added to [extensions/README.md](../extensions/README.md)
- [ ] `pre-commit run --all-files` and `reuse lint` pass

**Migrating from KhronosGroup/glTF** (in addition to the above)

- [ ] Copyright holder and license chosen for every file
- [ ] Links to files in KhronosGroup/glTF updated or removed
- [ ] After merge, KhronosGroup/glTF notified so the old folder can be replaced
      with a link
