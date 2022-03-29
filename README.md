# Optimizing_Python_LinkedIn_Learning Notes

- 3 rules of optimization
  1. Don't - always have measurable performance goals before optimizing goals
  2. Don't... Yet - developer time is expensive -- sometimes the best solution is to upgrade hardware
  3. Profile before Optimizing - profiling measures where code spends time
- general tips
  - use real data
  - windows-users
    - turn off anti-virus programs when c-profiling
  - have a test suite ready
  - know when to measure
- measuring time
  - helps to:
    - choose between alternatives
    - get metrics on run time
  - python methods
    - time module
    - timeit module
  - time is tricky for computers
  - measurements of elapsed time include the time processes spend sleeping
  - Python 3 includes the monotonic and perf_counter unctions for high resolution monotonic timers
- CPU Profiling
  - cProfile is recommended by Python
  - deterministic profilers record every function call, return, and exception
  - statistical profilers record where the program is at small intervals
  - pstats module displays profile-generated statistics file
  - `python -m cProfile <filename>.py`
```python
import cProfile
    
cProfile.run('function_name(params)')
```
  - run `python <filename>.py` when using above setup
```python
import cProfile
    
cProfile.run('function_name(params)', filename='prof.out')
```
   - run `python -m pstats prof.out`
     - `sort cumtime`
     - `stats 10`
     - pip install `snakeviz`
       - `snakeviz prof.out`
       

- bisects library python
- deque library python
- heapq library python
- 