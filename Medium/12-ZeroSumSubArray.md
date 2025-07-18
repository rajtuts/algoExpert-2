

### Implementation

Java
```Java
import java.util.*;

class Program {
    // O(n) time | O(n) space - where n is the length of nums
    public boolean zeroSumSubarray(int[] nums) {
        HashSet<Integer> sums = new HashSet<>();
        sums.add(0);
        int currentSum = 0;
        for (int num : nums) {
            currentSum += num;
            if (sums.contains(currentSum)) {
                return true;
            }
            sums.add(currentSum);
        }
        return false;
    }
}
```
