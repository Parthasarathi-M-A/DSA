### Monkeys and Doors

There are 100 doors, all closed. 

In a nearby cage are 100 monkeys.

The first monkey is let out and runs along the doors opening every one. 

The second monkey is then let out and runs along the doors closing the 2nd, 4th, 6th,…  - all the even-numbered doors. 

The third monkey is let out. He attends only to the 3rd, 6th, 9th,… doors (every third door, in other words), closing any that is open and opening any that is closed, and so on. 

After all 100 monkeys have done their work in this way, what state are the doors in after the last pass?

Answer with the number of open doors.

Answer is an integer.  Just put the number without any decimal places if it’s an integer. If the answer is Infinity, output Infinity.

Feel free to get in touch with us if you have any questions

### Code:
``` java
package JustPay;

import java.util.Scanner;

public class monkeyAndDoors {
    public static void main(String[] args) {
        Scanner s1=new Scanner(System.in);
        System.out.println("Enter the number of doors: ");
        int door=s1.nextInt();
        System.out.println("Enter the number of monkey: ");
        int monkey=s1.nextInt();
        boolean[] doors=new boolean[door];
        for(int i=1;i<=monkey;i++){
            for(int j=0;j<door;j++){
                if((j+1)%i==0)doors[j]=!doors[j];
            }
        }
        int ans=0;
        for(int i=0;i<door;i++)if(doors[i])ans++;
        System.out.println("number of open doors are : "+ans);

    }
}

```
