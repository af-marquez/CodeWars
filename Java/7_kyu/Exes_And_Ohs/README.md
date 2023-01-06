# Exes and Ohs
## Instructions

Check to see if a string has the same amount of 'x's and 'o's. The method must return a boolean and be case insensitive. The string can contain any char.

Examples input/output:

´´´
XO("ooxx") => true
XO("xooxx") => false
XO("ooxXm") => true
XO("zpzpzpp") => true // when no 'x' and 'o' is present should return true
XO("zzoo") => false
´´´

## My thought process
Steps:
1. Convert the input string to lower case
2. Initialize variables to count the number of 'x's and 'o's
3. Loop through the characters in the string
4. Return true if the number of 'x's and 'o's are equal, false otherwise

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class XO {
      public static boolean getXO(String str) {
        // Convert the input string to lower case
        str = str.toLowerCase();
        
        // Initialize variables to count the number of 'x's and 'o's
        int xCount = 0;
        int oCount = 0;
        
        // Loop through the characters in the string
        for (int i = 0; i < str.length(); i++) {
          char ch = str.charAt(i);
          if (ch == 'x') {
            xCount++;
          } else if (ch == 'o') {
            oCount++;
          }
        }
        
        // Return true if the number of 'x's and 'o's are equal, false otherwise
        return xCount == oCount;
      }
    }

</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see my answer</summary>

     public class XO {
      
      public static boolean getXO (String str) {
        str = str.toLowerCase();
        return str.replace("o","").length() == str.replace("x","").length();
        
      }
    }
    //by VikDaBaller
    
</details>
