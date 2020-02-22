In  this  problem,  we  will  implement  a  simple  dictionary  of common words in the English language, represented as an array of words paired with their 
lengths. You will need to implement each of the below methods in the Dictionary class. In this problem, the first line of input represents the method to call.  
It will be one of the following: MIN, MAX, RANGE, AVERAGE, MODE. The second line  will  represent  an  integer n,  which  denotes  the  number  of  words  
in the list. The following n lines will each be a word.  The words will not necessarily be sorted.  Your output should be a single line representing the 
results of the method. 
	(a)  minWordLength() method, which should return the length of the smallest word in the list. 
	(b)  maxWordLength(), which should return the length of the largest word in the list. 
	(c)  wordLengthRange(),  which  should  return the range of lengths in the word list. 
	(d)  averageWordLength(), which should return the average word length in the word list.  The method should return the average, accurate to exactly 
	     two decimal 
	     places (i.e.  if the average length is 5, return 5.00). 
	(e)  mostCommonWordLength(), which should return the most common length of the words in the list.  If there is a tie, you should return -1.  
             You may assume that the length of a word is at most 100 and at least 1.



Answer:

	import java.lang.UnsupportedOperationException;
	import java.util.Scanner;

	public class Main {
	    // Constants for function names in input
	    public static final String MIN_METHOD_NAME = "MIN";
	    public static final String MAX_METHOD_NAME = "MAX";
	    public static final String RANGE_METHOD_NAME = "RANGE";
	    public static final String AVERAGE_METHOD_NAME = "AVERAGE";
	    public static final String MODE_METHOD_NAME = "MODE";
	    
	    public static void main(String[] args) {
	        Scanner sc = new Scanner(System.in);
	        }
       
	    }
                                   
	    private static int minWordLength(String[] words) {
	        int minimum=Integer.MAX_VALUE;
        
	        for (int i=0;i<words.length;i++){
	          if (words[i].length()<minimum){
	            minimum=words[i].length();
	            }
	         }
        
	    return minimum; 
	    }
                                   
	    private static int maxWordLength(String[] words) {
	       int maximum=Integer.MIN_VALUE;
	        
	        for (int i=0;i<words.length;i++){
	          if (words[i].length()>maximum){
	            maximum=words[i].length();
	        }
	    }
        	
	    return maximum; 
	    }
	                                   
	    private static int wordLengthRange(String[] words) {
	       return maxWordLength(words)-minWordLength(words);
	    }
                                   
	    private static String averageWordLength(String[] words) {
	        double count=0;
	        for(int i=0;i<words.length;i++){
	          count+=words[i].length();
	        }
	      double average=count/words.length;
	        
	      return String.format("%.2f",average);
	    }
                                   
	    private static int mostCommonWordLength(String[] words) {	
	      int[]count=new int[101];   //created an array to keep track of wordLengths
	        for(int i=0; i<words.length;i++){
	          count[words[i].length()]+=1;
	        }
	      int modeHigh=0;           //now I have an array that needs to be checked for the mode
	      int modeTwoHigh=0;
	      int index=0
	        for(int i=0;i<count.length;i++){
	          if (count[i]>modeHigh){
	            modeTwoHigh=modeHigh;
	            modeHigh=count[i];
		    index=i;
	          }
	          else if(count[i]==modeHigh){
	            modeTwoHigh=count[i];
	          }
	        }
	      if(modeTwoHigh==modeHigh){
	      return -1;
	      }
	      else return index;
	      }
	}