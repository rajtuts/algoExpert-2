

### Implementation

Java:
```Java
import java.util.*;

class Program {
  // O(n) time | O(n) space - where n is the total number of elements in the
  // array
  public static List<Integer> spiralTraverse(int[][] array) {
    if (array.length == 0) return new ArrayList<Integer>();

    var result = new ArrayList<Integer>();
    var startRow = 0;
    var endRow = array.length - 1;
    var startCol = 0;
    var endCol = array[0].length - 1;

    while (startRow <= endRow && startCol <= endCol) {
      for (int col = startCol; col <= endCol; col++) {
        result.add(array[startRow][col]);
      }

      for (int row = startRow + 1; row <= endRow; row++) {
        result.add(array[row][endCol]);
      }

      for (int col = endCol - 1; col >= startCol; col--) {
        // Handle the edge case when there's a single row
        // in the middle of the matrix. In this case, we don't
        // want to double-count the values in this row, which
        // we've already counted in the first for loop above.
        // See Test Case 8 for an example of this edge case.
        if (startRow == endRow)
          break;
        result.add(array[endRow][col]);
      }

      for (int row = endRow - 1; row > startRow; row--) {
        // ... (code continues)
      }
    }
    return result; // Assuming this is the return statement based on the method signature
  }
}
```
