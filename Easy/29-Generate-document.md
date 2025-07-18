



### Implementation

Java:
```Java
import java.util.*;

class Program {

  // O(n + m) time | O(c) space - where n is the number of characters, m is
  // the length of the document, and c is the number of unique characters in the
  // characters string
  public boolean generateDocument(String characters, String document) {
    HashMap<Character, Integer> characterCounts = new HashMap<Character, Integer>();

    for (int idx = 0; idx < characters.length(); idx++) {
      char character = characters.charAt(idx);
      characterCounts.put(character, characterCounts.getOrDefault(character, 0) + 1);
    }

    for (int idx = 0; idx < document.length(); idx++) {
      char character = document.charAt(idx);
      if (!characterCounts.containsKey(character) || characterCounts.get(character) == 0) {
        return false;
      }

      characterCounts.put(character, characterCounts.get(character) - 1);
    }

    return true;
  }
}
```
