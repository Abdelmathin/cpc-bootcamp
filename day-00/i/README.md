## I - Basketball One-on-One

Alice and Barbara played some friendly games of one-on-one basketball after work, and you agreed to help them keep score. The rules of the game were simple:

- Each successful shot by a player earns them either one or two points;
- The first player to eleven points wins, with one exception;
- If the score is tied 10-10, the previous rule is replaced by a “win by 2” rule: the first player to lead the other by at least two points wins.

So for example, 11–7, 9–11, and 14–12 are possible final scores (but not 14–13).

Whenever Alice or Barbara scored points, you jotted down an A or B (indicating a score by Alice or by Barbara) followed by a 1 or 2 (the number of points scored). You have some records of the games Alice and Barbara played in this format, but do not remember who won each game. Can you reconstruct the winner from the game record?

### Input

The input consists of a single line with no more than 200 characters: the record of one game. The record consists of single letters (either A or B) alternating with single numbers (either 1 or 2), and includes no spaces or other extraneous characters. Each record will be a correct scoring history of a single completed game, played under the rules described above.

### Output

Print a single character, either A or B: the winner of the recorded game.

### Sample 1

| Input            | Output         |
| ---------------- | -------------- |
| A2B1A2B2A1A2A2A2 | A              |

### Sample 2

| Input                          | Output         |
| ------------------------------ | -------------- |
| A2B2A1B2A2B1A2B2A1B2A1A1B1A1A2 | A              |

# Answer:

```c

# include <stdio.h>
# include <unistd.h>

static int score(int A, int B)
{
	if (A > B)
		write(1, "A\n", 2);
	else
		write(1, "B\n", 2);
	return (0);
}

int main(void)
{
	int i = 0;
	int A = 0;
	int B = 0;
	static char buffer[210];

	buffer[read(0, buffer, 210)] = 0;
	while ((buffer[i] == 'A') || (buffer[i] == 'B'))
	{
		if (buffer[i] == 'A')
		{
			A += buffer[i + 1] - '0';
		}
		else
		{
			B += buffer[i + 1] - '0';
		}
		i += 2;
		if ((A == 10) && (B == 10))
		{
			break ;
		}
		if (A >= 11)
			return (score(A, B));
		if (B >= 11)
			return (score(A, B));
	}
	while ((buffer[i] == 'A') || (buffer[i] == 'B'))
	{
		if (buffer[i] == 'A')
		{
			A += buffer[i + 1] - '0';
		}
		else
		{
			B += buffer[i + 1] - '0';
		}
		i += 2;
		if ((A - B >= 2) && (A >= 12))
			return (score(A, B));
		if ((B - A >= 2) && (B >= 12))
			return (score(A, B));
	}
	return (score(A, B));
}

```
