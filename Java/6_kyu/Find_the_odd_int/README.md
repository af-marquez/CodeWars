# Find the odd int
## Instructions

Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

Examples
```[7]``` should return ```7```, because it occurs 1 time (which is odd).
```[0]``` should return ```0```, because it occurs 1 time (which is odd).
```[1,1,2]``` should return ```2```, because it occurs 1 time (which is odd).
```[0,1,0,1,0]``` should return ```0```, because it occurs 3 times (which is odd).
```[1,2,2,3,3,3,4,3,3,3,2,2,1]``` should return ```4```, because it appears 1 time (which is odd).

## My thought process

Steps:
1. Iterate array
2. Add to List the element that is being counted
3. Count to see if appears an odd amount of times
4. If it doesn't, get next element and check if it is on the list 
5. Return num

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    import java.util.*;

    public class FindOdd {
        public static int findIt(int[] a) {

            List<Integer> list = new ArrayList<Integer>();
            int c = 0;
            
            for(int i = 0; i < a.length; i++){
                if(!list.contains(a[i])){
                    list.add(a[i]);
                    for(int j = 0; j < a.length; j++){
                        if(a[i] == a[j] ){
                        c++;
                        }
                    }
                    if(c % 2 != 0){
                    return a[i];
                    }
                }
            }
            return 0;
        }
    }
    
</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see the answer</summary>

    public class FindOdd {
        public static int findIt(int[] A) {
            int xor = 0;
            for (int i = 0; i < A.length; i++) {
                xor ^= A[i];
            }
            return xor;
        }
    }
    //by rbuckley
    
</details>