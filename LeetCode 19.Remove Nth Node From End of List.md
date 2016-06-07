# LeetCode 19.Remove Nth Node From End of List



---
Total Accepted: 111864 Total Submissions: 374606 Difficulty: Easy
Given a linked list, remove the nth node from the end of list and return its head.

For example,

   Given linked list: 1->2->3->4->5, and n = 2.

   After removing the second node from the end, the linked list becomes 1->2->3->5.
Note:
Given n will always be valid.
Try to do this in one pass.

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 * 
 * 
 */
public class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
        ListNode pNote = head;
        ListNode qNote = head;
        
         //如果只有head，直接返回
        if(head.next == null){ 
            head = head.next;
            return head;
        }
        
        //pNote开始遍历链表，同时n递减，当n小于0时，qNote递减，便利结束，qNote为倒数n＋1个节点
        while(pNote != null){ 
            pNote = pNote.next;
            if (n < 0){
                qNote = qNote.next;
            }
            
            n--;
        }
        
        // qNote未能开始遍历，则需要删除的为head
        if ( n == 0){
            head = head.next;
            return head;
        } 
        
        // 删除节点
        pNote = qNote.next; 
        qNote.next = pNote.next;
     
        return head;
    }
}
```

