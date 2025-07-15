## import java.util.*;
````java[]

class Node{
    int data;
    Node next;
    Node prev;
    Node(int data){
        this.data=data;
        this.next=null;
        this.prev=null;
    }
}
class Dll{
    Node head,tail;
    public void insertatbegin(int data){
        Node newnode=new Node(data);
        if(head==null){
            head=newnode;
            tail=newnode;
        }
        else{
            newnode.next=head;
            head.prev=newnode;
            head=newnode;
        }
    }
    public void insertatend(int data){
        Node newnode=new Node(data);
        if(tail==null){
            head=newnode;
            tail=newnode;
        }
        else{
            tail.next=newnode;
            newnode.prev=tail;
            tail=newnode;
        }
    }
    public void deleteatbegin(){
        if(head==tail){
            head=tail=null;
        }
        else{
            head=head.next;
            head.prev=null;
        }
    }
     public void deleteatend(){
        if(head==tail){
            head=tail=null;
        }
        else{
          tail=tail.prev;
          tail.next=null;
        }
    }
    public void display(){
        Node temp=head;
        while(temp!=null)
        {
            System.out.print(temp.data+" ");
            temp=temp.next;
        }
    }
    public void reverse(){
        Node temp=tail;
        while(temp!=null)
        {
            System.out.print(temp.data+" ");
            temp=temp.prev;
        }
    }
    public int count(){
        Node temp=head;
        int len=0;
        while(temp!=null)
        {
            len++;
            temp=temp.next;
        }
        return len;
    }
    public boolean search(int target){
        Node temp=head;
        while(temp!=null){
            if(temp.data==target){
                return true;
            }
            temp=temp.next;
        }
        return false;
    }
    public void findindex(int ele)
    {
        int index=0;
        Node temp=head;
        boolean found=false;
        while(temp!=null){
            if(temp.data==ele){
              System.out.println("Element " + ele + " found at index: " + index);
              found=true;
                break;
            }
            index++;
            temp=temp.next;
        }
        if(!found){
            System.out.println("Element " + ele + " Not found" );
        }
        
    }
    
}
public class Main
{
	public static void main(String[] args) {
        Scanner s=new Scanner(System.in);
        Dll obj=new Dll();
        while(true){
            int val=s.nextInt();
            if(val==-1){
                break;
            }
           // obj.insertatbegin(val);
             obj.insertatend(val);
        }
        System.out.println("After insert the element ");
        obj.display();
        //System.out.println("After delete the element ");
       // obj.deleteatbegin();
        //obj.deleteatend();
         System.out.println("\nAfter reverse the element ");
        obj.reverse();
        System.out.println("\nCount or length of the node in the list "+obj.count());
        int k=s.nextInt();
        /*boolean found=obj.search(k);
        if(found){
            System.out.println("Element found");
        }
        else{
            System.out.println("Element not found");
        }*/
        obj.findindex(k);
	}
}

`````

