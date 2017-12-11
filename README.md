# Elemental Words

Each element in the periodic table has a symbol associated with it. For instance, the symbol for the element Yttrium is Y. A fun thing to do is see if we can form words using symbols of elements strung together. The symbol for Einsteinium is Es, so the symbols for Yttrium and Einsteinium together form:

Y + Es = YEs

Yes! Ignoring capitalization, we can think of any string of letters formed by the concatenation of one or more element symbols as an elemental word -- per the above,yes is an elemental word. There is only one combination of element symbols that can form yes, but in general, there may be more than one combination of element symbols that can form a given elemental word. Let's call each different combination of element symbols that can form a given elemental word word an elemental form of word.

Your task is to implement the function elementalForms(word), which takes one parameter (the string word), and returns an array (which we'll call forms). If word can be formed by combining element symbols from the periodic table, then forms should contain one or more sub-arrays, each consisting of strings of the form 'elementName (elementSymbol)', for each unique combination of elements that can form word.

### Example

The word 'snack' can be formed by concatenating the symbols of 3 different combinations of elements:

    ----------------------------------------------------
    |       1        |       2        |       3        |
    |---------------------------------------------------
    | Sulfur    (S)  | Sulfur    (S)  | Tin       (Sn) |
    | Nitrogen  (N)  | Sodium    (Na) | Actinium  (Ac) |
    | Actinium  (Ac) | Carbon    (C)  | Potassium (K)  |
    | Potassium (K)  | Potassium (K)  |                |
    ----------------------------------------------------

So elementalForms('snack') should return the following array:

    [
      ['Sulfur (S)', 'Nitrogen (N)', 'Actinium (Ac)', 'Potassium (K)'],
      ['Sulfur (S)', 'Sodium (Na)', 'Carbon (C)', 'Potassium (K)'],
      ['Tin (Sn)', 'Actinium (Ac)', 'Potassium (K)']
    ]

### Guidelines

* Capitalization does not matter:

    elementalForms('beach')
    // => [ ['Beryllium (Be)', 'Actinium (Ac)', 'Hydrogen (H)'] ]
    elementalForms('BEACH')
    // => [ ['Beryllium (Be)', 'Actinium (Ac)', 'Hydrogen (H)'] ]

* The order of the returned sub-arrays does not matter, but the order of the strings within each sub-array does matter -- they should be in the order that "spells out" word.
* If word is not an elemental word (that is, no combination of element symbols can form word), return an empty array.
* You do not need to check the type of word. It will always be a (possibly empty) string.
* Finally, the helper method getElement has been provided, which is a map from each element symbol to its corresponding full name (e.g. getElement("Na") === "Sodium (Na)"). Have fun!

Rappel des commandes junit :

    javac -cp .:junit-4.12.jar ElementalWordsTest.java
    java -cp .:junit-4.12.jar:hamcrest-core-1.3.jar org.junit.runner.JUnitCore ElementalWordsTest
