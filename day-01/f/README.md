# F - Substring reverse

# Answer:

```c

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/f
	cc -Wall -Wextra -Werror main.c -o a.out && ./a.out
*/

# include <stdio.h>

int main(void)
{
	int i = 0;
	int j = 0;
	static char s[1000];
	scanf("%s", s);
	scanf("%d", &i);
	scanf("%d", &j);
	i--;
	j--;
	while (i < j)
	{
		char c = s[i];
		s[i] = s[j];
		s[j] = c;
		i++;
		j--;
	}
	printf("%s\n", s);
	return (0);
}
```
