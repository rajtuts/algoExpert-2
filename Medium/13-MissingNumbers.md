

### Implementation

Java
```Java
import java.util.*;

class Program {
    // O(n) time | O(1) space - where n is the number of elements in the array
    public int majorityElement(int[] array) {
        int count = 0;
        int answer = array[0];

        for (int value : array) {
            if (count == 0) {
                answer = value;
            }

            if (value == answer) {
                count++;
            } else {
                count--;
            }
        }

        return answer;
    }
}
```
