### Nearest Meeting Cell
Problem Description :
You are given a maze with N cells. Each cell may have multiple entry points but not more than one
exit (i.e. entry/exit points are unidirectional doors like valves). The cells are named with an integer
from 0 to N-1.
You have to find :
Nearest meeting cell : Given any two cells - C1, C2, find the closest cell Cm that can be reached
from both C1 and C2.
INPUT FORMAT :
1. The first line contains the number of cells N.
2. The second line has a list of N values of the edge[ ] array, where edge[i] conatins the cell
number that can be reached from cell 'i' in one step. edge[i] is -1 if the ith doesn't have an
exit.
3. Third line for each testcase contains two cell numbers whose nearest meeting cell needs to
be found. (return -1 if there is no meeting cell from two given cells)
OUTPUT FORMAT :
Output a single line that denotes the nearest meeting cell (NMC).
Sample Input :
23
4 4 1 4 13 8 8 8 0 8 14 9 15 11 -1 10 15 22 22 22 22 22 21
9 2
Sample Output :
4
### Code
``` java
package JustPay;

import java.util.ArrayList;
import java.util.Scanner;

public class meetingPoint {
    public static void main(String[] args) {
        Scanner s1=new Scanner(System.in);
        int n=s1.nextInt();
        int[] num=new int[n];
        for(int i=0;i<n;i++)num[i]=s1.nextInt();
        int start=s1.nextInt();
        int end=s1.nextInt();
        System.out.println(meeting(num,start,end));
    }
    public static int meeting(int [] num,int start,int end){
        ArrayList<Integer>go=new ArrayList<>();
        ArrayList<Integer>come=new ArrayList<>();
        int currenElement=start;
        while(!go.contains(end)){
            go.add(currenElement);
            currenElement=num[currenElement];
        }
        go.remove(go.size()-1);
        currenElement=end;
        while ((!go.contains(currenElement))){
            come.add(currenElement);
            currenElement=num[currenElement];
        }
        come.add(currenElement);
        for(int i=0;i<go.size();i++)if(come.contains(go.get(i)))return go.get(i);
        return -1;
    }
}

```
