# Logging settings

## How to use logging in python:
---
* Setting will be store into a file named **log.ini**.
* Following steps are used in the all python files.
```python
#Default logging setting
logging.config.fileConfig("log.ini")
logger = logging.getLogger('sLogger')

logger.info('information alerts')
logger.warning('warning alerts')
logger.error('error alerts')

```

