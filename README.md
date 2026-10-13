<!--
SPDX-FileCopyrightText: The Khronos Group Inc.
SPDX-License-Identifier: CC-BY-4.0
-->

# glTF-Community

Welcome! This repository provides the glTF community a place to publish
extensions they have created, gain visibility across the ecosystem, and connect
with potential collaborators.

This repository is also a proving ground: extensions that demonstrate community
adoption here are strong candidates for later submission to the main glTF
repository, where the Khronos 3D Formats Working Group can consider them for the
glTF standard.

## Where do glTF extensions go?

| Extension type | Repository |
| :------------- | :--------- |
| glTF 2.0 vendor extensions (`PREFIX_extension_name`), new or migrated | **This repository** |
| glTF 2.0 vendor prefix registration | **This repository** — see [vendors/README.md](./vendors/README.md) |
| Khronos extensions (`KHR_`) | [KhronosGroup/glTF](https://github.com/KhronosGroup/glTF) |
| Multi-vendor extensions (`EXT_`) | [KhronosGroup/glTF](https://github.com/KhronosGroup/glTF) |
| Any glTF 1.0 extension | [KhronosGroup/glTF](https://github.com/KhronosGroup/glTF) |

glTF 2.0 vendor extensions previously hosted in
[KhronosGroup/glTF](https://github.com/KhronosGroup/glTF/tree/main/extensions/2.0/Vendor)
are being moved here by their owners. The transition period ends 31 December
2026; this date may be extended. See
[Migrating an existing extension](./vendors/README.md#migrating-an-existing-extension-from-khronosgroupgltf).

Prefixes registered in KhronosGroup/glTF remain reserved for their current
holders; see [vendors/LEGACY_PREFIXES.md](./vendors/LEGACY_PREFIXES.md).

## Overview

**How this repository relates to the main glTF repository:**

- The [main glTF repository](https://github.com/KhronosGroup/glTF) is where the
  Khronos 3D Formats Working Group develops specifications on the formal glTF
  roadmap, under the protections of the Khronos IP Framework. If you want to
  contribute an idea or draft specification for consideration by the working
  group, that is the place to go.

- This Community repository is open to all. It provides community visibility
  with no direct Khronos working group involvement — though it is watched with
  interest as a valuable signal of community activity and requirements.

Because extensions here are not developed under the Khronos IP Framework, please
review each extension's licensing terms before implementing or using it — see
the individual extension directories and `LICENSE.md` for details.

## Extensions

**[Browse available extensions →](./extensions/README.md)**

Extensions are organized by vendor prefix under `extensions/`. Each extension
includes its own specification document and license information.

## Contributing

Community contributions are welcome. Before submitting, please review:

- **[CONTRIBUTING.md](./CONTRIBUTING.md)** — how to contribute an extension or
  other material
- **[LICENSE.md](./LICENSE.md)** — licenses in use across this repository
- **[COPYING.md](./COPYING.md)** — guidance on reusing or copying files and
  extensions
- **[vendors/README.md](./vendors/README.md)** — how to request a new vendor
  prefix, add an extension, or migrate an extension from KhronosGroup/glTF
- **[extensions/TEMPLATE.md](./extensions/TEMPLATE.md)** — template for a new
  extension specification

## Scope

This repository contains glTF 2.0 vendor extensions only. `KHR_` and `EXT_`
extensions, and glTF 1.0 extensions, are not accepted here.
