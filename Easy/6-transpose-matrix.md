


Implementation:

Java:
```Java
import java.util.*;

class Program {
  // O(w * h) time | O(w * h) space - where w is the
  // width of the matrix and h is the height
  public int[][] transposeMatrix(int[][] matrix) {
    int[][] transposedMatrix = new int[matrix[0].length][matrix.length];
    for (int col = 0; col < matrix[0].length; col++) {
      for (int row = 0; row < matrix.length; row++) {
        transposedMatrix[col][row] = matrix[row][col];
      }
    }
    return transposedMatrix;
  }
}
```
