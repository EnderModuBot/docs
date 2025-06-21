---
date: 2025-06-21
category: [core]
tags: [module, template, BaseModule]
description: How to create a module for ModuBotCore

author:
  - name: Endkind
    link: https://github.com/Endkind
    avatar: https://github.com/Endkind.png
---

# Module Template

To create a new module for **ModuBotCore**, you need to define a class in `modules/{name}/__init__.py` that inherits from `ModuBotCore.modules.BaseModule`.

`BaseModule` is an abstract class, so you must implement the following methods:

- `on_enable(self)`: Called when the module is enabled.
- `on_disable(self)`: Called when the module is disabled.

You also have access to a logger via `self.logger` for logging within your module.

There are two important `ClassVar` attributes you can set:

- `NAME`: The name of your module (string).
- `ENABLING`: Set to `True` (default) if the module should be enabled on startup. If set to `False`, the module will not be activated automatically.

## Example

```python
from ModuBotCore.modules import BaseModule

class MyModule(BaseModule):
    NAME = "MyModule"
    ENABLING = True

    def on_enable(self):
        self.logger.info("MyModule enabled!")

    def on_disable(self):
        self.logger.info("MyModule disabled!")
```

Place this class in `modules/MyModule/__init__.py` to register your module.