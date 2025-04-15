## Day 46 - Problem Solving for the day - 15.04.2025 
## Airline's Maintenance System. After every flight, seats with even-numbered seat IDs need to be flagged for special cleaning due to proximity to air vents. The system receives a list of seat numbers that  were occupied during the flight. To help the cleaning crew, you must replace every even seat number in the list with 0 to indicate that those seats need to be cleaned. 
## Test case 01 : 
Input:  [2, 4, 6, 8] 
Output: [0, 0, 0, 0] 
## Test case 02 : 
Input:  [12, 13, 14] 
Output: [0, 13, 0]

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	    int n=s.nextInt();
	    int[] a=new int[n];
		System.out.println("Enter the element");
		for(int i=0;i<n;i++)
		{
		    a[i]=s.nextInt();
		}
		for(int i=0;i<n;i++)
		{
		    if(a[i]%2==0)
		    {
		        a[i]=0;
		    }
		}		
		System.out.println(Arrays.toString(a));
	}
}

## OUTPUT

4
Enter the element
2
4
6
8
[0, 0, 0, 0]

````

