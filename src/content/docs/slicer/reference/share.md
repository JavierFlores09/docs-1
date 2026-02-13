---
title: Sharing
description: Reference of sharing capabilities.
---

<style>
  table td {
    vertical-align: middle;
  }

  /* force first column to max badge width */
  table tr > :first-child {
    width: 200px;
  }
</style>

slicer allows you to read files from an HTTP server (with an appropriate CORS setup) using the `url` search parameter.
This is useful for embedding slicer into outside web applications and allowing users to automatically source arbitrary files.

A notable use case is _decompiling the Minecraft client/server_, you can use a URL like `https://slicer.run?url=https://piston-data.mojang.com/v1/objects/ba2df812c2d12e0219c489c4cd9a5e1f0760f5bd/client.jar` to automatically load the Minecraft client JAR into slicer and start decompiling it, which is pretty neat!

:::tip

You can view a table of deobfuscated Minecraft versions on the [minecraft.katana-project.org](https://minecraft.katana-project.org) website, which provides links to slicer with the appropriate URL parameter already set up for each version.

:::

## Example

source URL: `https://raw.githubusercontent.com/GenericException/SkidSuite/refs/heads/master/obf/obf-sample-test.jar`<br>
slicer URL: `https://slicer.run?url=https://raw.githubusercontent.com/GenericException/SkidSuite/refs/heads/master/obf/obf-sample-test.jar`

If you need a space for uploading files to share, [pastes.dev](https://pastes.dev) and curl is a safe choice:

```bash
echo "https://api.pastes.dev/$(curl --progress-bar --data-binary @./path/to/file.jar -XPOST https://api.pastes.dev/post | jq -r '.key')"
```

## Buttons

A set of stylized buttons is provided for linking to slicer, akin to GitHub repository badges or the Vercel deploy button.

| Button                                               | URL                                               | Markdown                                                                             |
| ---------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------------------------------------------ |
| ![](https://slicer.run/button-disassemble-small.svg) | `https://slicer.run/button-disassemble-small.svg` | `[![](https://slicer.run/button-disassemble-small.svg)](https://slicer.run?url=...)` |
| ![](https://slicer.run/button-disassemble-large.svg) | `https://slicer.run/button-disassemble-large.svg` | `[![](https://slicer.run/button-disassemble-large.svg)](https://slicer.run?url=...)` |
| ![](https://slicer.run/button-decompile-small.svg)   | `https://slicer.run/button-decompile-small.svg`   | `[![](https://slicer.run/button-decompile-small.svg)](https://slicer.run?url=...)`   |
| ![](https://slicer.run/button-decompile-large.svg)   | `https://slicer.run/button-decompile-large.svg`   | `[![](https://slicer.run/button-decompile-large.svg)](https://slicer.run?url=...)`   |
