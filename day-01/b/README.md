# B - Candies Emm?

# Answer:

```c++
# include <iostream>
#include <sstream>

/*
	c++ -Wall -Wextra -Werror main.cpp -o a.out && ./a.out < infile
*/

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
