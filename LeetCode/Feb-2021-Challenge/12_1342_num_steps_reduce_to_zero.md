### My initial solution
```python
def numberOfSteps (self, num: int) -> int:
    return (bin(num)[2:].count('1')-1 + len(bin(num)[2:]))
```
```javascript
var numberOfSteps  = function(num) {
    let total = 0; 
    while (num != 0) {
        if (num % 2 == 0) {
            num /= 2; 
        } else {
            num -= 1; 
        }
        total += 1;
    }
    return total;
};
```
