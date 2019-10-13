![image](https://github.com/AliCemilcan/Java-Exercise-FIles/blob/master/Algorithms/img/HashMap.png)

```Java
 public static void GetKeyValues() {

        Map<String, String> list = new HashMap<>();
        int size = sc.nextInt();
        sc.nextLine();
        String a = "";
        String[] values_02 = new String[size];
        for (int i = 0; i < size; i++) {
            a = sc.nextLine();

            String values[] = a.split(" ");
            list.put(values[0], values[1]);

        }
        for (int k = 0; k < size; k++) {
            values_02[k] = sc.nextLine();
        }
        for (int i = 0; i < size; i++) {

            if (list.containsKey(values_02[i])) {
                System.out.print(values_02[i] + "=" + list.get(values_02[i]));
            } else {
                System.out.print("Not found");
            }

            System.out.println();
        }


    }
