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

##  Day 45 - Problem Solving for the day - 14.04.2025 
## A teacher wants to reward the top two scoring students in a test. Given the list of scores, find the two highest unique scores. Write a function top_two_scores(scores) that returns the two highest unique scores. 
## Test Case 01 : 
Input:  [88, 95, 70, 95, 60] 
Output: [95, 88] 
## Test Case 02 : 
Input:  [85, 85, 85] 
Output: [85] 
## Test Case 03  : 
Input:  [76] 
Output: [76] 
## Test Case 04 :  
Input:  [91, 91, 89, 89, 88] 
Output: [91, 89] 
## Test Case 05  : 
Input:  [91, 91, 89, 89, 88] 
Output: [91, 89]

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	    List<Integer> scores=new ArrayList<>();
	    int n=s.nextInt();
	    for(int i=0;i<n;i++)
	    {
	        scores.add(s.nextInt());
	    }
	    TreeSet<Integer> unique=new TreeSet<>(Collections.reverseOrder());
	    unique.addAll(scores);
	    List<Integer> res=new ArrayList<>();
	    int count=0;
	    for(int score:unique)
	    {
	        res.add(score);
	        count++;
	        if(count==2)
	        {
	            break;
	        }
	    }
	    System.out.println("Heightest Score "+res);
	    
	}
}


OUTPUT:

5
91
91
89
89
88
Heightest Score [91, 89]

````
##  Day 44 - Problem Solving for the day - 13.04.2025 
## Raja is working for a logistics company for their own application. One of the features in the app tracks the loading sequence of cargo containers onto a ship. Due to lastminute schedule changes, the loading sequence needs to be adjusted by rotating the list of containers to the right by k positions, where k is determined by the number of hours delayed. You’re given the current sequence of container IDs in an array, and the delay in hours. Your task is to compute the new loading order after the delay. Write a function adjust_loading_order(containers, delay_hours) that returns the new container loading sequence after adjusting it by rotating it to the right by delay_hours positions. 

## Sample Input 01  : 
containers = [201, 202, 203, 204] 
delay_hours = 1 
## Sample Output 01 : 
[204, 201, 202, 203] 
## Sample Input 02 : 
containers = [401, 402, 403] 
delay_hours = 5 
## Sample Output 02 : 
[402, 403, 401]

````JAVA[]

import java.util.*;
public class Main
{
    public static void rotate(int a[],int d,int n)
    {
         d%=n;
         reverse(a,0,d-1);
         reverse(a,d,n-1);
         reverse(a,0,n-1);
    }
    
    public static void reverse(int[] a,int start,int end)
    {
        while(start<end)
        {
            int temp=a[start];
            a[start]=a[end];
            a[end]=temp;
            start++;
            end--;
        }
    }
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	     int n=s.nextInt();
	     int[] a=new int[n];
	     System.out.println("Enter the container element");
	     for(int i=0;i<n;i++)
	     {
	         a[i]=s.nextInt();
	     }
	     System.out.println("Enter the time delay");
	     int t=s.nextInt();
	     rotate(a,t,n);
	     System.out.println(Arrays.toString(a));
	    
	}
}


OUTPUT:

4
Enter the container element
201
202
203
204
Enter the time delay
1
[202, 203, 204, 201]


````
##  Day 43 - Problem Solving for the day - 12.04.2025 
## Smart Traffic Management System in a smart city. Sensors are installed on every road junction to record the number of vehicles passing through each point at a given time. The data is recorded as an array of integers, where each value represents the traffic count at a junction. City engineers want to detect potential traffic bottlenecks (a sudden spike in traffic surrounded by lower counts), so they can prioritize those areas for intervention. 
## Our task is write the program that: 
1.Identifies all local traffic peaks, i.e., values that are greater than both neighbors 
2.Returns their indices 
3.If no peaks are found, return an empty list 
## Sample Input 01 :  
int[] trafficData = {12, 25, 40, 20, 15, 50, 45, 30} 
int[] trafficData = {5, 10, 5, 10, 5}

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	     int n=s.nextInt();
	     int[] a=new int[n];
	     System.out.println("Enter the traffic data");
	     for(int i=0;i<n;i++)
	     {
	         a[i]=s.nextInt();
	     }
	     List<Integer> res=new ArrayList<>();
	     for(int i=1;i<n-1;i++)
	     {
	         if(a[i]>a[i-1] && a[i]>a[i+1])
	         {
	             res.add(i);
	         }
	     }
	     System.out.println(" Local Peak Element "+ res);
	    
	}
}


OUTPUT:

8
Enter the traffic data
12
25
40
20
15
50
45
30
 Local Peak Element [2, 5]


`````

## Day 42 - Problem Solving for the day - 11.04.2025 
## A warehouse has multiple shelves represented by an array of weights.You must determine if you can split the array into two parts with equal sum. You're given an array of integers, where each element represents the weight on a shelf.You need to determine if it's possible to split the array into two parts such that the sum of the weights in both parts is equal. 
## Sample Input 01 : 
int[] shelves = {1, 2, 3, 4, 6} 
## Sample Input 02 : 
int[] shelves = {1, 2, 3}

````java[]


import java.util.*;
public class Main
{
    
    public static boolean checksum(int[] a,int n)
    {
        int totalsum=0;
        for(int ele:a)
        {
            totalsum+=ele;
        }
        int leftsum=0;
        for(int i=0;i<n;i++)
        {
            leftsum+=a[i];
            int rightsum=totalsum-leftsum;
            if(leftsum==rightsum)
            {
                return true;
            }
        }
        return false;
    }
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	     int n=s.nextInt();
	     int[] a=new int[n];
	     System.out.println("Enter the shelves data");
	     for(int i=0;i<n;i++)
	     {
	         a[i]=s.nextInt();
	     }
	     
	     System.out.println("can split shelves "+ checksum(a,n));
	    
	}
}


OUTPUT:
3
Enter the shelves data
1
2
3
 can split shelves true

````

##   Day 41 - Problem Solving for the day - 10.04.2025  
## You’re tracking the prices of items added to the cart. Sometimes users add the same product multiple times.
## Our Task is to find the below: Find the total cost of items. 
## Remove duplicates and display a summary of unique prices. 
## Sort the prices in descending order. 
## Sample Input 01 : 
int[] prices = {150, 150, 150, 150}; 
## Sample Input 02 : 
int[] prices = {999, 499, 799, 199, 499, 999, 199};

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	    List<Integer> prices=new ArrayList<>();
	    int n=s.nextInt();
	    int sum=0;
	    System.out.println("Enter the prices");
	    for(int i=0;i<n;i++)
	    {
	        prices.add(s.nextInt());
	        sum += prices.get(i);
	    }
	    TreeSet<Integer> unique=new TreeSet<>(Collections.reverseOrder());
	    unique.addAll(prices);
	    
	    System.out.println("unique prices "+unique);
	    System.out.println("Total cost "+sum);
	    
	}
}


OUTPUT:

7
Enter the prices
999
499
799
199
499
999
199
unique prices [999, 799, 499, 199]
Total cost 4193

````
 ## Day 40 - Problem Solving for the day - 09.04.2025  
## You are given a function, Int MaxExponents (int a , int b); You have to find and return the number between ‘a’ and ‘b’ ( range inclusive on both ends) which has the maximum exponent of 2. The algorithm to find the number with maximum exponent of 2 between the given range is Loop between ‘a’ and ‘b’. Let the looping variable be ‘i’. Find the exponent (power) of 2 for each ‘i’ and store the number with maximum exponent of 2 so faqrd in a variable , let say ‘max’. Set ‘max’ to ‘i’ only if ‘i’ has more exponent of 2 than ‘max’. Return ‘max’. Assumption: a <b 
## Note: If two or more numbers in the range have the same exponents of  2 , return the small number. 
## Example 
## Input: 
7 
12 
## Output: 
8


 ````JAVA[]

import java.util.*;
public class Main
{
    public static int exponent(int a,int b)
    {
        int res=a;
        int max=-1;
        for(int i=a;i<=b;i++)
        {
            int num=i;
            int count=0;
            while(num%2==0)
            {
                count++;
                num/=2;
            }
            if(count>max)
            {
                max=count;
                res=i;
            }
        }
        return res;
    }
	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	    System.out.println("Enter a value");
	    int a=s.nextInt();
	    System.out.println("Enter b value");
	    int b=s.nextInt();
	    int result = exponent(a, b);
        System.out.println("Number with maximum exponent of 2: " + result);
	    
	}
}


OUTPUT:

Enter a value
7
Enter b value
12
Number with maximum exponent of 2: 8

````


