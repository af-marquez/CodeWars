# List Filtering
## Instructions

In this kata you will create a function that takes a list of non-negative integers and strings and returns a new list with the strings filtered out.

Example
```
Kata.filterList(List.of(1, 2, "a", "b")) => List.of(1,2)
Kata.filterList(List.of(1, 2, "a", "b", 0, 15)) => List.of(1,2,0,15)
Kata.filterList(List.of(1, 2, "a", "b", "aasf", "1", "123", 231)) => List.of(1, 2, 231)
```

## My thought process
Steps:
1. Create new list
2. Iterate old list and add to new list in case it's a instance of integer
3. Return new list

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    import java.util.List;
    import java.util.ArrayList;

    public class Kata {
      
      public static List<Object> filterList(final List<Object> list) {
        List<Object> numbersOnly = new ArrayList<Object>();
        for(Object o : list){
          if(o instanceof Integer){
            numbersOnly.add((Integer)o);
          }   
        }
        return numbersOnly;
      }
    }

</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see the answer</summary>

    import java.util.*;
    import java.util.stream.Collectors;

    public class Kata {
      
      public static List filterList(final List<Object> list) {
        return list.stream()
          .filter(e -> e instanceof Integer)
          .collect(Collectors.toList());
      }

    }
    //by DKovalov
    
</details>
