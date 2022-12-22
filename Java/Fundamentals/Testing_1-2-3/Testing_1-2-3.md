# Testing 1-2-3
## Instructions

Your team is writing a fancy new text editor and you've been tasked with implementing the line numbering.

Write a function which takes a list of strings and returns each line prepended by the correct number.

The numbering starts at 1. The format is n: string. Notice the colon and space in between.

Examples: (Input --> Output)
```
[] --> []
["a", "b", "c"] --> ["1: a", "2: b", "3: c"]
```

## My thought process

Steps:
1. Create new list
2. Iterate old list, copy to new list with added info
3. Return list

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    import java.util.*;

    public class LineNumbering {
        public static List<String> number(List<String> lines) {
            List<String> newList = new ArrayList<String>();
            int c = 1;
            for(String line : lines){  
            newList.add(c+": "+ line);
            c++;
            }
            return newList;
        }
    }
    
</details>
