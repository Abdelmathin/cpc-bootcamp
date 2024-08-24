# H - Range Xor Queries

# Answer:

```c

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/h
	cc -Wall -Wextra -Werror main.c -o a.out && ./a.out
*/

# include <stdio.h>
# include <math.h>

int main(void)
{
	int n = 0;
	int q = 0;
	int a = 0;
	int b = 0;
	static long long arr[200001];
	static long long ans[200001];
	scanf("%d", &n);
	scanf("%d", &q);
	for (int i = 0; i < n; ++i)
	{
		scanf("%lld", &arr[i]);
		ans[i + 1] = arr[i] ^ ans[i];
	}
	for (int i = 0; i < q; ++i)
	{
		scanf("%d", &a);
		scanf("%d", &b);
		printf("%lli\n", ans[b] ^ ans[a - 1]);
	}
	return (0);
}
```
