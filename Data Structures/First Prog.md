##### Write code that prompts a user for their name and then displays 
      “Hello, [name here]!” The flow should look like the following:

      What is your name? Rachel Min
      Hello, Rachel Min!

If the user does not enter anything but presses Enter anyways, you should
re-prompt for the user’s name.  This flow should look like the following:
(note that there should be a space after any ?  or :)

	What is your name?
	What is your name?
	What is your name? Rachel Min
	Hello, Rachel Min!			########

Answer:
	import java.util.Scanner;

	public class Main {
	  public static void main(String[] args) {
	    greetings();
	    }
	public static void greetings(){
	    Scanner a = new Scanner(System.in);
	    System.out.println("What is your name? ");
	    String name = a.nextLine();
	      while(name.isEmpty()){
	        System.out.println("What is your name?");
	        name = a.nextLine();
	      }
	    System.out.println("Hello, "+name+"!");
   	 }
	}