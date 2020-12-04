# LinkedList

package com.company;

class ListNode {
    public int val;
    public ListNode next;
    public ListNode(int value){
        this.val = value;
    }
}

public class LinkedList {
    ListNode dummy;
    public LinkedList(){
        dummy = new ListNode(-1);
    }

    public int get(int location){
        ListNode cur = dummy.next;

        for(int i = 0; i < location; ++i){
            cur = cur.next;
        }
        return cur.val;
    }

    public void add(int location, int val){
        ListNode pre = dummy;

        for(int i = 0; i < location; ++i){
            pre = pre.next;
        }

        ListNode node = new ListNode(val);

        node.next = pre.next;
        pre.next = node;

    }

    public boolean contains(int val){
        ListNode head = dummy.next;

        while(head != null){
            if(head.val == val){
                return true;
            }
            head = head.next;
        }
        return false;

    }

    public void remove(int location){
        ListNode pre = dummy;

        for(int i = 0; i < location; ++i){
            pre = pre.next;
        }
        pre.next = pre.next.next;
    }
}
