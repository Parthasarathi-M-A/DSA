### Shortest Time To Reach Target Node
This problem ask you to give the minimum time that would take to
reach from src node to dest node. Here time would be given as edge
weights.
### Input 1 :
n = 9, m = 10

edges = [[0,1],[0,3],[3,4],[4 ,5],[5, 6],[1,2],[2,6],[6,7],[7,8],[6,8]]

start=0

end=7

output: 4
### Input 2:
n = 9, m = 10

edges = [[0,1],[0,3],[3,4],[4 ,5],[5, 6],[1,2],[2,6],[6,7],[7,8],[6,8]]

start=0

end=9

output: -1

### Code:
``` java
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.Queue;
import java.util.Scanner;

public class allPosiableWays {
    public static void main(String[] args) {
        Scanner s=new Scanner(System.in);
        System.out.println("Enter the number of Elements: ");
        int n=s.nextInt();
        System.out.println("Enter the number of vertex: ");
        int v=s.nextInt();
        ArrayList<ArrayList<Integer>>al=new ArrayList<>();
        for(int i=0;i<n;i++)al.add(new ArrayList<>());
        System.out.println("Enter the elements :");
        for(int i=0;i<v;i++){
            int n1=s.nextInt();
            int n2=s.nextInt();
            al.get(n1).add(n2);
            al.get(n2).add(n1);
        }
        System.out.println("Enter the start :");
        int start=s.nextInt();
        System.out.println("Enter the end :");
        int end=s.nextInt();
        System.out.println("minimum path :"+sortPath(al,start,end));
    }
    public static int sortPath(ArrayList<ArrayList<Integer>>al,int start,int end){
        boolean[] vis=new boolean[al.size()];
        Queue<Integer>q=new LinkedList<>();
        int count=0;
        q.add(start);
        vis[start]=true;
        while(!q.isEmpty()){
            int size=q.size();
            for(int i=0;i<size;i++){
                int current=q.poll();
                if(current==end)return count;
                for(int j=0;j<al.get(current).size();j++){
                    if(!vis[al.get(current).get(j)]) {
                        if(al.get(current).get(j)==end)return ++count;
                        q.add(al.get(current).get(j));
                        vis[al.get(current).get(j)]=true;
                    }
                }
            }
            count++;
        }
        return -1;
    }
}

```
