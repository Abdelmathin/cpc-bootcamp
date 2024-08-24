# F - Substring reverse

In a given string s was chosen a substring of characters from the i-th to the j-th inclusive (characters in the string s are numbered starting from one). Then was swapped the i-th symbol with the j-th, (i + 1)-th with (j - 1)-th and so on (the substring was reversed). Print the string s after all changes are done.

## Input

The first line contains the string s that is no longer than 1000 characters, the second line contains the numbers i and j (i ≤ j).

## Output

Print the string s after all changes.

## Example

| Input            | Output         |
| ---------------- | -------------- |
| zbbg             | zbbg           |
| 2 3              |                |

| Input            | Output         |
| ---------------- | -------------- |
| gaqipkajibk      | gaqikpajibk    |
| 5 6              |                |

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
