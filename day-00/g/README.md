## G - Sum of Two Values (use Map)

You are given an array of 𝑛 integers, and your task is to find two values (at distinct positions) whose sum is 𝑥.

### Input

The first input line has two integers 𝑛 and x: the array size and the target sum.

The second line has 𝑛 integers 𝑎<sub>1</sub>, 𝑎<sub>2</sub>,…,𝑎<sub>𝑛</sub> : the array values.

### Output

Print two integers: the positions of the values. If there are several solutions, you may print any of them. If there are no solutions, print IMPOSSIBLE.

### Constraints

1≤ n ≤ 2⋅10<sup>5</sup>

1 ≤ x,a<sub>i</sub> ≤ 10<sup>9</sup>

#### Example

| Input            | Output         |
| ---------------- | -------------- |
| 4 8              | 2 4            |
| 2 7 5 1          |                |

# Answer:

```c++
#include <iostream>
#include <map>
using namespace std;
int main()
{
	int n,x,a;
	map<int, int> m;
	cin>>n>>x;
	for (int i = 1; i <= n; ++i)
	{
		cin>>a;
		if (m.count(x-a)>0)
		{
			cout << m[x-a] << " " << i << endl;
			return 0;
		}
		m[a] = i;
	};
	cout << "IMPOSSIBLE" << endl;
	return 0;
}
```
