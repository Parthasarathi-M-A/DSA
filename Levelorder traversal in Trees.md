### Levelorder traversal in Trees

Given the root of a binary tree, return the level order traversal of its nodes' values. (i.e., from left to right, level by level).
### Input:
root = [3,9,20,null,null,15,7]

### Output:

3,9,20,15,7

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

   static ArrayList<Binarytree.Node> al=new ArrayList<>();
    static int index=0;
    public static void levelOrder(Binarytree.Node root){
        if(al.isEmpty())al.add(root);
        if(root.left==null&&root.right==null)return;
        if(root.left!=null)al.add(root.left);
        if(root.right!=null)al.add(root.right);
        levelOrder(al.get(++index));
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
