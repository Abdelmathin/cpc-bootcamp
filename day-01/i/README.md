# I - Password Gen

# Answer:

```c++

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/i
	c++ -Wall -Wextra -Werror main.cpp -o a.out && ./a.out
*/

# include <iostream>

int main(void)
{
	int n = 0;
	int k = 0;
	int i = 0;
	std::cin >> n;
	std::cin >> k;
	std::string password = "";
	while (true)
	{
		if (i >= k)
		{
			i = 0;
		}
		password += (char) ('a' + i);
		if ((int)(password.length()) == (int)n)
		{
			std::cout << password << std::endl;
			return (0);
		}
		i++;
	}
	return (0);
}
```
