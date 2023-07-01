# Assignment-String-
Assignment 4:-

class Main {

	

	int findSubArray(int arr[], int n)
	{
		int sum = 0;
		int maxsize = -1, startindex = 0;
		int endindex = 0;

	

		for (int i = 0; i < n - 1; i++) {
			sum = (arr[i] == 0) ? -1 : 1;

	

			for (int j = i + 1; j < n; j++) {
				if (arr[j] == 0)
					sum += -1;
				else
					sum += 1;

			

				if (sum == 0 && maxsize < j - i + 1) {
					maxsize = j - i + 1;
					startindex = i;
				}
			}
		}
		endindex = startindex + maxsize - 1;
		if (maxsize == -1)
			System.out.println("No such subarray");
		else
			System.out.println(startindex + " to " + endindex);

		return maxsize;
	}

	

	public static void main(String[] args)
	{
		LargestSubArray sub;
		sub = new LargestSubArray();
		int arr[] = { 1, 0, 0, 1, 0, 1, 1 };
		int size = arr.length;

		sub.findSubArray(arr, size);
	}
}

Assignment 2:-

public class Main{
    static boolean searchMatrix(int[] arr, int k, int N) {
        int low = 0;
        int high = N - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;

            if (arr[mid] == k) {
                return true;
            }
            if (arr[mid] < k) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return false;
    }
        public static void main(String args[])
        {
            int arr[][] = { { 1, 3, 5, 7 },
                    { 10, 11, 16, 20 },
                    { 23, 30, 34, 50 } };
            int K = 3;
            if (searchMatrix(arr, K)) {
                System.out.println("Found");
            }
            else {
                System.out.println("Not found");
            }
    }
}

Assignment 1:-

import java.util.*;
public class Main{
    public static boolean isPermutation(int[] arr, int n){

        for(int i=0; i<n; i++){
            boolean found = false;
            for(int j=0; j<n; j++){
                if(arr[j] == i){
                    found = true;
                    break;
                }
            }
            if(!found){
                return false;
            }

        }
        return true;
    }

    public static void main(String[] args) {
        int[] arr = {1,2,5,3,2};
        int n = arr.length;

        if(isPermutation(arr,n)){
            System.out.println("Yes");
        }
        else{
            System.out.println("No");
        }
    }

}



