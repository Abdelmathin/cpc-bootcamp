## F - Max Word Frequency (use Map)

Term frequency–Inverse document frequency (tf-idf) is a numerical statistic which reflects the importance of words in a document collection. It is often used in information retrieval system. The number of times a word appears in the document (word frequency) is one of the major factors to acquire tf-idf.

You are asked to write a program to find the most frequent word in a document.

### Input

The first line contains an integer 𝑛 ( 1 ≤ 𝑛 ≤ 1000 ) which determines the number of words. The following  𝑛 lines include the list of words, one word per line. A word contains only lower-case letters and it can contain up to 20 characters.

### Output

Print the word that has the highest frequency and its frequency, separated by a single space. If you get two or more results, choose one that comes later in the lexicographical order.

#### Example

| Input            | Output         |
| ---------------- | -------------- |
| 10               |  zebra 3       |
| mountain         |                |
| lake             |                |
| lake             |                |
| zebra            |                |
| tree             |                |
| lake             |                |
| zebra            |                |
| zebra            |                |
| animal           |                |
| lakes            |                |

# Answer:

```c++
#include<map>
#include<iostream>
#include<string.h>
using namespace std;
int main()
{
	int n;
	cin>>n;
	map<string,int> m;
	string k = "";
	int r = 0;
	while(n--)
	{
		string s;
		cin >> s;
		if (m.count(s) > 0)
		{
			m[s]++;
		}
		else{
			m[s]=1;
		}
		if ((m[s] > r) || ((m[s] == r) && (strcmp(k.c_str(),s.c_str()) < 0)))
		{
			r = m[s];
			k = s;
		}
	}
	cout << k << " " << r<<endl;
	return 0;
}
```
