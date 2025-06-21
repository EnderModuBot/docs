---
date: 2025-06-21
category: [core]
tags: [helpers, str2bool]
description: Overview of helpers in ModuBotCore

author:
  - name: Endkind
    link: https://github.com/Endkind
    avatar: https://github.com/Endkind.png
---

# Helpers

ModuBotCore provides useful helper functions in `ModuBotCore.helpers`.

## str2bool

`str2bool(value: str) -> bool`

Converts a string to a boolean value. Useful for parsing configuration values or user input.

### Example

```python
from ModuBotCore.helpers import str2bool

print(str2bool("true"))   # True
print(str2bool("False"))  # False
```