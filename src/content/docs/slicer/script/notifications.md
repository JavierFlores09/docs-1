---
title: Notifications
description: Overview of the notification (toast) API.
tableOfContents: false
---

You can display toast messages in the UI with the scripting API. It is exposed through the `ScriptContext` as `context.notification`.

Notifications are intended for lightweight feedback (state changes, errors, confirmations).

```js
context.notification.info("my_script/started");
context.notification.success("my_script/done");
context.notification.warning("my_script/warning");
context.notification.error("my_script/failed", {
    msgArgs: [/* ... */],
    description: "my_script/failed/desc",
    descriptionArgs: [/* ... */],
    duration: 1000 * 10, // 10 seconds
});
```
