# J - Olympiad Team

# Answer:

```c++
# include <iostream>

int main(void)
{
	int one = 0;
	int two = 0;
	int thr = 0;
	int teams_count = 0;
	static int ones[5000];
	static int twos[5000];
	static int thrs[5000];
	int n = 0; std::cin >> n;
	for (int i = 0; i < n; ++i)
	{
		int ti = 0;
		std::cin >> ti;
		if (ti == 1)
			ones[one++] = i + 1;
		if (ti == 2)
			twos[two++] = i + 1;
		if (ti == 3)
			thrs[thr++] = i + 1;
	}
	teams_count = one;
	if (teams_count > two)
		teams_count = two;
	if (teams_count > thr)
		teams_count = thr;
	std::cout << teams_count << std::endl;
	for (int i = 0; (i < one) && (i < two) && (i < thr); ++i)
	{
		std::cout << ones[i] << " " << twos[i] << " " << thrs[i] << std::endl;
	}
	return (0);
}
```
