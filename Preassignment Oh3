//Sara Klaavo (2624099)

import java.util.Date;
import java.util.InputMismatchException;
import java.util.Scanner;
import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.io.File;
import java.io.FileWriter;
import java.io.IOException; 

public class Main {

	private static final Scanner sc = new Scanner(System.in);
	
  //In the main method it asks user for a wanted function
	// in a loop which you can exit only by choosing Exit.
	//
	public static void main (String [] args) {
		
		String uname ="";
		
		System.out.println("** Welcome! **");
		
		int valinta1=0;
		while (valinta1==0) {
			
			System.out.println("\n\n-- Choose a function: --");
			System.out.println("1) Write a message");
			System.out.println("2) Look at the previous message");
			System.out.println("3) Exit");	
			
			try {
				valinta1 = sc.nextInt();
		    } catch (InputMismatchException ime) {
		    	valinta1=0;
		    }
			
			
			switch (valinta1) {
      
      // write a message:
      // receives given username and message, makes timestamp an
			// writes it into a file.
			 case 1: 
       
       
				 sc.nextLine();
				 System.out.println("Give a preferred username:");
				 uname = sc.nextLine();
				
				 sc.nextLine();
				 String message="";
				 System.out.println("Write a message. Note: An enter will end the message.");
				 int in = 2;
				 
				 while(in==2) {
					 
					 message = sc.nextLine();
					 if (message == "") {
						System.out.println("-- Something went wrong. The message can not be empty.");	
						System.out.println("-- Try again: ");	
					 }  else 
						 	in = 0;	 	
				 }
	
				 // Makes a timestamp:
				 DateFormat dateFormat = new SimpleDateFormat("yyyy/MM/dd HH:mm:ss");
				 Date date = new Date();
				 String time = dateFormat.format(date);

				 //writes to the file (timestamp, username and message):
				 try {
         
					   FileWriter writer = new FileWriter("preworkki.txt");
				     writer.write(time + " " );
				     
				     writer.write(" <" + uname + ">  " );
				     
				     writer.write(message + "\n" );
				     writer.close();
             
				 } catch (IOException e) {
					 System.out.println("\n ! Something went wrong with saving the message.");
				     e.printStackTrace();
				 }
				 
				 valinta1=0;
				 break;
				 
       //previous message
       // Opens a file and reads the latest message from the file.
			 case 2: 
						
			     try ( Scanner l = new Scanner (new File("preworkki.txt"))) {
						// "/Users/OMISTAJA/eclipse-workspace/Kt6O2/bin/sanoja.txt"	
			          String a= "";
				            
			          while(l.hasNextLine()) {
					       a = l.nextLine(); 	        	   
					      }          
					          
				      l.close();	
				      System.out.println("\n " + a);
				  }catch( IOException e ){
				      System.out.println("! Previous messages not found.");				           
				  }
	 
				 valinta1=0;
				 break;
				 
         
       // Exits  
			 case 3: 
				  System.out.println("\n Bye bye!  \\( ^-^)/");
				 break;
				 
       // Gives an error message
			 default: 
				 System.out.println("** Invalid input **");
				 sc.nextLine();
				 break;
				 
			}
		}
		

	}
  
  
  //writeMsg writes the message into the file (preworkki.txt)
	//
	public void writeMsg(String msg, String time,String username) {
  
		 try {
			   FileWriter writer = new FileWriter("preworkki.txt");
		     writer.write(time );
		     
		     writer.write(username);
		     
		     writer.write(msg);
		     writer.close();
		    
		     System.out.println("Message saved.\n");
		     
		 } catch (IOException e) {
			 System.out.println("Something went wrong.");
		     e.printStackTrace();
		 }
	}

}
