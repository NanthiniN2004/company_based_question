

## 1)  Given two integers M and N, calculate the sum of the factorials of all the integers from M and N inclusive* .if M is greater than N , return 0 or display an appropriate message. 
## Test Case 01 : M = 3, N = 5 
## Test Case 02 : M = 0, N = 4 
## Test Case 03 : M = 5, N = 5 
## Test Case 04 : M = 6, N =4

````java[]
package ex;
import java.util.*;
public class main2 {
   
	public static int fact(int n) {
		if(n==0 || n==1) {
			return 1;
		}
		return n*fact(n-1);
	}
	public static void main(String[] args) {
	 
  Scanner s=new Scanner(System.in);
  int m=s.nextInt();
  int n=s.nextInt();
  if(m>n) {
	  System.out.println("Invalid input");
  }
  int sum=0;
  for(int i=m;i<=n;i++) {
	  sum+=fact(i);
  }
  System.out.println("sum of the factorial: "+ sum);
    
	}
	

}


output:

3
6
sum of the factorial: 870


````
 ## 2)  You are working for a Survey Analysis company, and your team has been given the task of analyzing survey responses. The survey asks participants to select their favorite color from a list of options, and you are provided with an array of integers where each integer represents the choice of a color. The goal is to find the majority color — the color that has been selected by more than half of the participants. A majority element in the array is defined as an element that appears more than n/2 times, where n is the length of the array. 

## Requirements: 
## You need to write a function findMajorityColor that takes in an array of integers representing survey results and returns the majority element (if it exists), or -1 if there is no majority element. 

## Input: 
## An array of integers, colors[], where each integer represents a survey response corresponding to a particular color. If the length of the array is n, then the function should find the element that occurs more than n/2 times. 
## Output: 
## The majority element (integer) if it exists. 
## If no majority element exists, return -1. 
## Constraints: 
## The array can have at most 10^5 elements. 
## Array elements are non-negative integers.


```java[]


import java.util.*;
public class Main {

	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	    int n=s.nextInt();
	    int[] a=new int[n];
	    for(int i=0;i<n;i++) {
	    	a[i]=s.nextInt();
	    }
	    int candidate=a[0];
	    int count=1;
	    for(int i=1;i<n;i++) {
	    	if(a[i]==candidate) {
	    		count++;
	    	}
	    	else {
	    		count--;
	    	}
	    	
	    	if(count==0) {
	    		candidate=a[i];
	    		count=1;
	    	}
	    }
	    count=0;
	    for(int num:a) {
	    	if(num==candidate) {
	    		count++;
	    	}
	    }
	    
	    int result=(count>n/2) ? candidate:-1;
	    System.out.println("Majority Element: "+ result);

	}

}

OUTPUT:
5
1
3
3
2
3
Majority Element: 3

`````
## Find the kth largest and smallest number in an array 
## Task 1: Find the kth smallest score (You need to find the 3rd smallest score in this list.)
## Task 2: Find the kth largest score (You also need to find the 2nd largest score in this list.) 
## You have the following scores recorded for 10 participants:  (scores = [65, 89, 45, 72, 54, 91, 32, 77, 60, 82])

````java[]

package day;
import java.util.*;
public class Main1 {
  public static void main(String args[]) {
	  Scanner s=new Scanner(System.in);
	  int n=s.nextInt();
	  int[] a=new int[n];
	  for(int i=0;i<n;i++) {
		  a[i]=s.nextInt();
		  
	  }
	  System.out.println("Enter k value");
	  int k=s.nextInt();
	  for(int i=0;i<n;i++) {
		  for(int j=0;j<n;j++) {
			  if(a[i]<a[j]) {
				  int temp=a[i];
				  a[i]=a[j];
				  a[j]=temp;
			  }
		  }
	  }
	  System.out.println(k+"th largest Element:" + a[n-k]);
	  System.out.println(k+"th Smallest Element:" + a[k-1]);
  }
}


OUTPUT:

10
65
89
45
72
54
91
32
77
60
82
Enter k value
3
3th largest Element:82
3th Smallest Element:54

`````

## FIND THE THIRD MAXIMUM ELEMENT
````JAVA[]

class Solution {
    public int thirdMax(int[] nums) {
        long max1=Long.MIN_VALUE;
        long max2=Long.MIN_VALUE;
        long max3=Long.MIN_VALUE;
        for(int num : nums){
            if(num>max1){
                max3 = max2;
                max2 = max1;
                max1 = num;
            }else if(max1>num && num>max2){
                max3 = max2;
                max2 = num;
            }else if(max2>num && num>max3){
                max3=num;
            }
        }
        return max3 != Long.MIN_VALUE ? (int) max3 : (int) max1;
    }
}

````

## Find Original Array From Doubled Array 

## Problem Statement: A doubled array changed is formed from the original array after appending twice the value of each element in the original array and randomly shuffling elements in the updated original array. Given an array changed, return the original array if changed is a valid doubled array. Otherwise, return empty array. 
## Example:  Input: changed = [2,4,1,8] 

````java[]




