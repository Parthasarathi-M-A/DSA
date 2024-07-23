### characters to be removed to get a string
Number of characters to be removed to convert the given string to “Juspay”.

### Input:
Justapay
### Output :
2

### Code :
``` java
import java.util.Scanner;

public class StringToReduce {
    public static void main(String[] args) {
        Scanner s1=new Scanner(System.in);
        System.out.println("Enter the string");
        String s=s1.nextLine().toLowerCase();
        System.out.println(juspayRepeat(s));

    }
    public static int juspayRepeat(String s){
        char[] ca=s.toCharArray();
        char[]jp="juspay".toCharArray();
        for(int i=0;i<jp.length;i++){
            for(int j=0;j<ca.length;j++){
                if(ca[j]==jp[i]){
                    ca[j]='1';
                    jp[i]='1';
                    break;
                }
            }
        }
        for(int i=0;i<jp.length;i++)if(jp[i]!='1')return -1;
        int count=0;
        for(int i=0;i<ca.length;i++)if(ca[i]=='1')count++;
        return (ca.length-count);
    }

}

```
