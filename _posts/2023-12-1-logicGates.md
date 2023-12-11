---
toc: True
comments: True
layout: post
title: Logic Gates 
description: Door game
courses: {'compsci': {'week': 7}}
type: hacks
permalink: "lg"
---
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* Remember to move the style into scss folder later */
        /* Additional styles for positioning text paragraphs */
        #t1,
        #t2 {
            text-align: center;
            margin-bottom: 10px;
            font-weight: bold;
        }
        /* Style for the main container */
        .main-container {
            display: flex;
            justify-content: center;
            align-items: center;
        }
        /* Style for the door-lightbulb-container */
        .door-lightbulb-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-bottom: 20px; /* Add margin at the bottom */
        }
        .text-buttons {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-bottom: 20px; /* Add margin at the bottom */
        }
        #lightbulb {
            width: 100px;
            height: 100px;
            margin: 20px;
            background-image: url('off_lightbulb.png'); /* Replace with the path to your off lightbulb image */
            background-size: cover;
        }
        #door1 {
            width: 250px; /* Adjusted width to make it smaller */
            height: 550px; /* Adjusted height to make it smaller */
            margin: 20px;
        }
        /* Style for the button-container */
        .button-container {
            background-color: #f0f0f0; /* Lighter background color */
            border: 2px solid #999; /* Lighter border color */
            padding: 15px; /* Increased padding around the buttons */
            display: grid;
            grid-template-columns: repeat(3, 1fr); /* Three columns */
            gap: 12px; /* Increased gap between buttons */
            align-items: center;
            margin-top: 20px; /* Adjusted margin between the two button containers */
        }
        /* Style for the buttons in the container */
        .button-container .my-button {
            width: 80px; /* Set the width of the buttons */
            height: 50px; /* Set the height of the buttons */
            background-color: #808080; /* Grey background color */
            color: #000; /* Black text color */
            padding: 16px; /* Increase padding inside the button */
            border: 2px solid black; /* Black border */
            border-radius: 4px; /* Optional: Add rounded corners */
            cursor: pointer; /* Change cursor to pointer on hover */
            margin-bottom: 8px; /* Adjusted margin between buttons */
            position: relative; /* Add this line to enable z-index */
            z-index: 1; /* Add this line to control the stacking order */
            display: flex; /* Use flexbox */
            justify-content: center; /* Center the content horizontally */
            align-items: center; /* Center the content vertically */
        }
        .button-container .my-button:hover {
            background-color: #808080; /* Darker grey background color on hover */
            color: #fff; /* White text color on hover */
        }
        .clicked {
            background-color: blue; /* Change color if clicked */
            color: white; /* Change text color if clicked */
        }
        /* Style for the buttons */
        .my-button {
            background-color: #808080; /* Grey background color */
            color: #000; /* Black text color */
            padding: 16px; /* Increase padding inside the button */
            border: 2px solid black; /* Black border */
            border-radius: 4px; /* Optional: Add rounded corners */
            cursor: pointer; /* Change cursor to pointer on hover */
            margin-bottom: 8px; /* Adjusted margin between buttons */
            position: relative; /* Add this line to enable z-index */
            z-index: 1; /* Add this line to control the stacking order */
        }
        /* Style for the Check button */
        #check {
            padding: 20px; /* Increase padding for a larger button */
            background-color: #4CAF50; /* Green background color */
            color: white; /* White text color */
            border: none; /* No border */
            border-radius: 4px; /* Optional: Add rounded corners */
            cursor: pointer; /* Change cursor to pointer on hover */
            margin-top: 20px; /* Adjusted margin from the button container */
        }
        /* Style for the Check button on hover */
        #check:hover {
            background-color: #45a049; /* Darker green background color on hover */
        }
        /* Style for the "and" and "or" images */
        #and,
        #or {
            width: 60px; /* Adjust the size as needed */
            height: 50px; /* Adjust the size as needed */
            margin-bottom: 10px; /* Add margin at the bottom */
        }
        /* Style for the paragraph text */
        .text-buttons p {
            font-weight: bold; /* Make the text bold */
        }
    </style>
</head>

<body>
    <div class="main-container">
        <div class="door-lightbulb-container">
            <div id="lightbulb"></div>
            <img src="door1.png" id="door1">
        </div>
        <div class="text-buttons"">
        <img src="and.png" id="and">
        <p id="t1">Which two numbers add up to 5?</p>
        <div class="button-container">
          <button class="my-button" id="b1" onclick="toggle1Value(this);">2</button>
          <button class="my-button" id="b2" onclick="toggle2Value(this);">8</button>
          <button class="my-button" id="b3" onclick="toggle3Value(this);">9</button>
          <button class="my-button" id="b4" onclick="toggle4Value(this);">7</button>
          <button class="my-button" id="b5" onclick="toggle5Value(this);">3</button>
          <button class="my-button" id="b6" onclick="toggle6Value(this);">1</button>
        </div>
        <br>
        <img src="or.png" id="or">
        <p id="t2">Which word is a synonym to the word "binary"?</p>
        <div class="button-container">
          <button class="my-button" id="b7" onclick="toggle7Value(this);">One</button>
          <button class="my-button" id="b8" onclick="toggle8Value(this);">Dual</button>
          <button class="my-button" id="b9" onclick="toggle9Value(this);">Careful</button>
          <button class="my-button" id="b10" onclick="toggle10Value(this);">Utterance</button>
          <button class="my-button" id="b11" onclick="toggle11Value(this);">Paired</button>
          <button class="my-button" id="b12" onclick="toggle12Value(this);">Zero</button>
        </div>
        <button id="check" onclick="checkAnswer()">Check!</button>
        </div>
    </div>
  </body>
  <script>
  //Variable to keep track of the button value
  var button1Value = 0;
  var button2Value = 0;
  var button3Value = 0;
  var button4Value = 0;
  var button5Value = 0;
  var button6Value = 0;
  var button7Value = 0;
  var button8Value = 0;
  var button9Value = 0;
  var button10Value = 0;
  var button11Value = 0;
  var button12Value = 0;
  // Function to toggle the button value
  function toggle1Value(button) {
    // Toggle between 0 and 1
    button1Value = 1 - button1Value;
    changeColor(button);
  }
  // Function to toggle the button value
  function toggle2Value(button) {
    // Toggle between 0 and 1
    button2Value = 1 - button2Value;
    changeColor(button);
  }
  // Function to toggle the button value
  function toggle3Value(button) {
    // Toggle between 0 and 1
    button3Value = 1 - button3Value;
    changeColor(button);
  }
  // Function to toggle the button value
  function toggle4Value(button) {
    // Toggle between 0 and 1
    button4Value = 1 - button4Value;
    changeColor(button);
  }
  // Function to toggle the button value
  function toggle5Value(button) {
    // Toggle between 0 and 1
    button5Value = 1 - button5Value;
    changeColor(button);
  }
  // Function to toggle the button value
  function toggle6Value(button) {
    // Toggle between 0 and 1
    button6Value = 1 - button6Value;
    changeColor(button);
  }
    // Function to toggle the button value
    function toggle7Value(button) {
    // Toggle between 0 and 1
    button7Value = 1 - button7Value;
    changeColor(button);
  }
  // Function to toggle the button value
  function toggle8Value(button) {
  // Toggle between 0 and 1
  button8Value = 1 - button8Value;
  changeColor(button);
  }
  // Function to toggle the button value
  function toggle9Value(button) {
  // Toggle between 0 and 1
  button9Value = 1 - button9Value;
  changeColor(button);
  }
  // Function to toggle the button value
  function toggle10Value(button) {
  // Toggle between 0 and 1
  button10Value = 1 - button10Value;
  changeColor(button);
  }
  // Function to toggle the button value
  function toggle11Value(button) {
  // Toggle between 0 and 1
  button11Value = 1 - button11Value;
  changeColor(button);
  }
  // Function to toggle the button value
  function toggle12Value(button) {
  // Toggle between 0 and 1
  button12Value = 1 - button12Value;
  changeColor(button);
  }
  function openDoor() {
    var doorImage = document.getElementById('door1')
    doorImage.src = 'door1_Open.png';
    doorImage.alt = 'Open Door';
  }
  function correctAnswer() {
    var correctAnswer = false
    if (button1Value === 1 && button5Value === 1 && button8Value === 1 || button11Value === 1) {
      return correctAnswer = true
    }
    else {
      return correctAnswer = false
    }
  }
  function checkAnswer(isCorrect) {
    if (correctAnswer() === true) {
      document.getElementById('lightbulb').style.backgroundImage = "url('on_lightbulb.png')"; /* Replace with the path to your on lightbulb image */
      openDoor();
    } else {
      alert("Incorrect answer. Try again!");
    }
  }
  function changeColor(button) {
    if (button.style.backgroundColor === 'blue') {
        button.style.backgroundColor = ''; // Reset to default color
    } else {
        button.style.backgroundColor = 'blue';
    }
}
  function checkAnswer() {
    if (correctAnswer()) {
        document.getElementById('lightbulb').style.backgroundImage = "url('on_lightbulb.png')";
        openDoor();
        alert("Correct! You can move on to the next level.");
        // Add code here to proceed to the next level if needed
    } else {
        alert("Incorrect answer. Try again!");
    }
}
</script>
</body>