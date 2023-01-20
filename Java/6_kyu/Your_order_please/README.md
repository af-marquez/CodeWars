# Your order, please

## Instructions

Your task is to sort a given string. Each word in the string will contain a single number. This number is the position the word should have in the result.

Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).

If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.

Examples
```
"is2 Thi1s T4est 3a"  -->  "Thi1s is2 3a T4est"
"4of Fo1r pe6ople g3ood th5e the2"  -->  "Fo1r the2 g3ood 4of th5e pe6ople"
""  -->  ""
```

## My thought process

Steps:
      1. See if string is empty
      2. Split words
      3. Analize each word to read number and to point to it's correct position
      4. Turn into string
      5. Return String

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class Order {
        public static String order(String str) {
            
            if(str == ""){
            return str;
            }
            
            String [] splittedStrArray = str.split(" ");
            String [] orderedStrArray = new String[splittedStrArray.length];
            
            for(String word : splittedStrArray){
            for (int i = 0; i < word.length(); i++) {
                if(word.charAt(i) >= '1' && word.charAt(i) <= '9'){
                orderedStrArray[Character.getNumericValue(word.charAt(i)-1)] = word;
                }
            }
            }
            String toReturn = String.join(" ", orderedStrArray);
            
            return toReturn;
        }
    }
    
</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see the answer</summary>

    import java.util.Arrays;
    import java.util.Comparator;

    public class Order {
        public static String order(String words) {
            return Arrays.stream(words.split(" "))
            .sorted(Comparator.comparing(s -> Integer.valueOf(s.replaceAll("\\D", ""))))
            .reduce((a, b) -> a + " " + b).get();
        }
    }
    //by Aisenstein
    
</details>