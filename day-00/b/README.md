## B - Two arrays

Two arrays of integers are given. Print the elements from the first array (in the same order like they are given in the first array), that are absent in the second array.

### Input

First given number 𝑛 of elements in the first array, then given 𝑛 integers --- the elements of array. Then given the number of elements 𝑚 in the second array. Then given elements of the second array. The number of elements in each array is not greater than 100. All elements are integers.

### Output

Print in the first line the number of required elements. In the second line print those elements of the first array, that are absent in the second array in the same order like in the first array.

#### Example

| Input            | Output         |
| ---------------- | -------------- |
| 7                | 4              |
| 3 1 3 4 2 4 12   | 3 3 2 12       |
| 6                |                |
| 4 15 43 1 15 1   |                |

# Answer:

```python
n1 = int(input())
a1 = input().split()
n2 = int(input())
a2 = input().split()
s = ""
k = 0
for i in a1:
	if not (i in a2):
		k += 1
		s += str(i) + " "
print (k)
print (s.strip())
```

