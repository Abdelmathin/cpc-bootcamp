## C - Gravity Flip

Little Chris is bored during his physics lessons (too easy), so he has built a toy box to keep himself occupied. The box is special, since it has the ability to change gravity.

There are n columns of toy cubes in the box arranged in a line. The i-th column contains ai cubes. At first, the gravity in the box is pulling the cubes downwards. When Chris switches the gravity, it begins to pull all the cubes to the right side of the box. The figure shows the initial and final configurations of the cubes in the box: the cubes that have changed their position are highlighted with orange.

<p align="center">
	<a href="" target="blank">
		<img style="border-radius: 5px;" src="image.png" />
	</a>
</p>

Given the initial configuration of the toy cubes in the box, find the amounts of cubes in each of the n columns after the gravity switch!

### Input

The first line of input contains an integer n (1 ≤ n ≤ 100), the number of the columns in the box. The next line contains n space-separated integer numbers. The i-th number ai (1 ≤ a<sub>i</sub> ≤ 100) denotes the number of cubes in the i-th column.

### Output

Output n integer numbers separated by spaces, where the i-th number is the amount of cubes in the i-th column after the gravity switch.

#### Example

| Input            | Output         |
| ---------------- | -------------- |
| 4                | 1 2 2 3        |
| 3 2 1 2          |                |

| Input            | Output         |
| ---------------- | -------------- |
| 3                | 2 3 8          |
| 2 3 8            |                |

# Note:

The first example case is shown on the figure. The top cube of the first column falls to the top of the last column; the top cube of the second column falls to the top of the third column; the middle cube of the first column falls to the top of the second column.

In the second example case the gravity switch does not change the heights of the columns.

# Answer:

```python
a=input()
print(" ".join(map(str, sorted(map(int, input().split())))))
```
