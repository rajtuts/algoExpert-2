

### Implementation

Java:
```Java
import java.util.*;

class Program {

  // O(n * m) time | O(n * m) space - where n is the number of words and
  // m is the length of the longest word
  public ArrayList<ArrayList<String>> semordnilap(String[] words) {
    HashSet<String> wordsSet = new HashSet<String>(Arrays.asList(words));
    ArrayList<ArrayList<String>> semordnilapPairs = new ArrayList<ArrayList<String>>();

    for (String word : words) {
      String reverse = new StringBuilder(word).reverse().toString();
      if (wordsSet.contains(reverse) && !reverse.equals(word)) {
        ArrayList<String> semordnilapPair = new ArrayList<String>();
        semordnilapPair.add(word);
        semordnilapPair.add(reverse);
        semordnilapPairs.add(semordnilapPair);
        wordsSet.remove(word);
        wordsSet.remove(reverse);
      }
    }
    return semordnilapPairs; // Added missing return statement
  }
}

```
