# Sum of the first nth term of Series
## Instructions

Task:
Your task is to write a function which returns the sum of following series upto nth term(parameter).
```
Series: 1 + 1/4 + 1/7 + 1/10 + 1/13 + 1/16 +...
```
Rules:
* You need to round the answer to 2 decimal places and return it as String.

* If the given value is 0 then it should return 0.00

* You will only be given Natural Numbers as arguments.

Examples:(Input --> Output)
```
1 --> 1 --> "1.00"
2 --> 1 + 1/4 --> "1.25"
5 --> 1 + 1/4 + 1/7 + 1/10 + 1/13 --> "1.57"
```

## My thought process
Steps:
  1. Iterate a loop n times
  2. Sum each time
  3. Out of loop concatenate sum
  4. Return

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class NthSeries {
	
      public static String seriesSum(int n) {

        double sum = 1;
        double denominator = 4; 
        for(int i = 1; i < n; i++){
          sum += (1/denominator);
          denominator+= 3;
        }
        String s = String.format("%.2f", sum);
        return n == 0 ? "0.00" : s;
      }
    }

</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see my answer</summary>

     public class NthSeries {
	
      public static String seriesSum(int n) {
        
        double sum = 0.0;
        for (int i = 0; i < n; i++)
          sum += 1.0 / (1 + 3 * i);
        
        return String.format("%.2f", sum);
        
      }
    }
    //by ptrgags
    
</details>
