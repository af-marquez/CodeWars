###My answer
Implement a function that adds two numbers together and returns their sum in binary. The conversion can be done before, or after the addition.

The binary number returned should be a string.

Examples:(Input1, Input2 --> Output (explanation)))
```
1, 1 --> "10" (1 + 1 = 2 in decimal or 10 in binary)
5, 9 --> "1110" (5 + 9 = 14 in decimal or 1110 in binary)
```
##My thought process
Steps:
1- Sum Numbers
2-Divide the number by 2 keeping notice of the quotient 
and the remainder.Continue dividing the quotient by 2 
until you get a quotient of zero.
3-Return string in reverse order.

##My answer

```
public class Kata{
  
  public static String binaryAddition(int a, int b){

    int sum = a+b;
    String numInBinary = "";

    do {
      numInBinary = numInBinary + (sum % 2);
      sum = sum / 2;
  } while (sum != 0);
    
    return new StringBuilder(numInBinary).reverse().toString();
  }
}
```