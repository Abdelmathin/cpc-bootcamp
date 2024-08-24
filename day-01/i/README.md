# I - Password Gen

Innokentiy decides to change the password in the social net "Contact!", but he is too lazy to invent a new password by himself. That is why he needs your help.

Innokentiy decides that new password should satisfy the following conditions:

- the length of the password must be equal to n,
- the password should consist only of lowercase Latin letters,
- the number of distinct symbols in the password must be equal to k,
- any two consecutive symbols in the password must be distinct.

Your task is to help Innokentiy and to invent a new password which will satisfy all given conditions.

### Input

The first line contains two positive integers n and k (2 ≤ n ≤ 100, 2 ≤ k ≤ min(n  26)) — the length of the password and the number of distinct symbols in it.

### Output

Print any password which satisfies all conditions given by Innokentiy.

### Examples

| Input            | Output         |
| ---------------- | -------------- |
| 4 3              | java           |

| Input            | Output         |
| ---------------- | -------------- |
| 6 6              | python         |

| Input            | Output         |
| ---------------- | -------------- |
| 5 2              | phphp          |

### Note

In the first test there is one of the appropriate new passwords — java, because its length is equal to 4 and 3 distinct lowercase letters a, j and v are used in it.

In the second test there is one of the appropriate new passwords — python, because its length is equal to 6 and it consists of 6 distinct lowercase letters.

In the third test there is one of the appropriate new passwords — phphp, because its length is equal to 5 and 2 distinct lowercase letters p and h are used in it.

Pay attention the condition that no two identical symbols are consecutive is correct for all appropriate passwords in tests.

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
