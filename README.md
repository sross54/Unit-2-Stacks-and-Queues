"""
===========================================================
UNIT 2 DISCUSSION: STACKS AND QUEUES (PYTHON)
===========================================================

OVERVIEW:
This assignment introduces two fundamental data structures:
the Stack (LIFO) and the Queue (FIFO).

You will complete, modify, and extend the starter code while
explaining key concepts through comments and improved output.
"""

from collections import deque


class Stack:
    def __init__(self):
        # TODO (Student): Create the internal data structure for the stack.
        # Hint: A Python list can be used to store stack values.
        # A Python list is used to store stack values.
        self.items = []

    def push(self, value):
        # TODO (Student): Add value to the stack.
        # Add a short comment explaining why this operation supports LIFO behavior.
        # Adding items to the end of the list supports LIFO behavior
        # because the most recently added item becomes the top item.
        self.items.append(value)

    def pop(self):
        # TODO (Student): Remove and return the most recently added value.
        # Improve or explain empty-stack handling.
        # What should happen if the stack is empty?
        # Remove and return the most recently added value.
        if self.is_empty():
            return "Error: Cannot pop from an empty stack."
        return self.items.pop()

    def peek(self):
        # TODO (Student): Return the top value without removing it.
        # Add a comment explaining what peek does.
        # Peek returns the top value without removing it.
        if self.is_empty():
            return "Error: Stack is empty."
        return self.items[-1]

    def is_empty(self):
        # TODO (Student): Return True if the stack has no values.
        # Returns True when no items exist in the stack.
        return len(self.items) == 0


class Queue:
    def __init__(self):
        # TODO (Student): Create the internal data structure for the queue.
        # Hint: collections.deque is useful for efficient queue operations.
        # deque provides efficient insertion and removal operations.
        # Create the queue's internal data structure
            self.items = deque()

    def enqueue(self, value):
        # TODO (Student): Add value to the back of the queue.
        # Add a short comment explaining why this operation supports FIFO behavior.
        # Adding to the back supports FIFO behavior because
        # the first item added remains at the front.
        self.items.append(value)

    def dequeue(self):
        # TODO (Student): Remove and return the value from the front of the queue.
        # Explain or improve empty-queue handling.
        # Remove and return the front item.
        if self.is_empty():
            return "Error: Cannot dequeue from an empty queue."
        return self.items.popleft()

    def front(self):
        # TODO (Student): Return the front value without removing it.
        # Add a comment explaining what front returns.
        # Returns the front value without removing it.
        if self.is_empty():
            return "Error: Queue is empty."
        return self.items[0]

    def is_empty(self):
        # TODO (Student): Return True if the queue has no values.
        # Returns True when the queue has no items.
        return len(self.items) == 0


def main():
    print("=== UNIT 2: STACKS AND QUEUES ===")

    # ===============================
    # TODO (Student): STACK DEMO
    # ===============================
    # Requirements:
    # 1. Create a Stack object.
    # 2. Add at least 4 values to the stack.
    # 3. Improve the print statements so they clearly explain what is happening.
    # 4. Demonstrate LIFO behavior.
    # 5. Show what happens when pop() is used on an empty stack.
    #
    # Edge Cases:
    # 6. Show what happens when peek() is used on an empty stack.
    # 7. Create a stack with only one item, remove it,
    #    and verify the stack is empty afterward.


print("\n=== STACK DEMO ===")
stack = Stack()
print("\nAdding values to the stack:")
stack.push("A")
stack.push("B")
stack.push("C")
stack.push("D")
print("Pushed: A, B, C, D")

print("\nTop item using peek():", stack.peek())

print("\nDemonstrating LIFO behavior:")
print("Pop #1:", stack.pop())  # D
print("Pop #2:", stack.pop())  # C
print("Pop #3:", stack.pop())  # B
print("Pop #4:", stack.pop())  # A

print("\nAttempting to pop from an empty stack:")
print(stack.pop())

print("\nAttempting to peek at an empty stack:")
print(stack.peek())

print("\nSingle-item stack test:")
single_stack = Stack()
single_stack.push(100)
print("Item added:", single_stack.peek())
print("Item removed:", single_stack.pop())
print("Stack empty?", single_stack.is_empty())

# ===============================
# TODO (Student): QUEUE DEMO
# ===============================
# Requirements:
# 1. Create a Queue object.
# 2. Add at least 4 values to the queue.
# 3. Improve the print statements so they clearly explain what is happening.
# 4. Demonstrate FIFO behavior.
# 5. Show what happens when dequeue() is used on an empty queue.
#
# Edge Cases:
# 6. Show what happens when front() is used on an empty queue.
# 7. Create a queue with only one item, remove it,
#    and verify the queue is empty afterward.

print("\n=== QUEUE DEMO ===")
queue = Queue()

print("\nAdding values to the queue:")
queue.enqueue("A")
queue.enqueue("B")
queue.enqueue("C")
queue.enqueue("D")
print("Enqueued: A, B, C, D")

print("\nFront item using front():", queue.front())

print("\nDemonstrating FIFO behavior:")
print("Dequeue #1:", queue.dequeue())  # A
print("Dequeue #2:", queue.dequeue())  # B
print("Dequeue #3:", queue.dequeue())  # C
print("Dequeue #4:", queue.dequeue())  # D

print("\nAttempting to dequeue from an empty queue:")
print(queue.dequeue())

print("\nAttempting to view the front of an empty queue:")
print(queue.front())

print("\nSingle-item queue test:")
single_queue = Queue()
single_queue.enqueue(100)
print("Front item:", single_queue.front())
print("Removed item:", single_queue.dequeue())
print("Queue empty?", single_queue.is_empty())


if __name__ == "__main__":
    main()
