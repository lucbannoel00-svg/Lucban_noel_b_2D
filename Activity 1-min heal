# Lucban_noel_b_2D
Activity8

class MinHeap:
    def __init__(self):
        self.heap = []

    def insert(self, value):
        self.heap.append(value)
        i = len(self.heap) - 1

        while i > 0:
            parent = (i - 1) // 2

            if self.heap[i] < self.heap[parent]:
                self.heap[i], self.heap[parent] = (
                    self.heap[parent], self.heap[i]
                )
                i = parent
            else:
                break

    def peek(self):
        if not self.heap:
            raise IndexError("Heap is empty")
        return self.heap[0]

    def extract(self):
        if not self.heap:
            raise IndexError("Heap is empty")

        minimum = self.heap[0]
        last = self.heap.pop()

        if self.heap:
            self.heap[0] = last
            self._heapify(0)

        return minimum

    def _heapify(self, i):
        n = len(self.heap)

        while True:
            smallest = i
            left = 2 * i + 1
            right = 2 * i + 2

            if left < n and self.heap[left] < self.heap[smallest]:
                smallest = left

            if right < n and self.heap[right] < self.heap[smallest]:
                smallest = right

            if smallest == i:
                break

            self.heap[i], self.heap[smallest] = (
                self.heap[smallest], self.heap[i]
            )
            i = smallest

    def size(self):
        return len(self.heap)


# Testing
h = MinHeap()

values = [5, 9, 11, 14, 19, 17, 18, 13]

for value in values:
    h.insert(value)

print("Peek:", h.peek())
print("Size:", h.size())

result = []
while h.size() > 0:
    result.append(h.extract())

print("Extracted:", result)
