![image](https://github.com/AliCemilcan/Java-Exercise-FIles/blob/master/Algorithms/img/MeanMedianMOde.png)
```Java
public class Solution {

    public static void main(String[] args) {
       
        Scanner sc = new Scanner(System.in);
        
        int size = sc.nextInt();
        sc.nextLine();
        int[] array_01 = new int[size];

        String[] arrstr = sc.nextLine().split(" ");
        for (int i = 0; i < size; i++) {
            array_01[i] = Integer.parseInt(arrstr[i]);
        }
        int sum = 0;
        for (int a : array_01) {
            sum += a;

        }
        //  DecimalFormat df2 = new DecimalFormat("#.##");
        // float mean = sum/size;
        // System.out.println(df2.format(mean));
        float summ = (float) sum/size;
        System.out.printf("%.1f", summ);
        Arrays.sort(array_01);
        int mid;
        int mid_02;
        if (size % 2 != 0) {
            mid = size / 2;
            mid_02 = mid + 1;
            System.out.println((array_01[mid]+array_01[mid_02])/2);
        } else {
            mid = size / 2;
            mid_02 = mid - 1;
            System.out.println((array_01[mid]+array_01[mid_02])/2);
        }
        Map<Integer,Integer>map = new HashMap<>();
        for(int key:array_01){
            if(map.containsKey(key)){
                int occurence = map.get(key);
                occurence++;
                map.put(key,occurence);
            }else{
                map.put(key,1);
            }
        }


        int max_count=0, res = -1;

        for(Map.Entry<Integer,Integer> val: map.entrySet()){

            if(max_count < val.getValue()){
                res=val.getKey();
                max_count = val.getValue();
            }
        }
        System.out.println(res);

        }
    }
