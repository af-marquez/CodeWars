# Simple Pig Latin
## Instructions

Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.

Examples
```
pigIt('Pig latin is cool'); // igPay atinlay siay oolcay
pigIt('Hello world !');     // elloHay orldway !
```

## My thought process

Steps:
1. Put words separated into an array
2. Put word in char array
2. Handle words to reposition first letter and add suffix
3. Return String

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class PigLatin {
  
        public static String pigIt(String str) {
            
            String[] words = str.split(" ");
            char firstChar;
            String newString = "";
            String newWord = "";
            int i = 0;
            int j = 0;
            
            //iterate all words
            for(i = 0; i < words.length; i++){
                
                //adjust array size considering extra letters
                //if it's punctuation mark
                if(words[i].charAt(0) >= 33 && words[i].charAt(0) <= 64 && words[i].length() == 1){
                  char[] currentWordChars = {words[i].charAt(0)};
                  //convert word to string
                  newWord = String.valueOf(currentWordChars);
                }else{
                  char[] currentWordChars = new char[words[i].length() + 2];    
                  //save first char of the word
                  firstChar = words[i].charAt(0);
                  //create new word
                for(j = 0; j < words[i].length() - 1; j++ ){    
                    currentWordChars[j] = words[i].charAt(j + 1);
                }
                // add newfinal chars
                currentWordChars[j] = firstChar;
                currentWordChars[j + 1] = 'a';
                currentWordChars[j + 2] = 'y';
                //convert word to string
                newWord = String.valueOf(currentWordChars);
             }

            newString = newString + newWord;        
            //in case it needs space between words
            if(i != words.length - 1){
            newString = newString + " ";
            }
          }
          return newString;
        }
    }
    
</details>

## The Best answer to this problem

<details> 
  <summary>Click here to see my answer</summary>

    public class PigLatin {
        public static String pigIt(String str) {
            return str.replaceAll("(\\w)(\\w*)", "$2$1ay");
        }
    }
    //by Blind4Basics
    
</details>
