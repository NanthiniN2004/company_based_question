## Day 53 - Problem Solving for the day - 22.04.2025

## Find the duplicate in an array

## Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive. There is only one repeated number in nums, return this repeated number.You must solve the problem without modifying the array nums and use only constant extra space.

## Test Case 01:

Input: nums = [1,3,4,2,2] 

Output: 2

## Test Case 02 : 

Input: nums = [3,1,3,4,2] 

Output: 3

## Test Case 03 : 

Input: nums = [1,1] 

Output: 1

## Test Case 04 : 

Input: nums = [1,1,2] 

Output: 1

````java[]

package sample;
import java.util.*;
public class findduplicate {
  public static int findduplicate(int[] a)
  {
	  int slow=a[0];
	   int fast=a[0];
		
	  do {
			slow=a[slow];
			fast=a[a[fast]];
		}while(slow!=fast);                                   ////Floyd's Tortoise and Hare (Cycle Detection) algorithm. THIS IS ALGORITHM USED FOR SOLVE THIS PROBLEM EFFIENTLY
		slow=a[0];
		while(slow!=fast)
		{
			slow=a[slow];
			fast=a[fast];
		} 
		return slow;
  }
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++)
		{
			a[i]=s.nextInt();
		}
	  int res=findduplicate(a);
	  System.out.println("Duplicate element "+res);

	}

}

OUTPUT:

5
3
1
3
4
2
Duplicate element 3

````

