
### Implementation

Java:
```Java
import java.util.*;

class Program {

  // O(n * m) time | O(c) space - where n is the number of strings, m is the
  // length of the longest string, and c is the number of unique characters
  // across all strings
  public String[] commonCharacters(String[] strings) {
    HashMap<Character, Integer> characterCounts = new HashMap<Character, Integer>();
    for (String string : strings) {
      HashSet<Character> uniqueStringCharacters = new HashSet<Character>();
      for (int i = 0; i < string.length(); i++) {
        uniqueStringCharacters.add(string.charAt(i));
      }

      for (char character : uniqueStringCharacters) {
        if (!characterCounts.containsKey(character)) {
          characterCounts.put(character, 0);
        }
        characterCounts.put(character, characterCounts.get(character) + 1);
      }
    }

    ArrayList<Character> finalCharacters = new ArrayList<Character>();
    for (Map.Entry<Character, Integer> characterCount : characterCounts.entrySet()) {
      Character character = characterCount.getKey();
      Integer count = characterCount.getValue();
      if (count == strings.length) {
        finalCharacters.add(character);
      }
    }

    String[] finalCharactersArr = new String[finalCharacters.size()];
  }
}
```
