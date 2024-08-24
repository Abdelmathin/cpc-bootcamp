# C - Crazy array

# Answer:

```c++
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