### My Initial Solution 
'''python
# Space: O(1) 
# Time: O(1), since we know n is 32 bits 
def hammingWeight(self, n: int) -> int:
    total = n & 1 
    while n != 0: 
        total += n >> 1 & 1 
        n = n >> 1 
    return total 
'''
The 1 inside the solution acts as a **bit mask**, in this case it gives us the least significant bit 

### Another approach using a bit-manipulating trick 
'''python
def hammingWeight(self, n):
    total = 0
    while n:
        n &= n - 1
        total += 1
    return total
'''
n & n - 1 will remove the least significant 1

Intuition: n = XXX1000, n - 1 = XXX0111, n & (n - 1) = XXX0000
