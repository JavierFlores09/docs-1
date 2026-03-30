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

slicer allows you to temporarily adjust certain aspects of its behavior using URL parameters, such as automatically loading a file or importing a script on startup.
This is useful for embedding slicer into outside web applications and allowing users to automatically source arbitrary files.

You can:

- automatically load a file using the `url` parameter, e.g. `https://slicer.run?url=https://example.com/my.jar`.
- automatically open a file from your loaded ZIP/JAR file using the `file` parameter, e.g. `https://slicer.run?url=https://example.com/my.jar&file=my.jar/path/inside/jar/MyClass.class`.
  - You can also create the shareable URL directly in slicer by right-clicking the tab of an open file and selecting `Copy shareable link`!
- automatically load a mapping file using the `mapping` parameter, e.g. `https://slicer.run?url=https://example.com/my.jar&mapping=https://example.com/my.tiny`.
- automatically import a script using the `script` parameter, e.g. `https://slicer.run?script=https://example.com/my-slicer-script/index.js`.

:::tip

A notable use case is _decompiling the Minecraft client/server_, you can use a URL like `https://slicer.run?url=https://piston-data.mojang.com/v1/objects/ba2df812c2d12e0219c489c4cd9a5e1f0760f5bd/client.jar` to automatically load the Minecraft client JAR into slicer and start decompiling it, which is pretty neat!

You can view a table of deobfuscated Minecraft versions on the [minecraft.katana-project.org](https://minecraft.katana-project.org) website, which provides links to slicer with the appropriate URL parameters already set up for each version.

:::

## Sharing a file

source URL: `https://raw.githubusercontent.com/GenericException/SkidSuite/refs/heads/master/obf/obf-sample-test.jar`<br>
slicer URL: `https://slicer.run?url=https://raw.githubusercontent.com/GenericException/SkidSuite/refs/heads/master/obf/obf-sample-test.jar`

If you need a space for uploading files to share, [pastes.dev](https://pastes.dev) and curl is a safe choice:

```bash
echo "https://api.pastes.dev/$(curl --progress-bar --data-binary @./path/to/file.jar -XPOST https://api.pastes.dev/post | jq -r '.key')"
```

### Buttons

A set of stylized buttons is provided for linking to slicer, akin to GitHub repository badges or the Vercel deploy button.

| Button                                               | URL                                               | Markdown                                                                             |
| ---------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------------------------------------------ |
| ![](https://slicer.run/button-disassemble-small.svg) | `https://slicer.run/button-disassemble-small.svg` | `[![](https://slicer.run/button-disassemble-small.svg)](https://slicer.run?url=...)` |
| ![](https://slicer.run/button-disassemble-large.svg) | `https://slicer.run/button-disassemble-large.svg` | `[![](https://slicer.run/button-disassemble-large.svg)](https://slicer.run?url=...)` |
| ![](https://slicer.run/button-decompile-small.svg)   | `https://slicer.run/button-decompile-small.svg`   | `[![](https://slicer.run/button-decompile-small.svg)](https://slicer.run?url=...)`   |
| ![](https://slicer.run/button-decompile-large.svg)   | `https://slicer.run/button-decompile-large.svg`   | `[![](https://slicer.run/button-decompile-large.svg)](https://slicer.run?url=...)`   |
