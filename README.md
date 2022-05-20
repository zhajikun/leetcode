# leetcode easy 75

## leetcode75

## 1.  2 sum
        [2, 7, 4, 5, 9, 4] , target = 8
         0  1  2  3  4  5  , index

        method 1 bruit force , two for loop
        method 2 HashMap
        create a hashmap, then for loop the array
        if number 2 did not find the 6 in the hashmap, then write 2 as key and 2's index as value
                    HashMap
                 Key  |  Value(index)
    for loop      2        0
                  7        1
                  4        2
                  ...      ...
                  4        5

            

    public int[] twoSum(int[] nums, int target) {

        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length ; i++) {
            if (map.containsKey(target - nums[i])) {
               return new int[]{i, map.get(target - nums[i])}
            } else {
               map.put(nums[i] , i);
            }

        }

        return null;
        
    }

## 2.  Add two numbers

    Input: l1 = [2,4,3], l2 = [5,6,4]
    Output: [7,0,8]
    Explanation: 342 + 465 = 807.

