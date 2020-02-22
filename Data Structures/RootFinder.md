Implement squareRootFinder and nthRootFinder. For more details, please look at the write-up posted on iCollege. Please leave the main method blank, but you can use it for testing. If you'd like to run your squareRootFinder or nthRootFinder, you may call it in your main method and the print the output to see what you get.

	Hint: Remember we want decimal places, so we may want to start using doubles and not ints. 

Tests that I will run:

	squareRootFinder(41, 1) == 20.50000
	squareRootFinder(41, 3) == 5.12500
	squareRootFinder(41, 20) == 6.40316
	squareRootFinder(41, 100) == 6.40312
	squareRootFinder(100, 1) == 50.00000
	squareRootFinder(100, 3) == 12.50000
	squareRootFinder(100, 6) == 10.93750

	nthRootFinder(64, 100, 3) == 4.0000
	nthRootFinder(64, 2, 3) == 16.0000
	nthRootFinder(60, 4, 3) = 3.75000
	nthRootFinder(60, 100, 3) == 3.91487
	nthRootFinder(32, 4, 5) == 2.0000
	nthRootFinder(100, 20, 5) == 2.51188


Answer:
	import java.text.DecimalFormat;

	class Main {
	  public static void main(String[] args) {
	    
	  }
	  
	  public static String squareRootFinder(int number, int iterations){
	    
	      double min=0;
	      double max=number;
	      double mid=0;       //initialized a mid outside, in the worst cast scenario that there wasn't an iteration
           	    while(iterations>0){
	       mid=(max+min)/2;     //insuring the mid is always updated at the beginning of the while loop
	      
	      if(mid*mid>number){  
	        max=mid;           //if the square of the mid is too big, then max gets updated to min
        
	       }else if(mid*mid<number){
	        min=mid;           //if the square of the mid is too small, then min gets updated to min
	       }
	       iterations--;    //update
	    }
	    String answer=String.format("%.5f",mid);
	   return answer;
    
	  }
  
	   public static String nthRootFinder(int number, int iterations, int n){
	    // TODO: implement the nthRoofFinder here
	    double min=0;               //initialized min
	    double max=number;          //initialized max
	    double middle=0;            //set mid as 0; just in case there are no iterations
    
	       while(iterations>0){
	         middle=(min+max)/2;
	         double input=middle;       //the update for the mid, after it goes through the while loop
	            for (int i=n; i>1;i--){
	            input=input*middle;      //this is the function that raises mid to the 'n'th power
	            }
	         if(input>number){
	         max=middle;
	          }
	         else if(input<number){
	         min=middle;
	          }
	        iterations--;               // updating the while loop
	       }
	    return String.format("%.5f", middle); 
   
	  }
	}