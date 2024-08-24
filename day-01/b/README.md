# B - Candies Emm?

Mihai and Bianca are playing with bags of candies. They have a row of bags of candies.
The -th bag has candies. The bags are given to the players in the order from the first bag
to the -th bag.

If a bag has an even number of candies, Mihai grabs the bag. Otherwise, Bianca grabs the
bag. Once a bag is grabbed, the number of candies in it gets added to the total number of
candies of the player that took it.

Mihai wants to show off, so he wants to reorder the array so that at any moment (except at
the start when they both have no candies), Mihai will have strictly more candies than
Bianca. Help Mihai find out if such a reordering exists.

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
