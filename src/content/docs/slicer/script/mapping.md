---
title: Mapping
description: Overview of the mapping manipulation API.
tableOfContents: false
---

The mapping API allows you to manipulate and export obfuscation mappings that slicer is currently holding onto and load new ones.

For further context on what mappings are, check out the [mapping documentation](/slicer/reference/analysis/mapping).

```js
await context.mapping.load(data, dst); // loads mappings from the provided data (string), optionally from a specific namespace (dst)
await context.mapping.export(format); // exports the currently loaded mappings in a specified format (e.g. "tiny_v1", "tiny_v2, "tsrg", "proguard", etc.); returns the exported data as a string
context.mapping.clear(); // clears the currently loaded mappings, reverting all names to their original state
context.mapping.size(); // gets the number of currently loaded class mappings
```
