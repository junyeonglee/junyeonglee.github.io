# Heaps

## Min Heaps
```py
import heapq

# under the hood are arrays
minHeap = []

# push
heapq.heappush(minHeap, 8)
heapq.heappush(minHeap, 7)
heapq.heappush(minHeap, 9)

# min
min = minHeap[0]

# pop
while(len(minHeap)):
  print(heapq.heappop(minHeap))
```

## Max Heaps
```py
# no max heaps by default, the work around is to use min heap and multiply by -1 when push & pop
import heapq

maxHeap = []

# push
heapq.heappush(maxHeap, -8)
heapq.heappush(maxHeap, -7)
heapq.heappush(maxHeap, -9)

# max
max = -1 * maxHeap[0]

# pop
while(len(maxHeap)):
  print(-1 * heapq.heappop(maxHeap))
```

## Build Heaps
```py
import heapq

arr = [8, 5, 6, 7, 2]
heapq.heapify(arr)
while(arr):
  print(heapq.headpop(arr))
```

