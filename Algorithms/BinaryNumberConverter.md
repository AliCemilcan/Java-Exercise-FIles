![image](https://github.com/AliCemilcan/Java-Exercise-FIles/blob/master/Algorithms/img/BinaryNumbers.png)
```Java
public class Solution {



    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int number = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");
        scanner.close();

        String[] binar = Integer.toBinaryString(number).split("0");
        String tmp = "";
        for (int i = 0; i < binar.length; i++) {
            for (int k = i + 1; k < binar.length; k++) {
                if (binar[i].length() < binar[k].length()) {
                    binar[i] = tmp;
                    binar[k] = binar[i];
                    tmp = binar[k];
                }
            }


        }
        System.out.println(binar[0].length());
        }
    }

