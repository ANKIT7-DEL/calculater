# calculater

import java.util.Scanner;
interface Calculator{
	double add(double a,double b);
	double subtract(double a ,double b);
	double multiply (double a ,double b);
	double divide(double a , double b);
}
class BasicCalculator implements Calculator{
	public double add(double a ,double b) {
		return a +b;
	}
	public double subtract(double a ,double b) {
		return a- b;
	}
	public double multiply (double a ,double b) {
		return a*b;
	}
	public double divide(double a , double b) {
		if(b==0) {
			throw new ArithmeticException("Cannot Divide by zero");
		}
		return a/b;
	}
	
}







public class cal {
	public static void main(String[] args) {
	Scanner scanner = new Scanner (System.in);
	System.out.print("Enter the fisrt Number");
	double num1 = scanner.nextDouble();
	
	System.out.print("enter the second number");
	double num2 = scanner.nextDouble();
	
	Calculator calculator = new BasicCalculator();
	
	System.out.println("result of addition " + calculator.add(num1, num2));
	System.out.println("result of substraction" + calculator.subtract(num1, num2));
	System.out.println("result of multipy" + calculator.multiply(num1, num2));
	 
	try {
		System.out.println("result of division " + calculator.divide(num1, num2));
	}catch(ArithmeticException e) {
		System.out.println("Error " + e.getMessage());
	}
	
	
	}
}
