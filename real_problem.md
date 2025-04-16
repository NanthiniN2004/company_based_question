## Day 39 - Problem Solving for the day - 08.04.2025  
## You are given a function, Void *ReplaceCharacter(Char str[], int n, char ch1, char ch2); The function accepts a string  ‘ str’ of length n and two characters ‘ch1’ and ‘ch2’ as its arguments . Implement the function to modify and return the string ‘ str’ in such a way that all occurrences of ‘ch1’ in original string are replaced by ‘ch2’ and all occurrences of ‘ch2’  in original string are replaced by ‘ch1’. Assumption: String Contains only lower-case alphabetical letters. 
## Note: 
## Return null if string is null. 
## If both characters are not present in string or both of them are same, then return the string unchanged. 
## Example: 
## Input: 
Str: apples 
ch1:a 
ch2:p 
## Output: 
paales

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	  /* String str="apple";
	   String ch1="a";
	    String ch2="p";
	    String replace=str.replaceAll(ch1,ch2);
	     replace=str.replaceAll(ch2,ch1);
		System.out.println(replace);*/
		
		Scanner s=new Scanner(System.in);
		System.out.println("Enter the string");
		String str=s.nextLine();
		System.out.println("Enter the two character");
		char ch1=s.next().charAt(0);
		char ch2=s.next().charAt(0);
		if(str==null)
		{
		    System.out.println("null");
		}
		if(ch1==ch2)
		{
		    System.out.println(str);
		}
		StringBuilder sb=new StringBuilder();
		for(char c:str.toCharArray())
		{
		    if(c==ch1)
		    {
		        sb.append(ch2);
		        
		    }
		    else if(c==ch2)
		    {
		        sb.append(ch1);
		    }
		    else{
		        sb.append(c);
		    }
		}
		System.out.println(sb.toString());
		
	}
}


OUTPUT:

Enter the string
apple
Enter the two character
a
p
paale

````

