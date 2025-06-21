---
date: 2025-06-21
category: [core]
tags: [BaseConfig, config, ClassVar]
description: Base configuration class for ModuBotCore

author:
  - name: Endkind
    link: https://github.com/Endkind
    avatar: https://github.com/Endkind.png
---

# BaseConfig

`BaseConfig` is the base class for all configuration classes in ModuBotCore. It provides automatic runtime type checking for class variables (`ClassVar`).

When you create a subclass of `BaseConfig`, all `ClassVar` attributes are validated to ensure their types match the declared types. This helps catch configuration errors early.

## Supported Types

- Primitive types: `str`, `int`, `float`, `bool`
- Type wrappers, e.g., `Type[SomeClass]`

If a `ClassVar` has an invalid or unsupported value/type, a `TypeError` is raised at class creation time.

## Example

```python
from typing import ClassVar
from ModuBotCore.config import BaseConfig

class MyConfig(BaseConfig):
    NAME: ClassVar[str] = "MyBot"
    ENABLE_FEATURE: ClassVar[bool] = True
    TIMEOUT: ClassVar[int] = 30
```

If you assign a wrong type, e.g. `NAME: ClassVar[str] = 123`, a `TypeError` will be raised immediately.

This ensures your configuration is always type-safe.