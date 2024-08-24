# K - MEXO Game

# Answer:

```c++
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
