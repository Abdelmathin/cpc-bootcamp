# B - Candies Emm?

Mihai and Bianca are playing with bags of candies. They have a row 𝑎 of 𝑛 bags of candies. The 𝑖 -th bag has 𝑎𝑖  candies. The bags are given to the players in the order from the first bag to the 𝑛 -th bag.

If a bag has an even number of candies, Mihai grabs the bag. Otherwise, Bianca grabs the bag. Once a bag is grabbed, the number of candies in it gets added to the total number of candies of the player that took it.

Mihai wants to show off, so he wants to reorder the array so that at any moment (except at the start when they both have no candies), Mihai will have strictly more candies than Bianca. Help Mihai find out if such a reordering exists.

### Input

The first line of the input contains an integer 𝑡 (1 ≤ t ≤ 1000) — the number of test cases.

The first line of each test case contains a single integer n (1 ≤ n ≤ 100) — the number of
bags in the array.

The second line of each test case contains space-separated integers a<sub>i</sub> (1 ≤ a<sub>i</sub> ≤ 100)  —
the number of candies in each bag.

### Output

For each test case, output "YES" (without quotes) if such a reordering exists, and "NO" (without quotes) otherwise.

You can output the answer in any case (for example, the strings "yEs", "yes", "Yes" and "YES" will be recognized as a positive answer)

### Examples


### Note

In the first test case, Mihai can reorder the array [4, 1, 2, 3] as follows: . Then the process proceeds as follows:

- the first bag has 4 candies, which is even, so Mihai takes it — Mihai has 4 candies and Bianca has 0.

- the second bag has 1 candies, which is odd, so Bianca takes it — Mihai has 4 candies, and Bianca has 1.

- the third bag has 2 candies, which is even, so Mihai takes it — Mihai has 6 candies, and Bianca has 1.

- the fourth bag has 3 candies, which is odd, so Bianca takes it — Mihai has 6 candies, and Bianca has 4.

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
