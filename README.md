# 📱 Mobile Calculator App - Requirements & OOP Modeling

This project consists of a comprehensive documentation and object-oriented analysis for a mobile calculator application. It maps user inputs, behavioral logic, edge cases, and architectural design before the implementation phase.

## 📋 Features & Specifications

### 1. User Inputs & Data Flow
* **Numeric Inputs:** Supports multi-digit composition (e.g., pressing '1', '2', '3' constructs the number `123`).
* **Operations:** Standard arithmetic operations: Addition (+), Subtraction (-), Multiplication (x), and Division (÷).
* **Sequential & Chained Execution:** Follows a standard `number → operation → number → result` flow, while allowing chained operations where the previous result becomes the first operand for the next calculation.

### 2. Edge Cases & Error Handling
* **Decimal Point Control:** Prevents malformed numbers by ignoring consecutive or multiple decimal points (e.g., `3.1.4` is blocked).
* **Operation Override:** If multiple operators are pressed sequentially without an intermediate number, the last operator overrides the previous one.
* **Division by Zero:** Safely caught and handled by displaying an error message (`Error` or `Undefined`) without crashing the application.
* **Display Limitations:** Implements truncating or scientific notation for numbers exceeding screen limits.

---

## 🏗️ Object-Oriented Design (OOP)

The application logic is designed around a core `Calculator` class with the following structure:

### Atributes (State)
* `currentDisplayValue`: The text/number currently shown on the screen.
* `storedOperand`: Stores the first number for the pending operation.
* `pendingOperation`: Holds the current arithmetic operator (+, -, x, ÷).
* `isNewNumberStart`: A boolean flag indicating if the next digit pressed should clear the display and start a new number.

### Methods (Behavior)
* `insertDigit(digit)`: Appends a digit to the current number string.
* `insertDecimalPoint()`: Safely appends a decimal point if one isn't already present.
* `selectOperation(operator)`: Stores the current display value and the chosen operation.
* `calculateResult()`: Executes the pending operation using the stored operand and the current value, updating the display with the result.
* `clear()`: Resets the entire calculator state (corresponds to the 'C' or 'AC' button).

---

## 🧠 Key Takeaways
This planning phase highlights the importance of mapping all user interaction possibilities and state transitions before writing code, ensuring a robust, crash-free, and predictable user experience.
