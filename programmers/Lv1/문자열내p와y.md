```python
from collections import Counter

def solution(s):
    s_list = list(map(str.lower, s))
    counter = Counter(s_list)
    return counter['p'] == counter['y']
```