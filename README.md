# javacode
import java.io.*;
import java.util.*;
public class Sample{ 

	static final int chars = 256; 
	static int Substr(String str) 
	{ 
		int n = str.length(); 
		int a = 1;
		int max = 1; 
		int index;  
		int str2[] = new int[chars]; 
		for (int i = 0; i < chars; i++) { 
			str2[i] = -1; 
		} 
		str2[str.charAt(0)] = 0; 
		for (int i = 1; i < n; i++) { 
			index = str2[str.charAt(i)]; 
			if (index == -1 || i - a > index) 
				a++; 
			else { 
					if (a > max) 
					max = a; 

				a = i - index; 
			} 

			str2[str.charAt(i)] = i; 
		} 
 
		if (a > max) 
			max = a; 

		return max; 
	} 


	public static void main(String[] args) 
	{ 
		Scanner sc =new Scanner(System.in);
		String str=sc.nextLine();
		int temp = Substr(str); 
		System.out.println(temp); 
	} 
} 
