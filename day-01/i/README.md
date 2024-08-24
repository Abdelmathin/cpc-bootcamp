# I - Password Gen

# Answer:

```c++
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
