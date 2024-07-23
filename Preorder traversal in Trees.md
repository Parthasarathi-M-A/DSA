### Preorder traversal in Trees
Given the root of a binary tree, return the preorder traversal of its nodes' values.

### Input: 
root = [1,null,2,3]

### Output: 
[1,2,3]

### Code :
``` java

public class ArrayTotree {
     Node root;
    static class Node{
        int data;
        Node left;
        Node right;
        Node(int item){
            this.data=item;
            this.left=null;
            this.right=null;
        }
    }

     public static void preOrder(Binarytree.Node root){
        if(root==null)return;
        System.out.println(root.data);
        preOrder(root.left);
        preOrder(root.right);
    }
    }
    public static Node arrayToTree(int arr[],int st,int end){
        if(st>end)return null;
        int mid=(st+end)/2;
        Node curr=new Node(arr[mid]);
        curr.left=arrayToTree(arr,st,mid-1);
        curr.right=arrayToTree(arr,mid+1,end);
        return curr;
    }

    public static void main(String[] args) {
        int[] arr={10,20,30,40,50,60,70};
        Node root=arrayToTree(arr,0,arr.length-1);
        inOrder(root);
    }
}

```
