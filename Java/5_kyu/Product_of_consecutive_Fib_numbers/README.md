# Product of consecutive Fib numbers
## Instructions

The Fibonacci numbers are the numbers in the following integer sequence (Fn):

```0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, ...```

such as

```F(n) = F(n-1) + F(n-2) with F(0) = 0 and F(1) = 1.```

Given a number, say prod (for product), we search two Fibonacci numbers F(n) and F(n+1) verifying

```F(n) * F(n+1) = prod.```

Your function productFib takes an integer (prod) and returns an array:

```[F(n), F(n+1), true] or {F(n), F(n+1), 1} or (F(n), F(n+1), True)```
depending on the language if F(n) * F(n+1) = prod.

If you don't find two consecutive F(n) verifying ```F(n) * F(n+1) = prod``` you will return

```[F(n), F(n+1), false] or {F(n), F(n+1), 0} or (F(n), F(n+1), False)```
F(n) being the smallest one such as F(n) * F(n+1) > prod.

Some Examples of Return:
(depend on the language)
```
productFib(714) # should return (21, 34, true), 
                # since F(8) = 21, F(9) = 34 and 714 = 21 * 34

productFib(800) # should return (34, 55, false), 
                # since F(8) = 21, F(9) = 34, F(10) = 55 and 21 * 34 < 800 < 34 * 55
-----
productFib(714) # should return [21, 34, true], 
productFib(800) # should return [34, 55, false], 
-----
productFib(714) # should return {21, 34, 1}, 
productFib(800) # should return {34, 55, 0},        
-----
productFib(714) # should return {21, 34, true}, 
productFib(800) # should return {34, 55, false},
```
Note:
You can see examples for your language in "Sample Tests".

## My thought process

Steps:
1. Calculate fibbonacci
2. Iterate while result has not been found
3. Return long array
Note: this won't be the prettiest code

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class ProdFib {
  
      public static long fibonacci(long n){
        if(n == 0){
            return 0;
        }
        if(n == 1 || n == 2){
            return 1;
        }

        long prev = 0;
        long prevprev = 1;
        long current = 1;

        for(int i = 3; i <= n; i++) {
            current = prev + prevprev;
            prevprev = prev;
            prev = current;
        }
        return current;
    }
      
      public static long[] productFib(long prod) {
        long actualProd = 0;
        long i = 0;
        long fnplusone = 0;
        long fn = 0;
        while(actualProd < prod){
          fn = fibonacci(i);
          fnplusone = fibonacci(i+1);
          actualProd = fn * fnplusone;
          i++;
        }
        long[] toReturn = {fn, fnplusone, actualProd == prod ? 1 : 0};
        return toReturn;
      }
    }
    
</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see the answer</summary>

    public class ProdFib { // must be public for codewars	
	
      public static long[] productFib(long prod) {
        long a = 0L;
        long b = 1L;
        while (a * b < prod) {
          long tmp = a;
          a = b;
          b = tmp + b;
        }
        return new long[] { a, b, a * b == prod ? 1 : 0 };
      }
    }
    //by student003
    
</details>
