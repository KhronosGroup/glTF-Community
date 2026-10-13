<!--
SPDX-FileCopyrightText: The Khronos Group Inc.
SPDX-License-Identifier: CC-BY-4.0
-->

# Contributing to KhronosGroup/glTF-Community

Contributions to the glTF-Community repository are welcome.

This repository accepts glTF 2.0 vendor extensions and vendor prefix
registrations, including vendor extensions being migrated from
[KhronosGroup/glTF](https://github.com/KhronosGroup/glTF). Khronos (`KHR_`) and
multi-vendor (`EXT_`) extensions are managed by the Khronos 3D Formats Working
Group in KhronosGroup/glTF and are not accepted here.

All contributions must be submitted via a GitHub Pull Request (PR). Extensions
are placed in the `extensions/PREFIX` folder, where `PREFIX` is the all-capitals
text string registered to your organization.

The first PR submitted by a GitHub account triggers an automated [Contributor
License Agreement](#contributor-license-agreement) signing
request. The CLA must be completed before that PR can be merged.

## Vendor Prefix

Before submitting an extension, your organization must have a registered vendor
prefix. For full instructions on registering a prefix, submitting extensions,
and migrating extensions from KhronosGroup/glTF, see
[vendors/README.md](./vendors/README.md). Prefixes registered in
KhronosGroup/glTF are reserved for their current holders; see
[vendors/LEGACY_PREFIXES.md](./vendors/LEGACY_PREFIXES.md).

New extension specifications should start from the
[extension template](./extensions/TEMPLATE.md).

## Naming and Licensing Conventions

Extension folders, extension names, and documentation files follow specific
naming conventions. Each extension must include a copyright notice and licensing
information, and license terms must be consistent with the CLA. For details on
both naming and licensing requirements, see
[vendors/README.md](./vendors/README.md).

PRs that modify extensions not owned by your organization will be denied.
Contact the extension's copyright owner directly for any changes to their work.

## Contributor License Agreement

When you submit a pull request to KhronosGroup/glTF-Community for the first
time, you must execute the [Khronos Community Hosting Contributor License
Agreement (CLA)](./CLA.md). The CLA confirms that you own your work and are
granting Khronos the necessary permissions to redistribute it in this
repository. Subsequent PRs from the same account do not require re-signing.

## AI-Assisted Contributions

By submitting a Contribution to this repository, you additionally represent
that, to the extent any of Your Contributions were developed with the
assistance of artificial intelligence tools or AI-generated code, You have
exercised sufficient review, judgment, and creative direction over such tools
and resulting material to reasonably consider it Your original creation, and
You are not aware of any third-party license, intellectual property claim, or
other restriction arising from such use that is associated with any part of
Your Contribution or use thereof.
