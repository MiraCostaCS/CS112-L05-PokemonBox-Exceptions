## 📋 Project Assessment: Lab 05 - PokémonBox + Exceptions

### 1. Git & Workflow
- [ ] **Commit Messages:** Descriptive and incremental (e.g., "Defined custom PokemonAlreadyExistsException" or "Implemented try-catch in Main menu").

### 2. Functional Requirements
- [ ] **Pokemon (Model Class):**
    - [ ] **Constructors Upgrade:** Replaced `System.exit()` or shutdown logic with `throw new IllegalArgumentException("Message")` for invalid data in all constructors
- [ ] **`PokemonAlreadyExistsException` (Custom Exception):**
    - [ ] **Definition:** New class created that `extends Exception`
    - [ ] **Constructors:**
      - [ ] Includes a default constructor with default error message.
      - [ ] Includes a message-based constructor to pass specific error details.
- [ ] **PokemonBox (Container Class):**
    - [ ] **Constructor Upgrade:** Throws `IllegalArgumentException` if initial parameters (like capacity) are invalid.
    - [ ] **getPokemon(int location):** Throws `IndexOutOfBoundsException` if the location is outside the valid array range.
    - [ ] **add(Pokemon p):**
        - [ ] Scans the current array for a Pokémon with the same name (or uses `hasPokemon()` method).
        - [ ] Throws `PokemonAlreadyExistsException` if a match is found, preventing the duplicate from being added.
- [ ] **Driver Program (Main.java):**
    - [ ] **InputMismatchException:** Uses `try-catch` within the menu to catch non-integer inputs, clears the scanner buffer, and allows the user to try again.
      - [ ] Pay close attention to the Scanner's buffer when catching `InputMismatchException`—if you don't clear the "bad" input with a `nextLine()`, you might end up in an infinite loop!
    - [ ] **IllegalArgumentException:** Catches invalid Pokémon data during creation and prompts the user for corrected values without crashing.
    - [ ] **PokemonAlreadyExistsException:** Specifically catches the custom exception; displays a message regarding regional sustainability and habitat loss before returning to the menu.

### 3. Code Quality & Standards
- [ ] **Exception Handling:**
    - [ ] `try-catch` blocks are scoped narrowly (not wrapping the entire program).
    - [ ] Specific exceptions are caught before more general ones (e.g., catching `InputMismatchException` specifically, not catching all with `Exception`).
- [ ] **Naming & Formatting:** `PokemonAlreadyExistsException` follows standard Java exception naming conventions.
- [ ] **Robustness:** The program remains running even after an exception is triggered (the "Lather, Rinse, Repeat" approach to user errors).
- [ ] **Documentation:** JavaDoc present for all methods. Custom exception and logic changes are clearly documented.
