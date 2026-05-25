# Ex06 BMI Calculator
## Date: 25-06-2026

## AIM
To develop a responsive and interactive Body Mass Index (BMI) Calculator using React that allows users to input their height and weight, and calculates their BMI to categorize their health status (e.g., Underweight, Normal, Overweight, Obese).

## DESIGN STEPS

### STEP 1: Initialize React Project

<li>Create a new React app using create-react-app.</li>
<li>Install React Router using:</li>
npm install react-router-dom

### STEP 2: Set Up Routing

Create routing structure with react-router-dom:

<li>Home route (/) – Intro or Navigation</li>

<li>BMI Calculator route (/bmi)</li>

<li>Result route (/result)</li>

### STEP 3: Design the BMI Form Page

<li>Create a form to accept Height (in cm or m) and Weight (in kg).</li>

<li>On form submit, navigate to the result page with entered values via URL query params or context/state.</li>

## STEP 4: Handle Input Validation

<li>Check if height and weight are valid numbers.</li>

<li>Optionally, show error messages for invalid inputs.</li>

### STEP 5: Perform BMI Calculation

<li>In the result component:

<li>Extract height and weight from the route (URL or passed state).</li>

<li>Apply the BMI formula:</li>

![image](https://github.com/user-attachments/assets/ec785506-c96b-489e-8783-fb1a5d36101a)
​
 
<li>Convert height from cm to m if needed.</li></li>

### STEP 6: Display Result

<li>Show calculated BMI.</li>

<li>Show category based on BMI range:

<li>Underweight, Normal, Overweight, Obese, etc.</li></li>

### STEP 7: Navigation Options

<li>Provide a button to go back to the BMI form to calculate again.</li>

### STEP 8: Enhancements

<li>Add styling using CSS or Tailwind.</li>

## PROGRAM

```
import { useState } from "react";

function BMI() {
  const [weight, setWeight] = useState("");
  const [height, setHeight] = useState("");
  const [bmi, setBmi] = useState("");

  function calculateBMI() {
    const result = weight / ((height / 100) * (height / 100));
    setBmi(result.toFixed(2));
  }

  return (
    <div>
      <h1>BMI Calculator</h1>

      <input
        type="number"
        placeholder="Enter weight"
        onChange={(e) => setWeight(e.target.value)}
      />

      <br /><br />

      <input
        type="number"
        placeholder="Enter height"
        onChange={(e) => setHeight(e.target.value)}
      />

      <br /><br />

      <button onClick={calculateBMI}>
        Calculate
      </button>

      <h2>Your BMI: {bmi}</h2>
    </div>
  );
}

export default BMI;
```


## OUTPUT
<img width="1475" height="603" alt="image" src="https://github.com/user-attachments/assets/4b694abe-8419-49d9-ae11-0d371bc10417" />




## RESULT
The BMI Calculator successfully takes user input for height and weight, performs the BMI calculation in real-time using React state and event handling, and displays the BMI value along with the corresponding health category.
