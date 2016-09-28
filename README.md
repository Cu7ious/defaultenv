# defaultenv

Environment and config file reader for python3.
**Warrning:** slightly magic inside. This module magically read and use environment value both from '.env' file and environment itself.

```python
$ echo "MY_VAL='test'" > .env
$ python
>>> from defaultenv import env
>>> env('PATH')
'/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/opt/X11/bin'
>>> env('TEST')
>>> env('MY_VAL')
'test'
>>> import os; os.environ['MY_VAL']
'test'

```

`env` method may be used to check the value of variable.
If variable is not defined `env` method will return `None`.
If both environment variable and corresponding .env record is exist then  .env have a priority.
And yes, you can use `os.environ` instead of  `env()`, all records from .env will be exported immidiately.
