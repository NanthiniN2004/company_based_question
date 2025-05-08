## Day 69 - Problem Solving for the day - 08.05.2025
## You're working on a text simplification tool that removes duplicate characters for normalization.
## Remove all duplicate characters from a string and return the result in order of first appearance.
## Test case 01 :
Input  : "programming"
Output  : "progamin"

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		String str=s.next();
		HashSet<Character> set=new HashSet<>();
		StringBuilder sb=new StringBuilder();
		for(char c:str.toCharArray())
		{
		    if(!set.contains(c))
		    {
		        set.add(c);
		        sb.append(c);
		    }
		}
		System.out.println("After remove the duplicate character:"+sb.toString());
	}
}


OUTPUT:

PROGRAMMING
After remove the duplicate character:PROGAMIN

````
## Day 67 - Problem Solving for the day - 06.05.2025
## You are building a plagiarism detection system for a university. To compare student assignments, your system needs to analyze all possible substrings of a given string (such as a sentence or paragraph fragment) to look for similarities.  Your task is to write a function that, given a string, returns all possible substrings that can be formed from it.
## Note: A substring is a contiguous sequence of characters within a string. For a string of length n, there are n * (n + 1) / 2 possible substrings.
## Test case 01  :
## Input  :"xyz"
## Output  : ["x", "xy", "xyz", "y", "yz", "z"]
## Test case 02  :
## Input : "abc"
## Output : ["a", "ab", "abc", "b", "bc", "c"]

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		String str=s.next();
		int n=str.length();
		List<String> res=new ArrayList<>();
		for(int i=0;i<n;i++)
		{
		  for(int j=i+1;j<=n;j++) 
		  {
		      res.add(str.substring(i,j));
		  }
		}
		System.out.println(res);
	}
}


OUTPUT:

xyz
[x, xy, xyz, y, yz, z]


`````

