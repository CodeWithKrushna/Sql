# KP
PrimeNumberProgram
package com.corejava.demo;

public class PrimeNumber2
{
	public static void main(String[] args)
	{
		String PNumber ="";
		
		for(int i=1; i<1000; i++) 
		{
			int count=0;
			
			for(int j=1;j<=i;j++) 
			{
				if(i%j==0)
				{
					count++;
				}
			}
			if(count==2) 
			{
				PNumber=PNumber+i+" ";
			}
			
		}
		System.out.println("Prime Number Between 1 TO 1000");
		System.out.println(PNumber);
		

	}

}
