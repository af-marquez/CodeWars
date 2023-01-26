# Pick peaks
## Instructions

In this kata, you will write a function that returns the positions and the values of the "peaks" (or local maxima) of a numeric array.

For example, the array ```arr = [0, 1, 2, 5, 1, 0]``` has a peak at position 3 with a value of 5 (since arr[3] equals 5).

The output will be returned as a ``Map<String,List>with two key-value pairs:"pos"and"peaks". If there is no peak in the given array, simply return ```{"pos" => [], "peaks" => []}` ```.

Example: ```pickPeaks([3, 2, 3, 6, 4, 1, 2, 3, 2, 1, 2, 3]) ```should return ```{pos: [3, 7], peaks: [6, 3]}``` (or equivalent in other languages)

All input arrays will be valid integer arrays (although it could still be empty), so you won't need to validate the input.

The first and last elements of the array will not be considered as peaks (in the context of a mathematical function, we don't know what is after and before and therefore, we don't know if it is a peak or not).

Also, beware of plateaus !!! ```[1, 2, 2, 2, 1]``` has a peak while ```[1, 2, 2, 2, 3]``` and ```[1, 2, 2, 2, 2]``` do not. In case of a plateau-peak, please only return the position and value of the beginning of the plateau. For example: pickPeaks```([1, 2, 2, 2, 1])``` returns ```{pos: [1], peaks: [2]}``` (or equivalent in other languages)

Have fun!

## My thought process

Steps:
1. Iterate array in case it is not empty, else return
2. Check if current num is bigger than prev and next num
3. Check if it is a plateau peak
3. In case it is, add to map
4. In case it is not, continue iteration
5. Return map

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    import java.util.*;

    public class PickPeaks {
        
        public static Map<String,List<Integer>> getPeaks(int[] arr) {
            
          Map<String, List<Integer>> map = new HashMap<>();
          ArrayList<Integer> arrayPos = new ArrayList<>();
          ArrayList<Integer> arrayPeak = new ArrayList<>();
          
          int prev = 0;
          int next = 0;
          int j = 0;
          
          for(int i = 1; i < arr.length - 1;i++){
            prev = arr[i - 1];
            next = arr[i + 1];
            if(arr[i] > prev && arr[i] > next){
              arrayPos.add(i);
              arrayPeak.add(arr[i]);
            } else if(arr[i] > prev && arr[i]== next){
                j = i;        
                while(i+1 < arr.length-1 && arr[i]== arr[i + 1]){
                  i++;
                }
                if(arr[i]>arr[i + 1]){
                  arrayPos.add(j);
                  arrayPeak.add(arr[j]);
                }  
              }
          }
          map.put("pos", arrayPos);
          map.put("peaks", arrayPeak);
          return map;
        }
    }
    
</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see the answer</summary>

    import java.util.*;

    public class PickPeaks {
        
        public static Map<String,List<Integer>> getPeaks(int[] arr) {
            
            Map<String,List<Integer>> ans = new HashMap<String,List<Integer>>() {{
                put("pos",   new ArrayList<Integer>() );
                put("peaks", new ArrayList<Integer>() );
            }};
            int posMax = 0;
            boolean matchAsc = false;
            
            for (int i = 1 ; i < arr.length ; i++) {
                if (arr[i-1] < arr[i]) {
                    matchAsc = true;
                    posMax = i;
                }
                if (matchAsc && arr[i-1] > arr[i]) {
                    matchAsc = false;
                    ans.get("pos").add(posMax);
                    ans.get("peaks").add(arr[posMax]);
                }
            }
            return ans;
        }
    }
    //by Blind4Basics
    
</details>
