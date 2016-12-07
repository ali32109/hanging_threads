# hanging_threads
Deadlocks? Detect where your threads hang in Python with one import.

## Usage

Starting monitoring as simple as calling the start_monitoring() function.

```
from hanging_threads import start_monitoring
monitoring_thread = start_monitoring()
```

You may also pass additional parameters.

```
monitoring_thread = start_monitoring(seconds_frozen=10, tests_per_second=10)
```

The values in the example are defaults. This mean the check will happen 10
times per second. If a thread is frozen for at least 10 seconds then the stack
is dumped into standard error stream. This happens again every 10 seconds
while there is no changes in the stack registered during checks.


## Useful Stackoverflow links

- [GIL-deadlocks are not covered by this](http://stackoverflow.com/questions/10014481/python-threads-hang#comment33263430_17744731)
- [Package requested, so this was created](http://stackoverflow.com/questions/3443607/how-can-i-tell-where-my-python-script-is-hanging/17744556#comment69129716_17744556)
