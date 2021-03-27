# tttt
Python timing library for rudimentary benchmarking.

## Usage

### Basic Example
```python
import tttt
tttt.start()
tttt.time()
# Time elapsed: 2.4 us
```

### Named Timers:
```python
import tttt
tttt.start('Open bigfile.txt')
with open('bigfile.txt') as f:
  f.read()
tttt.time('Open bigfile.txt')
# Open bigfile.txt: 1.6 ms
```

### As a context manager
```python
import tttt
with tttt.time('Open bigfile.txt')
  with open('bigfile.txt') as f:
    f.read()
# Open bigfile.txt: 1.6 ms
```

### Incremental Timers
```python
import tttt
tttt.start()
tttt.inc()
tttt.inc(bar=True, bar_max_s=1)
tttt.time()
```
