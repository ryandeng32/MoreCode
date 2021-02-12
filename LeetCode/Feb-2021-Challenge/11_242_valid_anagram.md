###My initial Solution
```python
# The idea is to use a dictionary to track the differences between the two string 
# and an initial comparison is done to get rid of the easy cases 
def isAnagram(self, s: str, t: str) -> bool:
    if len(s) != len(t) or set([x for x in s]) != set([x for x in t]): 
        return False
    counter = dict() 
    for char in s: 
        if char not in counter: 
            counter[char] = 0
        counter[char] += 1 
    for char in t: 
        counter[char] -= 1 
    for char in counter: 
        if counter[char] != 0: 
            return False
    return True 
```

To understand JS better, I will also write solutions in JS
```javascript
var isAnagram = function(s, t) {
    if (s.length !== t.length) {
        return false; 
    }
    
    let counter = {} 
    for(let i=0; i< s.length; i++){
        if (!(s[i] in counter)) {
            counter[s[i]] = 0; 
        }
        if (!(t[i] in counter)) {
            counter[t[i]] = 0; 
        }
        counter[s[i]] += 1; 
        counter[t[i]] -= 1; 
    }
    for(let key in counter) {
        if (counter[key] !== 0) {
            return false ;
        }
    }
    return true ;
};
```
