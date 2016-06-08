# LeetCode 27. Remove Element



---
Total Accepted: 122406 Total Submissions: 356377 Difficulty: Easy
Given an array and a value, remove all instances of that value in place and return the new length.

Do not allocate extra space for another array, you must do this in place with constant memory.

The order of elements can be changed. It doesn't matter what you leave beyond the new length.

Example:
Given input array nums = [3,2,2,3], val = 3

Your function should return length = 2, with the first two elements of nums being 2.


```java
public class Solution {
    public int removeElement(int[] nums, int val) {
        // if (nums.length == 0) 
        //     return 0;
            
        // int i = 0, j = nums.length - 1;
    
        // while ( i <= j ){
        //     if ( nums[i] == val ){
        //         int temp = nums[i];
        //         nums[i] = nums[j];
        //         nums[j] = temp;
        //         j--;
        //     } else {
        //         i++;
        //     }
        // }
        
        // return j + 1;
        
        int newIndex = 0;  
        for (int oldIndex = 0; oldIndex < nums.length; ++oldIndex) {  
            if (nums[oldIndex] != val) {  
                nums[newIndex] = nums[oldIndex];//可以覆盖val所占空间
                newIndex++;
            }   
        }  
        return newIndex;  
        
    }
}
```




