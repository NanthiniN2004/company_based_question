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

##  Day 38 - Problem Solving for the day - 07.04.2025  
## A carry is a digit that is transferred to left if sum of digits exceeds 9 while adding two numbers from right-to-left one digit at a time You are required to implement the following function. Int NumberOfCarries(int num1 , int num2); The functions accepts two numbers ‘num1’ and ‘num2’ as its arguments. You are required to calculate and return  the total number of carries generated while adding digits of two numbers ‘num1’ and ‘ num2’. Assumption: num1, num2>=0 
## Example: 
## Input 
Num 1: 451 
Num 2: 349 
## Output 
2

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		System.out.println("Enter the number 1");
		int n1=s.nextInt();
		System.out.println("Enter the number 2");
		int n2=s.nextInt();
		int carry=0;
		int count=0;
		while(n1>0 || n2>0)
		{
		    int d1=n1%10;
		    int d2=n2%10;
		    int sum=d1+d2+carry;
		    if(sum>=10)
		    {
		        carry=1;
		        count++;
		        
		    }
		    else{
		        carry=0;
		    }
		    n1/=10;
		    n2/=10;
		}
		System.out.println("count of the carry "+count);
	
	}
}

OUTPUT:
Enter the number 1
5892
Enter the number 2
3108
count of the carry 3

````
##  Day 37 - Problem Solving for the day - 05.04.2025 
 
## Selection of MPCS exams include a fitness test which is conducted on ground. There will be a batch of 3 trainees, appearing for running test in track for 3 rounds. You need to record their oxygen level after every round. After trainee are finished with all rounds, calculate for each trainee his average oxygen level over the 3 rounds and select one with highest oxygen level as the most fit trainee. If more than one trainee attains the same highest average level, they all need to be selected. 
 
## Display the most fit trainee (or trainees) and the highest average oxygen level. 
 
## Note: 
The oxygen value entered should not be accepted if it is not in the range between 1   and 100. 
If the calculated maximum average oxygen value of trainees is below 70 then declare the trainees as unfit with meaningful message as “All trainees are unfit. 
 
## Average Oxygen Values should be rounded. 
 
## Example 1: 
## INPUT VALUES 
95 
92 
95 
92 
90 
92 
90 
92 
90 
 
## OUTPUT VALUES 
Trainee Number : 1 
Trainee Number : 3 
 
## Note: 
Input should be 9 integer values representing oxygen levels entered in order as   
Round 1 
Oxygen value of trainee 1 
Oxygen value of trainee 2 
Oxygen value of trainee 3 
 
Round 2 
Oxygen value of trainee 1 
Oxygen value of trainee 2 
Oxygen value of trainee 3 
Round 3 
Oxygen value of trainee 1 
Oxygen value of trainee 2 
Oxygen value of trainee 3 
Output must be in given format as in above example. For any wrong input final output should display “INVALID INPUT”

````JAVA[]


