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

     ListNode dummy = new ListNode(-1);
        ListNode pointer = dummy;
        
        int carry = 0;
        while (l1 != null || l2 != null) {
           int v1 = l1 != null ? l1.val : 0;
           int v2 = l2 != null ? l2.val : 0;
           int sum = v1 + v2  + carry;
           carry = sum / 10;
           int remain = sum % 10;
           ListNode newNode = new ListNode(remain);
           pointer.next = newNode;
           pointer = pointer.next;
            
            if(l1 != null) l1 = l1.next;
            if(l2 != null) l2 = l2.next;
        }
        
        if (carry > 0) {
           ListNode newNode = new ListNode(carry);
           pointer.next = newNode;
           pointer = pointer.next;
        }
        
      return dummy.next;    


## 3. Longest Substring Without Repeating Characters

        public int lengthOfLongestSubstring(String s) {
       if ( null == s || 0 == s.length()) return 0;
       int i = 0, j = 0, max = 0;
       Set<Character> set = new HashSet<>();
       while (i < s.length()) {
           char c = s.charAt(i);
           while (set.contains(c)) {
             set.remove(s.charAt(j));
             ++j;
           }
           set.add(c);
           max= Math.max(max, i-j +1);
           ++i;
       } 
        
     return max;   
    }