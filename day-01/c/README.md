# C - Crazy array

You are given an array of integers. You want to modify the array so that it is increasing, i.e., every element is at least as large as the previous element.

On each move, you may increase the value of any element by one. What is the minimum
number of moves required?

### Input
The first input line contains an integer : the size of the array.
Then, the second line contains integers x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>n</sub>: the contents of the array.

### Output

Print the minimum number of moves.

### Constraints

- 1 $$\le$$ n $$\le$$ 2 ⋅ 10<sup>5</sup>
- 1 $$\le$$ x<sub>i</sub> $$\le$$ 10<sup>9</sup>

### Example

| Input      | Output         |
| 5          | 5
| 3 2 5 1 7

# Answer:

```c++

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/c
	c++ -Wall -Wextra -Werror main.cpp -o a.out && ./a.out
*/

# include <iostream>

int main(void)
{
	int n = 0;
	long long prev = 0;
	long long moves = 0;
	long long current = 0;
	std::cin >> n;
	for (int i = 0; i < n; ++i)
	{
		std::cin >> current;
		if (prev > current)
		{
			moves += (prev - current);
			current = prev;
		}
		prev = current;
	}
	std::cout << moves << std::endl;
	return (0);
}
```
