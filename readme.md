# Ali

```java
package LooPs;

import java.util.Scanner;

/*
This program displays the number of Upper Case letters
 */
public class Exercise_05_50 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter a string");
        String str1 = sc.nextLine();
        int a=0;
        int numberUppercase = 0;
        while(a<str1.length()){
            if(str1.charAt(a)>=65 && str1.charAt(a)<=90){

                ++numberUppercase;
            }
            a++;
        }
        System.out.println("Total Uppercase letter is : " + numberUppercase);
    }
}
```
