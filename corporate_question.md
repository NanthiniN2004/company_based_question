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

