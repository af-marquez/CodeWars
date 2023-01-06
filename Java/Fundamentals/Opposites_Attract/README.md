# Opposites Attract
## Instructions

Timmy & Sarah think they are in love, but around where they live, they will only know once they pick a flower each. If one of the flowers has an even number of petals and the other has an odd number of petals it means they are in love.

Write a function that will take the number of petals of each flower and return true if they are in love and false if they aren't.

## My thought process
Steps:
1. Sum Numbers given to us
2. See if it's multiple of 2.
3. Return Bollean.

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class OppositesAttract {

      public static boolean isLove(final int flower1, final int flower2) {
        return (flower1+flower2)% 2 != 0 ? true : false;
      }
      
    }

</details>
