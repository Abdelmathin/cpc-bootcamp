# K - MEXO Game
Alice and Bob play yet another game on an array 𝑎 of size 𝑛. Alice starts with an empty array 𝑐 . Both players take turns playing, with Alice starting first.

On Alice's turn, she picks one element from 𝑎 , appends that element to 𝑐 , and then deletes it from 𝑎.

On Bob's turn, he picks one element from 𝑎, and then deletes it from 𝑎.

The game ends when the array 𝑎 is empty. Game's score is defined to be the MEX of 𝑐. Alice wants to maximize the score while Bob wants to minimize it. Find game's final score if both players play optimally.

The MEX (minimum excludant) of an array of integers is defined as the smallest non-negative integer which does not occur in the array. For example:

- The MEX of [2, 2, 1] is 0, because 0 does not belong to the array.
- The MEX of [3, 1, 0, 1] is 2, because 0 and 1 belong to the array, but 2 does not.
- The MEX of [0, 3, 1, 2] is 4, because 0, 1, 2 and 3 belong to the array, but 4 does not.

### Input

Each test contains multiple test cases. The first line contains a single integer 𝑡 (1 ≤ t ≤ 2⋅10<sup>4</sup>) — the number of test cases. The description of the test cases follows.

The first line of each test case contains a single integer 𝑛 (1 ≤ n ≤ 2⋅10<sup>5</sup>).

The second line of each test case contains 𝑛 integers 𝑎<sub>1</sub>, 𝑎<sub>2</sub>, …, 𝑎<sub>n</sub> (0 ≤ 𝑎<sub>i</sub> < n).

It is guaranteed that the sum of 𝑛over all test cases does not exceed 2⋅10<sup>5</sup>

### Output
 For each test case, find game's score if both players play optimally.

### Example

| Input      | Output         |
| ---------- | -------------- |
| 3          | 2              |
| 4          | 1              |
| 0 0 1 1    | 0              |
| 4          |                |
| 0 1 2 3    |                |
| 2          |                |
| 1 1        |                |

### Note

In the first test case, a possible game with a score of 2 is as follows:

- 1 Alice chooses the element 1. After this move, a = [0, 0, 1] and c = [1].
- 2 Bob chooses the element 0. After this move, a = [0,1] and c = [1].
- 3 Alice chooses the element 0. After this move, a = [1] and c = [1,0].
- 4 Bob chooses the element 1. After this move, a = [] and c = [1,0].

At the end, c = [1,0], which has a MEX of 2. Note that this is an example game and does not necessarily represent the optimal strategy for both players.

# Answer:

```c++

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/k
	c++ -Wall -Wextra -Werror main.cpp -o a.out && ./a.out
*/

# include <iostream>
# define MAX_N 200001

int *ft_clear(int *array, int n)
{
	for (int i = 0; i < n; ++i)
	{
		array[i] = 0;
	}
	return (array);
}

int *ft_fill(int *array, int n)
{
	int ai = 0;
	ft_clear(array, MAX_N);
	for (int i = 0; i < n; ++i)
	{
		std::cin >> ai;
		array[ai]++;
	}
	return (array);
}

int ft_optimal_mex(int *array, int n)
{
	int used = 0;
	for (int i = 0; i <= n; ++i)
	{
		if (array[i] == 0)
			return (i);
		if (array[i] == 1)
		{
			if (used)
				return (i);
			used++;
		}
	}
	return (0);
}

int main(void)
{
	static int array[MAX_N];

	int t = 0;
	std::cin >> t;
	while (0 < t)
	{
		int n = 0;
		std::cin >> n;
		ft_fill(array, n);
		std::cout << ft_optimal_mex(array, n) << std::endl;
		t = t - 1;
	}
	return (0);
}
```
