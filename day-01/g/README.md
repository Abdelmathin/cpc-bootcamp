# G - Clock

Victor has a 24-hour clock that shows the time in the format "HH:MM" (00 ≤ HH ≤ 23,00 ≤ MM ≤ 59). He looks at the clock every 𝑥 minutes, and the clock is currently showing time 𝑠.

How many different palindromes will Victor see in total after looking at the clock every 𝑥 minutes, the first time being at time 𝑠?

For example, if the clock starts out as 03:12 and Victor looks at the clock every  360 minutes (i.e. every 6 hours), then he will see the times 03:12, 09:12, 15:12, 21:12, 03:12, and the times will continue to repeat. Here the time 21:12 is the only palindrome he will ever see, so the answer is 1.

A palindrome is a string that reads the same backward as forward. For example, the times 12:21, 05:50, 11:11 are palindromes but 13:13, 22:10, 02:22 are not.

### Input

The first line of the input contains an integer 𝑡 (1 ≤ t ≤ 100) — the number of test cases. The description of each test case follows.

The only line of each test case contains a string 𝑠 of length 5 with the format "HH:MM" where "HH" is from "00" to "23" and "MM" is from "00" to "59" (both "HH" and "MM" have exactly two digits) and an integer 𝑥 (1 ≤ x ≤ 1440) — the number of minutes Victor takes to look again at the clock.

### Output

For each test case, output a single integer — the number of different palindromes Victor will see if he looks at the clock every 𝑥 minutes starting from time 𝑠.

### Examples

| Input             | Output         |
| ----------------- | -------------- |
| 6                 | 1              |
| 03:12 360         | 16             |
| 00:00 1           | 10             |
| 13:22 2           | 0              |
| 15:15 10          | 1              |
| 11:11 1440        | 1              |
| 22:30 27          |                |

### Note

The first test case is explained in the statement.

# Answer:

```c++

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/g
	c++ -Wall -Wextra -Werror main.cpp -o a.out && ./a.out
*/

# include <iostream>
# include <sstream>

std::string add_minutes(std::string time, int minutes)
{
	int in_minutes = 0;
	int hour   = 10 * (time[0] - '0') + (time[1] - '0');
	int minute = 10 * (time[3] - '0') + (time[4] - '0');
	in_minutes = (60 * hour + minute + minutes) % 1440;
	hour   = (in_minutes / 60);
	minute = (in_minutes % 60);
	std::stringstream ss(""); 
	if (hour < 10)
		ss << "0";
	ss << hour << ":";
	if (minute < 10)
		ss << "0";
	ss << minute;
	return (ss.str());
}

int is_palin(std::string time)
{
	return ((time[0] == time[4]) && (time[1] == time[3]));
}

int main(void)
{
	int t = 0;
	std::cin >> t;
	for (int i = 0; i < t; ++i)
	{
		std::string time;
		int s = 0;
		std::cin >> time;
		std::cin >> s;
		const std::string init_time = time;
		int count = 0;
		do
		{
			count += is_palin(time);
			time = add_minutes(time, s);
		} while (init_time != time);
		std::cout << count << std::endl;
	}
	return (0);
}
```
