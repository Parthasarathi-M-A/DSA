### sorting two Array 
Given a K sorted array, Merge them in a sorted single 1d array in the least
complexity
### Input: 
K = 3, N = 4, arr = { {1, 3, 5, 7}, {2, 4, 6, 8}, {0, 9, 10, 11}}
### Output: 
0 1 2 3 4 5 6 7 8 9 10 11 
### Explanation: 
The output array is a sorted array that contains all the elements of the input matrix.
``` java
import java.util.ArrayList;
import java.util.Scanner;

public class MergeKSortedArray {
    public ArrayList<Integer> sort(int[][]array,int k){
        ArrayList<Integer>list=new ArrayList<>();
        int i=0;
        int[]index=new int[k];
        while(i<k*k){
            int small=Integer.MAX_VALUE;
            int smallIndex=0;
            for(int j=0;j<k;j++){
                if(index[j]<k) {
                    if (array[j][index[j]] < small) {
                        small = array[j][index[j]];
                        smallIndex = j;
                    }
                }
            }
            index[smallIndex]++;
            list.add(small);
            i++;
        }
        return list;
    }
    public static void main(String[] args) {
        Scanner ip=new Scanner(System.in);
        int k=ip.nextInt();
        int n=ip.nextInt();
        int[][]array=new int[k][n];
        for(int i=0;i<k;i++)
            for(int j=0;j<n;j++) array[i][j]=ip.nextInt();
        System.out.println(new MergeKSortedArray().sort(arr, arr.length));
    }
}
```
