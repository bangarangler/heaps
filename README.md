# Heaps Data Structure

---

## 06/12/2019

# Heap

All about priority!

Want to be able to access the priority element in O(1) time

First Pass Idea

    # Example : get_max()
    def get_max(queue):
        max_value = queue[0]
        for element in queue:
            if element > max_value:
                max_value = element
        return max_value

Runtime for this would be O(n) or linear time.  Had to look through every element in queue to make sure we found the max.  This will not be good enough

O(1) or constant time is what we want

Ways to Access in O(1) : using index if we know it.  Keys in objects / hash-table. If working with trees we pretty much have constant time access at root of the tree.

---

Heaps as Binary Trees : max element always at root of the tree. and children will just be smaller than the parent.  This would be opposite if it was a min heap.

When deleting from a heap. it will delete the max element from the heap and returned. so how do we fill in root spot?

Take one of the Leaf nodes and put it in root spot of the heap.  7 will figure out which is larger and then swap and repeat.

Whats the runtime of delete algorithm?  

---

Pros : Heaps are maximally efficient at what they do.

due to the fact that we combined the tree- and array-based approaches, heaps don't exhibit many weaknesses.

very flexible, since we can generalize the idea of priority to many different contexts.

---

Cons : only have direct access to the root of the tree. no direct access to any other nodes.

We can use an Array so we have access to every single element.

combining of the tree- and array-based approaches does not make the heap a particularly intuitive data structure to understand and grasp.

---

Formulas :

l = left, r = right, p = parent

 l = 2i + 1

r = 2i + 2

p = floor((i - 1) / 2)

    # Pseudocode
    '''
    1. store a reference to the first heap element
    2. set the value of the first heap element to the value of the last heap element
    3. pop from the heap's storage array to remove the last heap element
    4. In a loop:
    		A. Have the (new) first heap element check it's two 
    children using the given formulas
    		B. if either of the element's children are larger, swap the heap
     value of the parent node with the value of the larger child's value
     via their respective indices
    5. continue the loop until the element is in a spot where neither
     of its children are larger than it (or it's reached a spot where it
     has no children)
    '''