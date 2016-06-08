# LeetCode 345. Reverse Vowels of a String



---
Total Accepted: 20180 Total Submissions: 57018 Difficulty: Easy
Write a function that takes a string as input and reverse only the vowels of a string.

Example 1:
Given s = "hello", return "holle".

Example 2:
Given s = "leetcode", return "leotcede".



```java
public class Solution {
    public boolean isVowel(char c) {  //这个方法效率远高于 List.contains()方法，去看contains源码
        if('A' <= c && c <= 'Z') c += 'a'-'A';  
        return c=='a' || c=='e' || c=='i' || c=='o' || c=='u';  
    }
    
    public String reverseVowels(String s) {
      
        char[] charArray = s.toCharArray();
        // List<Character> vowels = Arrays.asList('a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U');
        int i = 0, j = charArray.length - 1;
        while (i < j){

            while( i<j && !isVowel( charArray[i]) ) {
                i++;
            }
            
            while( i<j && !isVowel( charArray[j]) ) {
                j--;
            }
           
            char temp = charArray[i]; 
            charArray[i] = charArray[j];
            charArray[j] = temp;
            i++;
            j--;

        }
        
        return String.valueOf(charArray);
    }
}
```




