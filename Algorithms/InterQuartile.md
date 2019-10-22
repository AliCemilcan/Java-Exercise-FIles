![image](https://github.com/AliCemilcan/Java-Exercise-FIles/blob/master/Algorithms/img/InterQuartile.png)
```Java
public class Statistic_Day02 {
    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) {
        Quartiles();

    }

    public static void Quartiles() {
        int size = sc.nextInt();

        int[] array_01 = new int[size];
        int[] array_rep = new int[size];

        int num_elements = 0;
        int median;
        int lowermedian;
        int uppermedian;
        for (int i = 0; i < size; i++) {
            array_01[i] = sc.nextInt();
        }

        sc.nextLine();
        for (int c = 0; c < size; c++) {
            array_rep[c] = sc.nextInt();
            num_elements += array_rep[c];
        }


        int[] final_array = new int[num_elements];

        int dataset = 0;
        for (int z = 0; z < size; z++) {
            for (int i = 0; i < array_rep[z]; i++) {
                final_array[dataset] = array_01[z];
                dataset++;
            }

        }
        Arrays.sort(final_array);
        size = final_array.length;


        if (size % 2 == 0) {

            median = (final_array[((num_elements / 2) - 1)] + final_array[(num_elements / 2)]) / 2;
            if ((size / 2) % 2 != 0) {
                lowermedian = final_array[(num_elements / 4)];
                uppermedian = final_array[((num_elements * 3) / 4)];


            } else {
                lowermedian = (final_array[(num_elements / 4)] + final_array[(num_elements / 4) - 1]) / 2;
                uppermedian = (final_array[(((num_elements * 3) / 4) - 1)] + final_array[((num_elements * 3) / 4)]) / 2;

            }


            System.out.println(Double.valueOf(uppermedian - lowermedian));
        } else {
            System.out.println("Tek sayilari icin islem ");
            median = final_array[(num_elements / 2)];

            if ((size / 2) % 2 != 0) {
                lowermedian = final_array[(num_elements / 4)];
                uppermedian = final_array[((num_elements * 3) / 4)];
            } else {
                lowermedian = (final_array[((num_elements / 4))] + final_array[(num_elements / 4) - 1]) / 2;

                uppermedian = (final_array[((num_elements * 3) / 4)] + final_array[((num_elements * 3) / 4) + 1]) / 2;
            }


            double q3 = (uppermedian - lowermedian);

            System.out.println(Double.valueOf(uppermedian - lowermedian));

        }

    }


}
