<!--
SPDX-FileCopyrightText: The Khronos Group Inc.
SPDX-License-Identifier: CC-BY-4.0
-->

<!--
See vendors/README.md for the full instructions. KHR_ and EXT_ extensions
belong in https://github.com/KhronosGroup/glTF and are not accepted here.
-->

## Type of PR

- [ ] Vendor prefix registration (only the `vendors/PREFIX.txt` file)
- [ ] Registration of a reserved legacy prefix (link to the original request:
      )
- [ ] New extension(s)
- [ ] Update to one existing extension
- [ ] Extension(s) migrated from KhronosGroup/glTF
- [ ] Other (repository documentation or tooling)

## Checklist

- [ ] The prefix is registered to my organization (or this PR registers it)
- [ ] Folder is `extensions/PREFIX/PREFIX_extension_name/`
- [ ] Every file has copyright and license information (header, `.license`
      sidecar, or `REUSE.toml` annotation), and every license used is in
      `LICENSES/`
- [ ] Specification includes License, IP Status, and Trademark information
- [ ] Each new extension has a row in `extensions/README.md`
- [ ] `pre-commit run --all-files` and `reuse lint` pass locally
