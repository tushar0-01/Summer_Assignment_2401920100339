// Two Sum

class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] result=new int[2];
        Map<Integer,Integer> map=new HashMap<>();
        for(int i=0;i<nums.length;i++){
            int rem=target-nums[i];
            if(map.containsKey(rem)){
                result[0]=map.get(rem);
                result[1]=i;
                break;
            }
            map.put(nums[i],i);
        }
        return result;
    }
}

// Remove Duplicates from Sorted Array

class Solution {
    public int removeDuplicates(int[] nums) {
        int k=0;
        int i=1;
        int j=1;
        while(j<nums.length){
            if(nums[j]==nums[j-1]){
                j++;
            }else{
                nums[i]=nums[j];
                i++;
                k++;
                j++;
            }
        }
        return k+1;
    }
}

// Best Time to Buy and Sell Stock

class Solution {
    public int maxProfit(int[] prices) {
        int profit=0;
        int n=prices.length;
        int max=prices[n-1];
        n=n-2;
        while(n>=0){
            if(prices[n]<max){
                int diff=max-prices[n];
                profit=Math.max(diff,profit);
            }else{
                max=prices[n];
            }
            n--;
        }
        return profit;
    }
}
