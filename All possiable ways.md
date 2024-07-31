### All possiable ways
You are in a city that consists of n intersections numbered from 0 to n - 1 with bi-directional roads between some intersections.
The inputs are generated such that you can reach any intersection from any other intersection and that there is at most one road between any two intersections.

You are given an integer n and a 2D integer array ‘roads’ where roads[i] = [ui, vi, timei] means that there is a road between intersections ui and vi that takes timei minutes to travel.
You want to know in how many ways you can travel from intersection 0 to intersection n - 1 in the shortest amount of time.

### Input :
Enter number of Nodes : 
6

Enter number of roads : 
8

Enter the paths : 

0 5 8

0 2 2

0 1 1

1 3 3

1 2 3

2 5 6

3 4 2

4 5 2

Enter the start point : 
1

Enter the end point : 
5

### Output :
Path: 1 0 5  weight: 9

Path: 1 0 2 5  weight: 9

Path: 1 3 4 5  weight: 7

Path: 1 2 0 5  weight: 13

Path: 1 2 5  weight: 9

### Code :
``` java
package graph;


import java.util.ArrayList;
import java.util.LinkedList;
import java.util.Queue;
import java.util.Scanner;

public class FindPath {
    static ArrayList<ArrayList<way>>al=new ArrayList();
    public static void main(String[] args){
        Scanner s1=new Scanner(System.in);
        System.out.println("Enter number of Nodes : ");
        int n=s1.nextInt();
        System.out.println("Enter number of roads : ");
        int m=s1.nextInt();
        System.out.println("Enter the paths : ");
        for(int i=0;i<n;i++)al.add(new ArrayList<way>());
        for(int i=0;i<m;i++){
            int s=s1.nextInt();
            int e=s1.nextInt();
            int w=s1.nextInt();
            al.get(s).add(new way(e,w));
            al.get(e).add(new way(s,w));
        }
        System.out.println("Enter the start point : ");
        int start=s1.nextInt();
        System.out.println("Enter the end point : ");
        int end=s1.nextInt();
        printWays(start,end);
    }
    public static void printWays(int start,int end){
        path("",start,end,0);
    }
    public static void path(String ans,int start,int end,int weight){
        if(ans.contains(start+""))return;
        if(start==end){
            System.out.println("Path: "+ans+start+"  weight: "+weight);
            return;
        }
        ans+=start+" ";
        Queue<way>alst=new LinkedList<>();
        for(int i=0;i<al.get(start).size();i++)alst.add(al.get(start).get(i));
        while(!alst.isEmpty()) path(ans,alst.peek().next,end,weight+alst.poll().dis);
    }
}
class way{
    int next;
    int dis;
    public way(int next,int dis){
        this.next=next;
        this.dis=dis;
    }
}

```
