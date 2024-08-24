# B - Candies Emm?

# Answer:

```c++

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/b
	c++ -Wall -Wextra -Werror main.cpp -o a.out && ./a.out
*/

# include <iostream>
# include <sstream>

int main(void)
{
	int t = 0;
	std::cin >> t;
	for (int i = 0; i < t; ++i)
	{
		int n = 0;
		std::cin >> n;
		int mihai = 0;
		int bianca = 0;
		for (int j = 0; j < n; ++j)
		{
			int candies = 0;
			std::cin >> candies;
			if (candies % 2 == 0)
			{
				mihai += candies;
			}
			else
			{
				bianca += candies;
			}
		}
		if (mihai > bianca)
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
