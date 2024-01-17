# Searching Algorithms

There are two different search algorithms:
: Linear Search
: Binary Search

## Linear Search
* This search method works regardless of whether the data is sorted or not.
* However, the data item you could be looking for might be near the end of the list so would take longer to get to.

```Python
find ← 2
found ← Falselength = list.LENGTH
counter ← 0
ENDWHILE found == False and counter < length
     IF list[counter] == find then
          found = True
          print ('Found at position', counter)
     ELSE:
          counter = counter + 1
     ENDIF
ENDWHILE
IF found == False then
     print('Item not found')
ENDIF 
```
* You need to know the code for a linear seach as it is simple.

## Binary Search
`Divide and conquer`

How it works:
: 1. Start by setting the counter to the middle position in the list.
: ![binary-search-1.png](binary-search-1.png)
: 2. If the value held there is a match, the search ends.
: 3. If the value at the midpoint is less than the value to be found, the list is divided in half. The lower half of the list is ignored and the search keeps to the upper half of the list.
: ![binary-search-2.png](binary-search-2.png)
: 4. Otherwise, if the value at the midpoint is greater than the value to be found, the upper half of the list is ignored and the search keeps to the lower half of the list.
: 5. The search moves to the midpoint of the remaining items. Steps 2 through 4 continue until a match is made or there are no more items to be found. 
: ![binary-search-3.png](binary-search-3.png)

* It is faster, but it requires the data to be sorted before being searched through.





