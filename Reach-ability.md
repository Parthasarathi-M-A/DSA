### Reach-ability 
This problem asks you to check for a given static graph if a node dest is
reachable from a given node src .
Input 1:
23
4 4 1 4 13 8 8 8 0 8 14 9 15 11 -1 10 15 22 22 22 22 22 21
2
0
Output:true  

Input 2:
23
4 4 1 4 13 8 8 8 0 8 14 9 15 11 -1 10 15 22 22 22 22 22 21
2
22
Output:false
### Code 
```java
import java.util.ArrayList;
import java.util.Scanner;

public class reachablility {
    public static void main(String[] args) {
        Scanner s1=new Scanner(System.in);
        int n=s1.nextInt();
        int[] num=new int[n];
        for(int i=0;i<n;i++)num[i]=s1.nextInt();
        int start=s1.nextInt();
        int end=s1.nextInt();
        System.out.println(isReachable(num,start,end));
    }
    public static boolean isReachable(int[] num,int start,int end){
        ArrayList<Integer>al=new ArrayList<>();
        int currentElement=start;
        while(!al.contains(currentElement)){
            if(currentElement==-1)break;
            al.add(currentElement);
            if(num[currentElement]==end)return true;
            currentElement=num[currentElement];
        }
        return false;
    }
}

```
