# Sum Of Odd Numbers
## Instructions

Given the triangle of consecutive odd numbers:

             1
          3     5
       7     9    11
   13    15    17    19
21    23    25    27    29
...
Calculate the sum of the numbers in the nth row of this triangle (starting at index 1) e.g.: (Input --> Output)
´´´
1 -->  1
2 --> 3 + 5 = 8
´´´
## My thought process

Steps:
  1.Find which numbers exist on row n
  2.Sum the numbers of the row
  Note:
    - The number of the row n means there are n numbers on that row
    - The very first number of each row gains always 2 more difference from the next first number
    (ex: 1 ,3 ,7 ,13, 21 ,31 ,43 ...)

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    class RowSumOddNumbers {
      
        public static int rowSumOddNumbers(int n) {
          if(n == 1){
            return 1;
          }
          int startingNum = 1;
          int startingNumsDifference = 2;
          for(int i = 1; i < n; i++){
            startingNum += startingNumsDifference;
            startingNumsDifference += 2;
          }
          int sum = 0;
          for(int i = 0; i < n; i++){
            sum += startingNum;
            startingNum = startingNum + 2; 
          }
          return sum;
        }
    }
    
</details>
