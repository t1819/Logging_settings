# Logging settings

## How to use logging in python:
---
* Following steps are used in the all python files.
```python
#Default logging setting
logging.config.fileConfig("log.ini")
logger = logging.getLogger('sLogger')

logger.info('information alerts')
logger.warning('warning alerts')
logger.error('error alerts')

```

* Below settings will be store into a file named **log.ini**.
```python
[loggers]
keys=root,sLogger

[handlers]
keys=consoleHandler,fileHandler

[formatters]
keys=fileFormatter,consoleFormatter

[logger_root]
level=DEBUG
handlers=consoleHandler

[logger_sLogger]
level=DEBUG
handlers=consoleHandler,fileHandler
qualname=sLogger
propagate=0

[handler_consoleHandler]
class=StreamHandler
formatter=consoleFormatter
args=(sys.stdout,)

[handler_fileHandler]
class=FileHandler
level=DEBUG
formatter=fileFormatter
args=('log\\debug.log',)

[formatter_fileFormatter]
format=[%(asctime)s] %(levelname)s %(name)s %(module)s %(funcName)s "%(message)s"
datefmt=

[formatter_consoleFormatter]
format=[%(asctime)s] %(levelname)s %(name)s %(module)s %(funcName)s "%(message)s"
datefmt=
```


* log output sample:
```python
[2020-05-21 01:05:10,983] ERROR root project_creation basic_config error in basic config file.
```