# J - Olympiad Team

The School №0 of the capital of Berland has n children studying in it. All the children in this school are gifted: some of them are good at programming, some are good at maths, others are good at PE (Physical Education). Hence, for each child we know value t<sub>i</sub>:

- t<sub>i</sub> = 1, if the i-th child is good at programming,
- t<sub>i</sub> = 2, if the i-th child is good at maths,
- t<sub>i</sub> = 3, if the i-th child is good at PE

Each child happens to be good at exactly one of these three subjects.

The Team Scientific Decathlon Olympias requires teams of three students. The school teachers decided that the teams will be composed of three children that are good at different subjects. That is, each team must have one mathematician, one programmer and one sportsman. Of course, each child can be a member of no more than one team.

What is the maximum number of teams that the school will be able to present at the Olympiad? How should the teams be formed for that?

### Input

The first line contains integer n (1 ≤ n ≤ 5000) — the number of children in the school. The second line contains n integers t<sub>1</sub>,t<sub>2</sub>, ...,t<sub>n</sub> (t<sub>i</sub>), where t<sub>i</sub> describes the skill of the i-th child.

### Output

In the first line output integer w — the largest possible number of teams.

Then print w lines, containing three numbers in each line. Each triple represents the indexes of the children forming the team. You can print both the teams, and the numbers in the triplets in any order. The children are numbered from 1 to n in the order of their appearance in the input. Each child must participate in no more than one team. If there are several solutions, print any of them.

If no teams can be compiled, print the only line with value w equal to 0.

### Examples

| Input            | Output         |
| ---------------- | -------------- |
| 7                | 2              |
| 1 3 1 3 2 1 2    | 3 5 2          |
|                  | 6 7 4          |

| Input            | Output         |
| ---------------- | -------------- |
| 4                | 0              |
| 2 1 1 2          |                |


# Answer:

```c++

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/j
	c++ -Wall -Wextra -Werror main.cpp -o a.out && ./a.out
*/

# include <iostream>

int main(void)
{
	int one = 0;
	int two = 0;
	int thr = 0;
	int teams_count = 0;
	static int ones[5000];
	static int twos[5000];
	static int thrs[5000];
	int n = 0; std::cin >> n;
	for (int i = 0; i < n; ++i)
	{
		int ti = 0;
		std::cin >> ti;
		if (ti == 1)
			ones[one++] = i + 1;
		if (ti == 2)
			twos[two++] = i + 1;
		if (ti == 3)
			thrs[thr++] = i + 1;
	}
	teams_count = one;
	if (teams_count > two)
		teams_count = two;
	if (teams_count > thr)
		teams_count = thr;
	std::cout << teams_count << std::endl;
	for (int i = 0; (i < one) && (i < two) && (i < thr); ++i)
	{
		std::cout << ones[i] << " " << twos[i] << " " << thrs[i] << std::endl;
	}
	return (0);
}
```
