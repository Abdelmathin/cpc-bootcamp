# A - Cost Emm?

We define an integer to be the most common on a subsegment, if its number of occurrences on that subsegment is larger than the number of occurrences of any other integer in that subsegment. A subsegment of an array is a consecutive segment of elements in the array a.

Given an array a of size n, and an integer k, determine if there exists a non-empty subsegment of a where k is the most common element.

### Input

Each test consists of multiple test cases. The first line contains a single integer t (1 ≤ t ≤ 1000) — the number of test cases. The description of test cases follows.

The first line of each test case contains two integers n and k (1 ≤ n ≤ 100, 1 ≤ k ≤ 100) — the number of elements in array and the element which must be the most common.

The second line of each test case contains n integers a<sub>1</sub>, a<sub>2</sub>, a<sub>3</sub> , …, a<sub>n</sub> (1 ≤ a<sub>i</sub> ≤100) — elements of the array.

## Output
For each test case output "YES" if there exists a subsegment in which k is the most common element, and "NO" otherwise.

You can output the answer in any case (for example, the strings "yEs", "yes", "Yes", and "YES" will be recognized as a positive answer).

### Examples

| Input       | Output         |
| ----------- | -------------- |
| 7           | YES
| 5 4         | NO
| 1 4 3 4 1   | NO
| 4 1         | YES
| 2 3 4 4     | YES
| 5 6         | YES
| 43 5 60 4 2 | YES
| 2 5         |
| 1 5         |
| 4 1         |
| 5 3 3 1     |
| 1 3         |
| 3           |
| 5 3         |
| 3 4 1 5 5   |


### Note
In the first test case we need to check if there is a subsegment where the most common element is 4.

On the subsegment [2,5] the elements are 4, 3, 4, 1.
- 4 appears 2 times
- 1 appears 1 time;
- 3 appears 1 time.

This means that 4 is the most common element on the subsegment [2,5], so there exists a subsegment where 4 is the most common element.

# Answer:

```c++

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/a
	c++ -Wall -Wextra -Werror main.cpp -o a.out && ./a.out
*/

# include <iostream>

int main(void)
{
	int t = 0;
	std::cin >> t;
	for (int i = 0; i < t; ++i)
	{
		int n = 0;
		int k = 0;
		std::cin >> n;
		std::cin >> k;
		int p = 0;
		int y = 0;
		for (int j = 0; j < n; ++j)
		{
			std::cin >> p;
			y += (p == k);
		}
		if (y)
		{
			std::cout << "YES" << std::endl;
		}
		else
		{
			std::cout << "NO" << std::endl;
		}
	}
	return (0);
}
```
