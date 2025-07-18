

### Implementation

Java
```Java
import java.util.*;

class Program {
    // O(n) time | O(n) space - where n is the length of the input array
    public int[] missingNumbers(int[] nums) {
        HashSet<Integer> includedNums = new HashSet<>();
        for (int num : nums) {
            includedNums.add(num);
        }

        int[] solution = new int[]{-1, -1};
        for (int num = 1; num < nums.length + 3; num++) {
            if (!includedNums.contains(num)) {
                if (solution[0] == -1) {
                    solution[0] = num;
                } else {
                    solution[1] = num;
                }
            }
        }
        return solution;
    }
}
```
