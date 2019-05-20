[![Build Status](https://travis-ci.org/fabiocaccamo/python-benedict.svg?branch=master)](https://travis-ci.org/fabiocaccamo/python-benedict)
[![codecov](https://codecov.io/gh/fabiocaccamo/python-benedict/branch/master/graph/badge.svg)](https://codecov.io/gh/fabiocaccamo/python-benedict)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/0dbd5cc2089f4dce80a0e49e6822be3c)](https://www.codacy.com/app/fabiocaccamo/python-benedict)
[![Requirements Status](https://requires.io/github/fabiocaccamo/python-benedict/requirements.svg?branch=master)](https://requires.io/github/fabiocaccamo/python-benedict/requirements/?branch=master)
[![PyPI version](https://badge.fury.io/py/python-benedict.svg)](https://badge.fury.io/py/python-benedict)
[![PyPI downloads](https://img.shields.io/pypi/dm/python-benedict.svg)](https://img.shields.io/pypi/dm/python-benedict.svg)
[![Py versions](https://img.shields.io/pypi/pyversions/python-benedict.svg)](https://img.shields.io/pypi/pyversions/python-benedict.svg)
[![License](https://img.shields.io/pypi/l/python-benedict.svg)](https://img.shields.io/pypi/l/python-benedict.svg)

# python-benedict
python-benedict is the Python dictionary for humans dealing with evil data.

## Features
-  Full **keypath** support *(using the dot syntax)*
-  Many **utility methods** to retrieve data as needed *(all methods listed below)*
-  100% **backward-compatible** *(you can replace existing dicts without pain)*

## Requirements
-  Python 3.4, 3.5, 3.6, 3.7

## Installation
-  Run `pip install python-benedict`

## Testing
-  Run `tox` / `python setup.py test`

## Usage
`benedict` is a dict subclass, so it is possible to use it as a normal dict *(you can just cast an existing dict)*.

### Basic get/set using keypath

```python
from benedict import benedict

d = benedict()
d['profile.firstname'] = 'Fabio'
d['profile.lastname'] = 'Caccamo'
print(d) # -> { 'profile':{ 'firstname':'Fabio', 'lastname':'Caccamo' } }
print(d['profile']) # -> { 'firstname':'Fabio', 'lastname':'Caccamo' }
print('profile.lastname' in d) # -> True
```

### Extra methods

```python
# Return a deepcopy of the dict.
d.deepcopy()
```

```python
# Return a list of all keypaths in the dict.
d.get_keypaths()
```

### Utility methods

```python
# Get value by key or keypath trying to return it as bool.
# Values like `1`, `true`, `yes`, `on`, `ok` will be returned as `True`.
d.get_bool(key, default=False)
```

```python
# Get value by key or keypath trying to return it as bool.
# Values like `1`, `true`, `yes`, `on`, `ok` will be returned as `True`.
d.get_bool(key, default=False)
```

```python
# Get value by key or keypath trying to return it as list of bool values.
# If separator is specified and value is a string it will be splitted.
d.get_bool_list(key, default=[], separator=',')
```

```python
# Get value by key or keypath trying to return it as datetime.
# If format is not specified it will be autodetected.
# If options and value is in options return value otherwise default.
d.get_datetime(key, default=None, format=None, options=[])
```

```python
# Get value by key or keypath trying to return it as list of datetime values.
# If separator is specified and value is a string it will be splitted.
d.get_datetime_list(key, default=[], format=None, separator=',')
```

```python
# Get value by key or keypath trying to return it as Decimal.
# If options and value is in options return value otherwise default.
d.get_decimal(key, default=Decimal('0.0'), options=[])
```

```python
# Get value by key or keypath trying to return it as list of Decimal values.
# If separator is specified and value is a string it will be splitted.
d.get_decimal_list(key, default=[], separator=',')
```

```python
# Get value by key or keypath trying to return it as dict.
# If value is a json string it will be automatically decoded.
d.get_dict(key, default={})
```

```python
# Get value by key or keypath trying to return it as float.
# If options and value is in options return value otherwise default.
d.get_float(key, default=0.0, options=[])
```

```python
# Get value by key or keypath trying to return it as list of float values.
# If separator is specified and value is a string it will be splitted.
d.get_float_list(key, default=[], separator=',')
```

```python
# Get value by key or keypath trying to return it as int.
# If options and value is in options return value otherwise default.
d.get_int(key, default=0, options=[])
```

```python
# Get value by key or keypath trying to return it as list of int values.
# If separator is specified and value is a string it will be splitted.
d.get_int_list(key, default=[], separator=',')
```

```python
# Get value by key or keypath trying to return it as list.
# If separator is specified and value is a string it will be splitted.
d.get_list(key, default=[], separator=',')
```

```python
# Get value by key or keypath trying to return it as slug.
# If options and value is in options return value otherwise default.
d.get_slug(key, default='', options=[])
```

```python
# Get value by key or keypath trying to return it as list of slug values.
# If separator is specified and value is a string it will be splitted.
d.get_slug_list(key, default=[], separator=',')
```

```python
# Get value by key or keypath trying to return it as string.
# Encoding issues will be automatically fixed.
# If options and value is in options return value otherwise default.
d.get_str(key, default='', options=[])
```

```python
# Get value by key or keypath trying to return it as list of str values.
# If separator is specified and value is a string it will be splitted.
d.get_str_list(key, default=[], separator=',')
```

## License
Released under [MIT License](LICENSE.txt).