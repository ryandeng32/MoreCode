### My Initial Solution 
```python
class PeekingIterator:
    def __init__(self, iterator):
        """
        :type iterator: Iterator
        """
        self.iterator = iterator 
        self.buffer = None 

    def peek(self):
        """
        Returns the next element in the iteration without advancing the iterator.
        :rtype: int
        """
        self.buffer = self.buffer or self.iterator.next() 
        return self.buffer
        

    def next(self):
        """
        :rtype: int
        """
        if self.buffer: 
            ans = self.buffer 
            self.buffer = None 
        else: 
            ans = self.iterator.next() 
        return ans 

    def hasNext(self):
        """
        :rtype: bool
        """
        if self.buffer: 
            return True 
        return self.iterator.hasNext() 
```
