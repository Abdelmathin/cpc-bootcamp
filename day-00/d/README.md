## D - Easy Stack

You have an empty stack and you are given some queries. These queries are the basic stack operations such as Push, Pop, and printing the Top element. Now, you should process the given queries.

### Input

First line contains an integer T (0 <= T <= 10<sup>6</sup>).
Each of the next T lines contains a query based on these formats.

1 n : Push n (0 < n <= 10<sup>9</sup>) to the top of the stack.

2 : Pop an element from the top of the stack. If the stack is empty, do nothing.

3 : Print the top element of the stack (see Output Format).

### Output

For each query 3, print the top element of the stack. If the stack is empty, print 'Empty!' without quotes.

#### Example

| Input            | Output         |
| ---------------- | -------------- |
| 6                | 15             |
| 1 15             | Empty!         |
| 1 20             |                |
| 2                |                |
| 3                |                |
| 2                |                |
| 3                |                |

# Warning!

Enormous input data!

# Answer:

```c
#include<stdio.h>
#include<stdlib.h>

int main()
{
	int *arr = (int*)malloc(sizeof(int) * 1000001);
	int t,n,i = 0;
	scanf("%d",&t);
	while (t--)
	{
		scanf("%d",&n);
		if(n==1)
		{
			scanf("%d",&n);
			arr[i++]=n;
		}
		else if ((n == 2) && (i > 0))
		{
			i--;
		}
		else if (n == 3)
		{
			if (i > 0)
			{
				printf("%i\n", arr[i-1]);
			}
			else
			{
				printf("%s\n", "Empty!");
			}
		}
	}
	free(arr);
	return (0);
}
```
