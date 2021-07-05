# Cmoney-online-judge-Problem-ft8107

import java.util.*;


public class Main {

    public static void main(String[] args) {
        // write some test code here
        Scanner sc = new Scanner(System.in);
        int serial=0;
        int score=0;
        HashMap<Double,Integer> list=new HashMap<Double, Integer>();
        ArrayList<Double> list_key=new ArrayList<>();
        while(true){
            do{
                score=sc.nextInt();
            }while(score<-1||score>100);
            if(score==-1){
                break;
            }
            else{
                serial++;
                list.put(score+0.000001*(serial),score);
            }
        }
        for(double a:list.keySet()){
            list_key.add(a);
        }

        int choose = 0;
        do{
            choose=sc.nextInt();
        }while(choose!=1&&choose!=2);

        if(choose==1){
            Collections.sort(list_key);
        }
        else{
            Collections.sort(list_key,Collections.reverseOrder());
        }

        for(int i=0;i<list_key.size();i++){
            int value=list.get(list_key.get(i));
            System.out.println(Math.round((list_key.get(i)-value)*1000000)+"."+value);
        }
    }
}
