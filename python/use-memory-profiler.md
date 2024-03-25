# Use Memory Profiler

Install
```shell
pip install memory_profiler
```

Template
```python
from memory_profiler import profile

@profile
def method(args):
    ...
  
method()
```

Use
```shell
python -m memory_profiler target.py
```

[source](https://pypi.org/project/memory-profiler/)