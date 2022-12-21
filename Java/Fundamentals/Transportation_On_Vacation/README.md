# Transportation on vacation
## Instructions

After a hard quarter in the office you decide to get some rest on a vacation. So you will book a flight for you and your girlfriend and try to leave all the mess behind you.

You will need a rental car in order for you to get around in your vacation. The manager of the car rental makes you some good offers.

Every day you rent the car costs $40. If you rent the car for 7 or more days, you get $50 off your total. Alternatively, if you rent the car for 3 or more days, you get $20 off your total.

Write a code that gives out the total amount for different days(d).

## My thought process

Steps:  
  1. $40 * d
  2. depending on days subtract value.

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class Kata {
      public static int rentalCarCost(int d) {
    
       int total = 0;
    
        if(d < 3){
          total = 40 * d;
        } else if(d < 7){
          total = (40 * d) - 20;
        }else{
          total = (40 * d) - 50;
        }
        return total;
      }
    }
    
</details>
