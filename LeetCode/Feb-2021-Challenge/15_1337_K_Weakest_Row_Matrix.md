### My initial Solution
```python
# the basic idea is to use a hashmap to group row indexes by their strength
# space: O(col) 
# time: O(col log col + col * row) 
def kWeakestRows(self, mat: List[List[int]], k: int) -> List[int]:
    col, row = len(mat[0]), len(mat) 
    count = {x: [] for x in range(0, col+1)}
    for i in range(row): 
        count[mat[i].count(1)].append(i) 
    ans = [] 
    for i in sorted(list(count.keys())): 
        if k <= len(count[i]): 
            ans.extend(count[i][:k])
            break 
        else: 
            ans.extend(count[i])
            k -= len(count[i]) 
    return ans 
```
### NOTE: learn how to use heap for questions like this (min, max k ...) 

            
