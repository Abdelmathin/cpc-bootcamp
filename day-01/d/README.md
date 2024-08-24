# D - Range Sum Queries

Given an array of n integers, your task is to process q queries of the form: what is the sum of values in range [a,b]?

### Input

The first input line has two integers n and q: the number of values and queries.
The second line has n integers $$x_1$$, $$x_2$$, $$\dots$$, $$x_n$$: the array values.
Finally, there are q lines describing the queries. Each line has two integers a and b: what is the sum of values in range [a,b]?

### Output

Print the result of each query.

### Constraints

- 1 $$\le$$ n,q $$\le$$ 2 $$\cdot$$ $$10^5$$
- 1 $$\le$$ $$x_i$$ $$\le$$ $$10^9$$
- 1 $$\le$$ a $$\le$$ b $$\le$$ n

### Example

#### Input:
8 4
3 2 4 5 1 1 5 3
2 4
5 6
1 8
3 3

#### Output:
11
2
24
4

# Answer:

```c

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/d
	cc -Wall -Wextra -Werror main.c -o a.out && ./a.out
*/

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
