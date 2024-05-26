import java.util.ArrayList;
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        //System.out.println("Hello world!");

        ArrayList<Integer> arrayList = new ArrayList<>(Arrays.asList(1, 2, 3, 5));
        int k = 2;

        getRollingAverage(arrayList,k);
    }
    private static void getRollingAverage(ArrayList<Integer> arrayList, int k){
        if (arrayList.size() < k ) {
            throw new RuntimeException("Окно больше выборки !!!");
        }
        float sumSubArray = 0;
        for (int i=0; i<k; i++){
            sumSubArray = sumSubArray + arrayList.get(i);
        }
        System.out.println(sumSubArray/k);
        for (int i=k; i<arrayList.size(); i++){
            sumSubArray = sumSubArray + arrayList.get(i) - arrayList.get(i-k);
            System.out.println(sumSubArray/k);
        }
    }
}