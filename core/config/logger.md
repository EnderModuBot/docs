---
date: 2025-06-21
category: [core]
tags: [logger, config, BaseConfig]
description: Logger configuration for ModuBotCore

author:
  - name: Endkind
    link: https://github.com/Endkind
    avatar: https://github.com/Endkind.png
---

# Logger Configuration

ModuBotCore provides a ready-to-use logger configuration via the `LoggerConfig` class.

## LoggerConfig

`LoggerConfig` inherits from `BaseConfig` and is a frozen dataclass. It defines the following class variables:

- `LEVEL`: Logging level (e.g., DEBUG, INFO). Defaults to the `LOG_LEVEL` environment variable or `'INFO'`.
- `FORMAT`: Format string for log messages. Default: `"[%(asctime)s - %(levelname)s - %(name)s]: %(message)s"`
- `DATEFMT`: Format string for timestamps in log messages. Default: `"%m/%d/%Y %H:%M:%S"`

You can use or override these settings in your own configuration if needed.

## Example

```python
from ModuBotCore.config import LoggerConfig

print(LoggerConfig.LEVEL)    # e.g., 'INFO'
print(LoggerConfig.FORMAT)   # e.g., '[%(asctime)s - %(levelname)s - %(name)s]: %(message)s'
print(LoggerConfig.DATEFMT)  # e.g., '%m/%d/%Y %H:%M:%S'
```

These settings control the log output format and level for all logging in ModuBotCore.