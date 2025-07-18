

### Implementation

Java
```Java
import java.util.*;

class Program {
    // O(n) time | O(1) space - where n is the number of seats
    public int bestSeat(int[] seats) {
        int bestSeat = -1;
        int maxSpace = 0;

        int left = 0;
        while (left < seats.length) {
            int right = left + 1;
            while (right < seats.length && seats[right] == 0) {
                right++;
            }

            int availableSpace = right - left - 1;
            if (availableSpace > maxSpace) {
                bestSeat = (left + right) / 2;
                maxSpace = availableSpace;
            }
            left = right;
        }

        return bestSeat;
    }
}
```
