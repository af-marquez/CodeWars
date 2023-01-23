# Third Angle of a Triangle
## Instructions

You are given two interior angles (in degrees) of a triangle.

Write a function to return the 3rd.

Note: only positive integers will be tested.

https://en.wikipedia.org/wiki/Triangle

## My thought process
Steps:
  1. Just return the result of the formula

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class ThirdAngle {
        public static int otherAngle(int angle1, int angle2) {
            return 180-angle1-angle2;
        }
    }

</details>