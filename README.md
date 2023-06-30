# Binary-to-octal-conversion-using-Java

Binary to Octal Conversion
In this article we will discuss binary to octal conversion using java. For this purpose we need to ask a binary number from user and convert that binary number to its octal equivalent form and then print the converted number on to the screen.
 
For conversion, we first convert the binary number into decimal form and then convert the decimal number to octal number. For better understanding with an example just have a look towards the diagram shown at the right.
Binary to octal conversion
Method discussed
We will first convert the Binary number into Decimal and then convert the Decimal number into Octal

Make sure that you have gone through these approaches below –

Binary to Decimal Conversion
Decimal to Octal Conversion
Run
//Java program to convert binary number to octal number
import java.util.Scanner;
public class Main
{
	public static void main(String args[])
	{
		//scanner class object creation
		Scanner sc = new Scanner(System.in);    
		//input from user
		System.out.print("Enter a binary number : ");
		int binary = sc.nextInt();
		//Declaring variable to store decimal number  
		int decimal = 0;
		//Declaring variable to use in power		
		int n = 0;  
		//writing logic for the conversion from binary to decimal
		while(binary > 0)
		{
			int temp = binary%10;  
			decimal += temp*Math.pow(2, n);  
			binary = binary/10;  
			n++;  
		}
		int octal[] = new int[20];
		int i = 0;
		//writing logic for the conversion from decimal to octal
		while(decimal > 0)
		{
			int r = decimal % 8;
			octal[i++] = r;
			decimal = decimal / 8;
		}
		//printing result
		System.out.print("Octal number : ");
		for(int j = i-1 ; j >= 0 ; j--)
		System.out.print(octal[j]); 
		//closing scanner class(not compulsory, but good practice)
		sc.close();
	}
}
Method 1 Code
Output :
Enter binary number: 1010
Decimal : 10
Octal : 12
Related Pages
Decimal to Binary conversion

Decimal to Octal Conversion

Decimal to Hexadecimal Conversion

Permutations in which n people can occupy r seats in a classroom 

Octal to Binary conversion

Quadrants in which a given coordinate lies

Method 2:-
Method 2 uses the concept of grouping 3 successive digits/bits of the binary number and calculating octal digits against each grouping

We use an additional array to store the octal digits at each index.

We will need to print the array in reverse to get actual octal equivalent.

Binary to octal conversion
Method 2 Code
Run
//Java program to convert binary number to octal number
import java.util.Scanner;
public class Main
{
	public static void main(String args[])
	{
		//scanner class object creation
		Scanner sc = new Scanner(System.in);    
		//input from user
		System.out.print("Enter a binary number : ");
		int binary = sc.nextInt();
		//Declaring variable to store decimal number  
		int decimal = 0;
		//Declaring variable to use in power		
		int n = 0;  
		//writing logic for the conversion from binary to decimal
		while(binary > 0)
		{
			int temp = binary%10;  
			decimal += temp*Math.pow(2, n);  
			binary = binary/10;  
			n++;  
		}
		int octal[] = new int[20];
		int i = 0;
		//writing logic for the conversion from decimal to octal
		while(decimal > 0)
		{
			int r = decimal % 8;
			octal[i++] = r;
			decimal = decimal / 8;
		}
		//printing result
		System.out.print("Octal number : ");
		for(int j = i-1 ; j >= 0 ; j--)
		System.out.print(octal[j]); 
		//closing scanner class(not compulsory, but good practice)
		sc.close();
	}
}
Output :
Enter binary number: 10101111
257
