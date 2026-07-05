```java

import java.util.*;

class Main{
	public static void main(String args[])
	{
		Scanner sc = new Scanner(System.in);

        int a = sc.nextInt();
        int target = sc.nextInt();

        int[] arr = new int[a];
        for(int i=0;i<a;i++){
            arr[i] = sc.nextInt();
        }

        int left=0;
        int right=a-1;

        while(left<right){
            int sum = arr[left] + arr[right];
            if(sum==target){
                System.out.println((left+1)+" "+(right+1));
                return;
            }
            else if(sum<target){
                left++;
            }
            else{
                right--;
            }
        }
                
            
        
	}
}


```
