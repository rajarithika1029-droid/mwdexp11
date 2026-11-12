# Exp 11 – Basic Calculator using React

## **NAME: Raja Rithika**

## **REG NO: 2305001029**

---

## Aim

To develop a basic calculator application using React that performs arithmetic operations such as addition, subtraction, multiplication, and division.

## Objectives

- To understand React components and JSX.
- To use the useState() hook to manage calculator values.
- To handle user input using onChange events.
- To perform arithmetic operations using conditional statements.
- To implement Calculate and Clear buttons using event handling.

## Program

### Step 1: Create a React Project

Execute the following commands in the VS Code terminal:

```bash
npm create vite@latest calculator-app
cd calculator-app
npm install
npm run dev
```

Select React as the framework and JavaScript as the variant.

### Step 2: App.jsx

Open `src/App.jsx` and paste the following code:

```jsx
import { useState } from "react";
import "./App.css";

function App() {
  const [num1, setNum1] = useState("");
  const [num2, setNum2] = useState("");
  const [operator, setOperator] = useState("+");
  const [result, setResult] = useState("");

  const calculate = () => {
    const a = Number(num1);
    const b = Number(num2);
    let answer;

    if (operator === "+") {
      answer = a + b;
    } else if (operator === "-") {
      answer = a - b;
    } else if (operator === "*") {
      answer = a * b;
    } else if (operator === "/") {
      answer = b !== 0 ? a / b : "Cannot divide by zero";
    }

    setResult(answer);
  };

  const clearCalculator = () => {
    setNum1("");
    setNum2("");
    setOperator("+");
    setResult("");
  };

  return (
    <div>
      <h1>Basic Calculator</h1>

      <input
        type="number"
        placeholder="Enter first number"
        value={num1}
        onChange={(e) => setNum1(e.target.value)}
      />

      <br /><br />

      <select
        value={operator}
        onChange={(e) => setOperator(e.target.value)}
      >
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>

      <br /><br />

      <input
        type="number"
        placeholder="Enter second number"
        value={num2}
        onChange={(e) => setNum2(e.target.value)}
      />

      <br /><br />

      <button onClick={calculate}>Calculate</button>
      <button onClick={clearCalculator}>Clear</button>

      <h2>Result: {result}</h2>
    </div>
  );
}

export default App;
```

### Step 3: App.css

Open `src/App.css` and paste:

```css
body {
  font-family: Arial, sans-serif;
  background-color: #f2f2f2;
  text-align: center;
}

div {
  margin-top: 50px;
}

h1 {
  color: #333;
}

input, select {
  padding: 10px;
  margin: 5px;
  width: 180px;
}

button {
  padding: 10px 20px;
  margin: 10px;
  background-color: blue;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: darkblue;
}

h2 {
  color: green;
}
```

## Output

### 1. Basic Calculator – Multiplication
<img width="453" height="277" alt="image" src="https://github.com/user-attachments/assets/8908bc3a-90e6-428d-8c7e-7752a74af5be" />


### 2. Basic Calculator – Division by Zero
<img width="417" height="271" alt="image" src="https://github.com/user-attachments/assets/e626dd83-b602-43ea-b7f3-e24b34c1a8e6" />



## Result

Thus, a basic calculator application was successfully implemented using React with useState(), event handling, and conditional statements to perform arithmetic operations.
