```python
def gcd(a, b):
    if a == 0:
        return b
    return gcd(b % a, a)

def lcd(a, b):
    return a * b // gcd(a, b)

def solution(arr):
    ans = lcd(arr[0], arr[1])
    for i in range(2, len(arr)):
        ans = lcd(ans, arr[i])
    return ans
```