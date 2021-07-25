package javaProject;
import java.util.Scanner;
import Package.*;

class Bmi
{
	double heightInMeter;
	double weightInKg;
	Bmi(double heightInMeter,double weightInKg){
		this.heightInMeter=heightInMeter;
		this.weightInKg=weightInKg;
	}
	
}



class Category extends Bmi
{
	public Category(double heightInMeter, double weightInKg) {
		super(heightInMeter, weightInKg);
		
	}
	

	public void categorycheck()
	{
		double bmi_value = (weightInKg/(heightInMeter*heightInMeter));
		System.out.println("The BMI value for the data is "+bmi_value);
		
	
		
		
	
		if( bmi_value < 18.5)
		{
			System.out.println("Need to improve diet and consult a doctor");
			System.out.println("MALNOURISHED");
		}
		if(bmi_value  > 18.5 && bmi_value < 25)
		{
			System.out.println("Is a fit individual. Keep maintaining a healthy lifestyle.");
			System.out.println("NORMAL");
		}	
		if(bmi_value  > 25 && bmi_value  < 30)
		{
			System.out.println("Good diet and regular excercise must");
			System.out.println("OVERWEIGHT");
			
		}
		if(bmi_value>30)
		{
			System.out.println("Must reduce weight and consult doctor");
			System.out.println("OBESE");
		
		}
	}
}
class rating {
	public void rate(int a) {
		System.out.println("You rated us "+a);
	}
	public void rate(String sr) {   //overloading
		System.out.println("Your Comment "+sr);
	}
}
interface AboutBmi //interface
{
public	void intro();
}
class introBmi implements AboutBmi{
public	void intro() {  //overriding.
		System.out.println("BODY MASS INDEX(BMI) is  a standard and basic fitness measurement procedure.");
		System.out.println("BMI is obtained by dividing body mass by the square of the body height.");
		System.out.println("BMI is expresswed in kg per meter square and implemented throughout the world.");
		System.out.println(" ");
	}
}
// ABSTACT CLASS
abstract class WriterIntro
{
	public void intro()
	{
		
	}
}
class DisplayWriterInfo extends WriterIntro
{
	// METHOD OVERIDDING
	public void intro()

	{
		System.out.println("This code is written by:-");
		System.out.println("R NAVEEN KUMAR");
		System.out.println("4NI19IS071");
		System.out.println("ISE - NATIONAL INSTITUTE OF ENGINEERING, MYSURU");
	}
}
class terminater extends Thread{ //threading
	public void run() {
		try {
			Thread.sleep(1000);
		}
		catch(InterruptedException e) {
			System.out.println("Intreption occur "+e);
		}
		System.out.println("Program is Terminating....");
		System.out.println("Program is terminated.");
	}
}
public class BodyMassIndexCalc {
	//private static String result;

	public static void main(String args[])
	{
	try {
		introBmi A1=new introBmi();
		A1.intro();
		// CREATE SCANNER CLASS OBJECT TO TAKE INPUT
		Scanner scan = new Scanner(System.in);
		System.out.println("Enter the weight in Kg: ");
		double weightInKg = scan.nextDouble();
		
		System.out.println("Enter the height in meters: ");
		double heightInMeter = scan.nextDouble();
		
		Category obj1 = new Category(heightInMeter,weightInKg);
		
		 obj1.categorycheck();
		System.out.println("Please rate us on basis of ur experience.");
		rating R1=new rating();
		System.out.println("Enter your rating on scale -10 to 10.");
		int ob1=scan.nextInt();
		System.out.println("Please choose a comment for us from Excellent, ,Good, Average,Poor,or any Others of ur choice.");
		String str =scan.next();
		R1.rate(ob1);
		R1.rate(str);
		//CLOSE SCANNER CLASS OBJECT
		scan.close();}
	catch(Exception e) {
		System.out.println("Exception is caught "+e);
	}
				
		finally{
			DisplayWriterInfo A2=new DisplayWriterInfo();
			A2.intro();
			ShowAcknowledgement A3=new ShowAcknowledgement();
			A3.Acknowledgement();
			terminater A5=new terminater();
			A5.run();
		
	}

}
}
-------------------------------------------------------------------------------------------------------------------------------------------------------------package Package;

public class ShowAcknowledgement {
	public void Acknowledgement()
	{
		System.out.println("I am happy to say that I have successfully concluded the project");
		System.out.println("I would like to thank our course instructor Mr. Suhaas K P");
		System.out.println("This project helped me to learn many new things");
		System.out.println("This project leads to enhancement of my knowledge in Oops with java.");
		
	}

}
