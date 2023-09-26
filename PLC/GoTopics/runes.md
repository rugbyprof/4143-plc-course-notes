## Runes

In Go, a `rune` is a built-in data type that represents a Unicode code point. Unicode is a character encoding standard that covers a wide range of characters from various writing systems around the world, including letters, symbols, and emojis. A `rune` is used to represent a single Unicode code point, which can be a character or symbol.

Here's an overview of `rune` in the context of Dungeons & Dragons (D&D) theme:

1. **Unicode Support:** Go's `rune` type is designed to work with Unicode characters, making it suitable for handling text that includes special characters, diacritics, and characters from different languages, which can be relevant in D&D for character names, spells, or descriptions.

2. **Single Characters:** A `rune` represents a single character, and it's often used when you need to work with individual characters within a string, such as parsing, modifying, or comparing characters.

3. **Type Alias:** Technically, a `rune` is an alias for the `int32` data type. It's used to emphasize that it's specifically used for Unicode code points.

Now, let's see a D&D-themed code example that uses `rune` to manipulate a character's name:

```go
package main

import (
    "fmt"
)

func main() {
    // Character name with special characters
    characterName := "Gandalf the Gray (ガンダルフ)"

    // Convert the character name to a rune slice
    characterRunes := []rune(characterName)

    // Print the character name in reverse
    fmt.Print("Character Name Reversed: ")
    for i := len(characterRunes) - 1; i >= 0; i-- {
        fmt.Print(string(characterRunes[i]))
    }
    fmt.Println()

    // Count the number of characters in the name
    characterCount := len(characterRunes)
    fmt.Printf("Character Name Length: %d characters\n", characterCount)

    // Access and print individual characters
    fmt.Print("Individual Characters: ")
    for _, char := range characterRunes {
        fmt.Printf("%c ", char)
    }
    fmt.Println()
}
```

In this D&D-themed example:

- We have a character name that includes special characters, such as Japanese characters (ガンダルフ).
- We convert the character name into a `rune` slice using `[]rune(characterName)`.
- We then demonstrate how to work with `rune` values by printing the character name in reverse, counting the number of characters, and printing individual characters.

The use of `rune` allows us to work with characters from different writing systems and handle them as individual units within a string, making it suitable for scenarios where D&D character names might involve various characters and symbols.