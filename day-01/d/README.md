# D - Range Sum Queries

# Answer:

```c++
# include <stdio.h>

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
		ans[i + 1] = ans[i] + arr[i];
	}
	for (int i = 0; i < q; ++i)
	{
		scanf("%d", &a);
		scanf("%d", &b);
		printf("%lli\n", ans[b] - ans[a - 1]);
	}
	return (0);
}
```
