# LeetCode 344. Reverse String



---
Total Accepted: 34109 Total Submissions: 58119 Difficulty: Easy
Write a function that takes a string as input and returns the string reversed.

Example:
Given s = "hello", return "olleh".


```java
public class Solution {
    public String reverseString(String s) {
        
        char[] charArray = s.toCharArray();
        int i = 0, j = charArray.length - 1;
        for ( i = 0; i < j; i++, j--){
            char temp = charArray[i];
            charArray[i] = charArray[j];
            charArray[j] = temp;
        }
        
        // s = String.valueOf(charArray);
        return String.valueOf(charArray);
    }
}
```




