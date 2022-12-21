# Convert a string to an array
## Instructions

Write a function to split a string and convert it into an array of words.

Examples (Input ==> Output):
"Robin Singh" ==> ["Robin", "Singh"]

"I love arrays they are my favorite" ==> ["I", "love", "arrays", "they", "are", "my", "favorite"]

## My thought process

Steps:
  1. Return using split() method

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class Solution {
  
      public static String[] stringToArray(String s) {
        return s.split(" ");
      }
  
    }
    
</details>

