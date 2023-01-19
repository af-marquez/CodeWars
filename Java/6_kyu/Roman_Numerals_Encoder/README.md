# Roman Numerals Encoder

## Instructions

Create a function taking a positive integer as its parameter and returning a string containing the Roman Numeral representation of that integer.

Modern Roman numerals are written by expressing each digit separately starting with the left most digit and skipping any digit with a value of zero. In Roman numerals 1990 is rendered: 1000=M, 900=CM, 90=XC; resulting in MCMXC. 2008 is written as 2000=MM, 8=VIII; or MMVIII. 1666 uses each Roman symbol in descending order: MDCLXVI.

Example:

conversion.solution(1000); //should return "M"
Help:

Symbol    Value
I          1
V          5
X          10
L          50
C          100
D          500
M          1,000
Remember that there can't be more than 3 identical symbols in a row.

More about roman numerals - http://en.wikipedia.org/wiki/Roman_numerals

## My thought process

Steps:
    1. Use remainder to separate each digit
    2. Depending on which house belongs (units, hundreds, etc)
    Convert to roman numeral
    3. Return reversed string

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class Conversion {

        public String solution(int n) {
        
        String romanNumerals = "";
        int remainder;
        int houseCounter = 1;
        
        while( n > 0){
            
            remainder = n % 10;
            
            switch(houseCounter) {
            case 1: //units
                switch(remainder){
                case 1:
                    romanNumerals += "I";
                break;
                case 2:
                    romanNumerals += "II";
                break;
                case 3:
                    romanNumerals += "III";
                break;
                case 4:
                romanNumerals += "VI";
                break;
                case 5:
                romanNumerals += "V";
                break;
                case 6:
                romanNumerals += "IV";
                break;
                case 7:
                romanNumerals += "IIV";
                break;
                case 8:
                romanNumerals += "IIIV";
                break;
                case 9:
                romanNumerals += "XI";
                break;
                }  
            break;
            case 2: //dozens
                switch(remainder){
                case 1:
                    romanNumerals += "X";
                break;
                case 2:
                    romanNumerals += "XX";
                break;
                case 3:
                    romanNumerals += "XXX";
                break;
                case 4:
                romanNumerals += "LX";
                break;
                case 5:
                romanNumerals += "L";
                break;
                case 6:
                romanNumerals += "XL";
                break;
                case 7:
                romanNumerals += "XXL";
                break;
                case 8:
                romanNumerals += "XXXL";
                break;
                case 9:
                romanNumerals += "CX";
                break;
                }  
            break;
            case 3: //hundreds
                switch(remainder){
                case 1:
                    romanNumerals += "C";
                break;
                case 2:
                    romanNumerals += "CC";
                break;
                case 3:
                    romanNumerals += "CCC";
                break;
                case 4:
                romanNumerals += "DC";
                break;
                case 5:
                romanNumerals += "D";
                break;
                case 6:
                romanNumerals += "CD";
                break;
                case 7:
                romanNumerals += "CCD";
                break;
                case 8:
                romanNumerals += "CCCD";
                break;
                case 9:
                romanNumerals += "MC";
                break;
                }  
            break;
            case 4: //thousands
                switch(remainder){
                case 1:
                    romanNumerals += "M";
                break;
                case 2:
                    romanNumerals += "MM";
                break;
                case 3:
                    romanNumerals += "MMM";
                break;
                }
            default:
                // code block
            }
            
            n = n / 10; 
            houseCounter++;
        }
        
            return new StringBuilder(romanNumerals).reverse().toString();
        }
    }
    
</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see my answer</summary>

     public class Conversion {

        public String solution(int n) {
            final String[] digit = {"", "I", "II", "III", "IV", "V", "VI", "VII",
                                    "VIII", "IX"};
            final String[] ten = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX",
                                    "LXXX", "XC"};
            final String[] hundred = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC",
                                    "DCCC", "CM"};
            final String[] thousand = {"", "M", "MM", "MMM"};
            
            String result="";
            result = thousand[n/1000] + hundred[n%1000/100] + ten[n%100/10] +
                    digit[n%10];
            return result;
        }
    }
    //by quangdao
    
</details>