# LeetCode 61. Rotate List



---

Total Accepted: 71150 Total Submissions: 308672 Difficulty: Medium
Given a list, rotate the list to the right by k places, where k is non-negative.

For example:
Given 1->2->3->4->5->NULL and k = 2,
return 4->5->1->2->3->NULL.

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
public class Solution {
    public ListNode rotateRight(ListNode head, int k) {
        ListNode pNote = head;
        ListNode qNote = head;
        int length = 0;
        
        if(head == null || k == 0){  //如果只有一个head，则返回head
            return head;
        }

//pNote从head开始遍历整个链表，length记录表长度，length超过n之后，qNote开始遍历。这样能保证qNode是需要寻找的节点的前一个节点

        while(pNote.next != null){ 
            length ++;    
            pNote = pNote.next;
            if (length > k){
                qNote = qNote.next;
            }

        }
        
        length = length + 1;
        
        // 根据k和length的大小进行判断
        if ( k > length) {//递归求解
            
            k = k % length;
            return rotateRight(head, k);
            
        } else  if ( k == length){
            
            return head;
            
        } else {
           
            ListNode newhead = qNote.next;
            qNote.next = null;
            pNote.next = head;
    
            return newhead;
        }
        
      
    }
}
```




