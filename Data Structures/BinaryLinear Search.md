##Binary & Linear Search
	In this problem, you will write binary and linear search.  For both functions 
	you  are  to  return  the  index  of  the  specified  number,  or  -1  if  the 
	number is not in the input list.  Also, even if you pass the tests, the TAs 
	will  go  through  the  code  and  ensure  you  implemented  linear  search  
	for linear search and binary search for binary search.

	For example, searching [0, 5, 10] for 10 should return 2.
	Searching [0, 5, 10] for 12 should return -1.

(a)  Implement  the linearSearch() method. This  method should
perform linear search on the given input list, and return an index, or -1 if 
the element doesn’t exist.
(b)  Implement  the binarySearch() method. This  method should  
perform  binary  search  on  the  given  input  list,  and  return an index, or -1 
if the element doesn’t exist.

	inputArray - a passed in array of integers, not necessarily sorted
	sortedArray - a sorted array of integers
	searchTarget - the number you are searching for

Answer:
	
	class Main {
	  public static void main(String[] args) {
	    // Don't mess with this
	  }
	}
	
	class LinearSearch { 
	  public int linearSearch(int[] inputArray, int searchTarget) {
	    for(int i=0;i<inputArray.length;i++){
	      if (inputArray[i]==searchTarget){
	          return i;
	        }
	     }
	  return -1;
	  }
	}

	class BinarySearch { 
	  public int binarySearch(int[] sortedArray, int searchTarget) {
	    int min=0;
	    int max=sortedArray.length-1;
	    while (min<=max){
	      int mid=(min+max)/2;
	      if (sortedArray[mid]<searchTarget){
	          min=mid+1;
	         }
	      else if (sortedArray[mid]>searchTarget){
	          max=mid-1;
	         }
	      else return mid;
	    }
	    return -1;
	  }
	}