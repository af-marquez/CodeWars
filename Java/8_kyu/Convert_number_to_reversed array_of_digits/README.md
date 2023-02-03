# Convert number to reversed array of digits
## Instructions

Convert number to reversed array of digits
Given a random non-negative number, you have to return the digits of this number within an array in reverse order.

Example(Input => Output):
```
35231 => [1,3,2,5,3]
0 => [0]
```
## My thought process
Steps:
  1. Turn into a string
  2. Iterate while filling new array
  3. Return Array

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class Kata {
      public static int[] digitize(long n) {
        String number = n + "";     
        int [] arr = new int [number.length()];
        int j = number.length()-1;
        for(int i = 0; i < number.length(); i++){
          arr[i] = Character.getNumericValue(number.charAt(j));
          j--;
        }
        return arr;
      }
    }

</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see the answer</summary>

    public class Kata {
      public static int[] digitize(long n) {
            return new StringBuilder().append(n)
                                      .reverse()
                                      .chars()
                                      .map(Character::getNumericValue)
                                      .toArray();
      }
    }
    //by SithFire
    
</details>
