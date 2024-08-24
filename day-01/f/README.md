# F - Substring reverse

# Answer:

```c++
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
