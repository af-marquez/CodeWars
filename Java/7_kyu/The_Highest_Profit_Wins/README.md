# The highest profit wins!
## Instructions

Write a function that returns both the minimum and maximum number of the given list/array.

Examples (Input --> Output)

```
[1,2,3,4,5] --> [1,5]
[2334454,5] --> [5,2334454]
[1]         --> [1,1]
```
Remarks
All arrays or lists will always have at least one element, so you don't need to check the length. Also, your function will always get an array or a list, you don't have to check for null, undefined or similar.

## My thought process
Steps:
  1. Iterate array
  2. Gather lowest and highest number
  3. Return new array

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    class MinMax {
        public static int[] minMax(int[] arr) {
          
          int min = arr[0];
          int max = arr[0];
          
          for(int i = 1; i < arr.length; i++){
            if(arr[i]> max){
              max = arr[i];
            }
            if(arr[i]< min){
              min = arr[i];
            }
          }
          int [] toReturn = {min, max};
          return toReturn;
        }
    }

</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see my answer</summary>

    import java.util.Arrays;

      class MinMax {
          public static int[] minMax(int[] arr) {
              // Your awesome code here
              Arrays.sort(arr);
              return new int[]{arr[0],arr[arr.length-1]};
          }
      }
    //by GoinDown4Real
    
</details>
