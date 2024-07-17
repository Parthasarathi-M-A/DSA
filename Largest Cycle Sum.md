### Largest Cycle Sum
Given a maze with N cells. Each cell may have multiple entry points but not more than one exit(i.e entry/exit points are unidirectional doors like valves).
You are given an array Edge[] of N integers, where Edge[i] contains the cell number that can be reached from of cell i in one step. Edge[i] is -1 if the ith cell doesn't have an exit. 
The task is to find the largest sum of a cycle in the maze(Sum of a cycle is the sum of the cell indexes of all cells present in that cycle).

Note:The cells are named with an integer value from 0 to N-1. If there is no cycle in the graph then return -1.

Example 1:

Input:
N = 4
Edge[] = {1, 2, 0, -1}
Output: 3
Explanation: 
There is only one cycle in the graph.
(i.e 0->1->2->0)
Sum of the cell index in that cycle 
= 0 + 1 + 2 = 3.
### Code
``` java
import java.util.*;

public class meetingPoint {
    public static void main(String[] args) {
        Scanner s1=new Scanner(System.in);
        int n=s1.nextInt();
        int[] num=new int[n];
        for(int i=0;i<n;i++)num[i]=s1.nextInt();
        int start=s1.nextInt();
        int end=s1.nextInt();
        System.out.printlnlargesSumCycle(n,num));
    }  
public long largesSumCycle(int N, int num[]){
        ArrayList<Integer> element=new ArrayList<>();
        int Max=Integer.MIN_VALUE;
        int anssum=0;
        int count=0;
        int sum=0;
        for(int i=0;i<num.length;i++){
            int currentNum=num[i];
            count=0;
            sum=0;
            while(!element.contains(currentNum)){
                element.add(currentNum);
                sum+=currentNum;
                if(currentNum==-1)break;
                currentNum=num[currentNum];
                count++;
            }
            
            if(currentNum==num[i])if(sum>anssum)anssum=sum;
            element.clear();
        }
        if(anssum==0)return -1;
        return (long)anssum;
    }
}
```
