# Create Phone Number
## Instructions

Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.

Example

```Kata.createPhoneNumber(new int[] {1, 2, 3, 4, 5, 6, 7, 8, 9, 0}) // => returns "(123) 456-7890"```

The returned format must be correct in order to complete this challenge.

Don't forget the space after the closing parentheses!

## My thought process

Steps:
1. Iterate through array
2. Check in each point of Phone Number and add to the string
3. Return string

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class Kata {
        public static String createPhoneNumber(int[] numbers) {

            String toReturn = "(";
            
            for(int i = 0; i < 10; i++){
                if(i==3){
                    toReturn += ") "+numbers[i];
                    i++;
                } if(i == 6){
                    toReturn += "-"+numbers[i];
                }else{
                    toReturn += numbers[i];
                } 
            }
            return toReturn;
        }
    }
    
</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see the answer</summary>

    public class Kata {
        public static String createPhoneNumber(int[] numbers) {
            return String.format("(%d%d%d) %d%d%d-%d%d%d%d",numbers[0],numbers[1],numbers[2],numbers[3],numbers[4],numbers[5],numbers[6],numbers[7],numbers[8],numbers[9]);
        }
    }
    //by Rishod
    
</details>
