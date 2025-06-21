---
date: 2025-06-21
category: [core]
tags: [core, ModuBotCore, customization]
description: Usage and customization of ModuBotCore

author:
  - name: Endkind
    link: https://github.com/Endkind
    avatar: https://github.com/Endkind.png
---

# ModuBotCore Usage

You can use the default core directly:

```python
from ModuBotCore import ModuBotCore

ModuBotCore().run()
```

Or you can customize it by creating your own class that inherits from `ModuBotCore`.

You have access to the logger via `self.logger`.

To start and stop the bot, use the `run()` and `stop()` methods.

## Important ClassVars

```python
NAME: ClassVar[str] = "ModuBotCore"
VERSION: ClassVar[str] = "0.0.1"
LOGGER_CONFIG: ClassVar[Type[LoggerConfig]] = LoggerConfig
MODULE_BASE_CLASS: ClassVar[Type[BaseModule]] = BaseModule
```

## Example: Custom Core

```python
from ModuBotCore import ModuBotCore
from ModuBotCore.config import LoggerConfig

class MyLoggerConfig(LoggerConfig):
    LEVEL = "DEBUG"

class MyBot(ModuBotCore):
    NAME = "MyCustomBot"
    VERSION = "1.2.3"
    LOGGER_CONFIG = MyLoggerConfig

bot = MyBot()
bot.run()
```

This allows you to extend and modify the core functionality as needed.