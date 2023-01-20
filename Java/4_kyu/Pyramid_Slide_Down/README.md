# Pyramid Slide Down
## Instructions

Lyrics...
Pyramids are amazing! Both in architectural and mathematical sense. If you have a computer, you can mess with pyramids even if you are not in Egypt at the time. For example, let's consider the following problem. Imagine that you have a pyramid built of numbers, like this one here:
```
   /3/
  \7\ 4 
 2 \4\ 6 
8 5 \9\ 3
```
Here comes the task...
Let's say that the 'slide down' is the maximum sum of consecutive numbers from the top to the bottom of the pyramid. As you can see, the longest 'slide down' is 3 + 7 + 4 + 9 = 23

Your task is to write a function that takes a pyramid representation as argument and returns its' largest 'slide down'. For example:

```
* With the input `[[3], [7, 4], [2, 4, 6], [8, 5, 9, 3]]`
* Your function should return `23`.
```
By the way...
My tests include some extraordinarily high pyramids so as you can guess, brute-force method is a bad idea unless you have a few centuries to waste. You must come up with something more clever than that.

## My thought process

Steps:

  After a long time and bit research the easiest away to approach this problem should be something like this 
  1. We should start from the base of the pyramid (ignoring the first level) going all the way to the top
  2. On each element of the current level, we put sum of the element with the biggest adjacent number of the row below
  3. Repeat this process all the way to the [0][0] where will be the final sum
  4. Return int with sum

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    class LongestSlideDown {
        public static int longestSlideDown(int[][] pyramid) {
            for (int i = pyramid.length - 2; i >= 0; i--) {
                for (int j = 0; j < pyramid[i].length; j++) {
                    pyramid[i][j] += Math.max(pyramid[i + 1][j], pyramid[i + 1][j + 1]);
                }
            }
            return pyramid[0][0];
        }
    }
    
</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see the answer</summary>

    public class LongestSlideDown {

        public static int longestSlideDown(int[][] p) {
            
            for (int i = p.length - 1; i >= 1; i--)
              for (int j = 0; j < i; j++)            
                p[i - 1][j] += Math.max(p[i][j], p[i][j + 1]);
            
            return p[0][0];
        }
    }
    //by dgmagno
    
</details>
