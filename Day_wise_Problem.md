

## Given two integers M and N, calculate the sum of the factorials of all the 
integers from M and N inclusive* .if M is greater than N , return 0 or display an 
appropriate message. 
Test Case 01 : M = 3, N = 5 
Test Case 02 : M = 0, N = 4 
Test Case 03 : M = 5, N = 5 
Test Case 04 : M = 6, N =4

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



