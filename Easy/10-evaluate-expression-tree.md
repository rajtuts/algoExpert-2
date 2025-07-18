

Implementation:

Java:
```Java
import java.util.*;

class Program {
  // This is an input class. Do not edit.
  static class BinaryTree {
    public int value;
    public BinaryTree left = null;
    public BinaryTree right = null;

    public BinaryTree(int value) {
      this.value = value;
    }
  }

  // O(n) time | O(h) space - where n is the number of nodes in the Binary Tree,
  // and h is the height of the Binary Tree
  public int evaluateExpressionTree(BinaryTree tree) {
    if (tree.value >= 0) {
      return tree.value;
    }

    int leftValue = evaluateExpressionTree(tree.left);
    int rightValue = evaluateExpressionTree(tree.right);

    if (tree.value == -1) {
      return leftValue + rightValue;
    } else if (tree.value == -2) {
      return leftValue - rightValue;
    } else if (tree.value == -3) {
      return leftValue / rightValue;
    }
    return leftValue * rightValue;
  }
}
```
