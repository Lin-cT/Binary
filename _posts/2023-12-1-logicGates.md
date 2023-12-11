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
</head>

<body>
    <div class="main-container">
        <div class="door-lightbulb-container">
            <div id="lightbulb"></div>
            <img src="door1.png" id="door1">
        </div>
        <div class="text-buttons">
        <img src="and.png" id="and">
        <p id="text1">Which two numbers add up to 5?</p>
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
        <p id="text2">Which word is a synonym to the word "binary"?</p>
        <div class="button-container2">
          <button class="my-button" id="b7" onclick="toggle7Value(this);">Pair</button>
          <button class="my-button" id="b8" onclick="toggle8Value(this);">Dual</button>
        </div>
        <button id="check" onclick="checkAnswer()">Check!</button>
        <button id="enter" onclick="clickEnter()" style="display: none;">Enter!</button>
        <button id="check2" onclick="checkAnswer2()" style="display: none;">Check!</button>
      </div>
    </div>
    <div id="level-container">
    </div>
  </body>
  <script>
  // Variable to keep track of the button value
  var button1Value = 0;
  var button2Value = 0;
  var button3Value = 0;
  var button4Value = 0;
  var button5Value = 0;
  var button6Value = 0;
  var button7Value = 0;
  var button8Value = 0;
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
  function openDoor() {
    var doorImage = document.getElementById('door1')
    doorImage.src = 'door1_Open.png';
    doorImage.alt = 'Open Door';
  }
  function correctAnswer() {
    var correctAnswer = false
    if (button1Value === 1 && button5Value === 1 && button8Value === 1 || button7Value === 1) {
      return correctAnswer = true
    }
    else {
      return correctAnswer = false
    }
  }
  function correctAnswer2() {
    var correctAnswer = false
    if (button4Value !== 1 && ((button7Value === 1) !== (button8Value === 1))) {
      correctAnswer = true;
      return correctAnswer = true
    }
    else {
      return correctAnswer = false
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
    document.getElementById('enter').style.display = 'block'; // Show the "Enter" button
  } else {
    alert("Incorrect answer. Try again!");
  }
}
function checkAnswer2() {
  if (correctAnswer2()) {
    document.getElementById('lightbulb').style.backgroundImage = "url('on_lightbulb.png')";
    openDoor();
    alert("Correct! Congrats!");
  } else {
      alert("Incorrect answer. Try again!");
    }
}
function clickEnter() {
    // Update questions and choices
    var andImage = document.getElementById('and');
    var orImage = document.getElementById('or');
    andImage.src = 'not.png'; // Replace with the path to your nor gate image
    orImage.src = 'xor.png'; // Replace with the path to your not gate image
    // Hide the "Enter" button after clicking
    document.getElementById('enter').style.display = 'none';
    document.getElementById('check').style.display = 'none';
    document.getElementById('check2').style.display = 'block';
    button1Value = 0;
    button2Value = 0;
    button3Value = 0;
    button4Value = 0;
    button5Value = 0;
    button6Value = 0;
    button7Value = 0;
    button8Value = 0;
    var b1 = document.getElementById("b1");
    var b2 = document.getElementById("b2");
    var b3 = document.getElementById("b3");
    var b4 = document.getElementById("b4");
    var b5 = document.getElementById("b5");
    var b6 = document.getElementById("b6");
    var b7 = document.getElementById("b7");
    var b8 = document.getElementById("b8");
    var text1 = document.getElementById("text1");
    var text2 = document.getElementById("text2");
    text1.innerHTML = "Click on any button except the red button.";
    b1.innerHTML = "";
    b2.innerHTML = "";
    b3.innerHTML = "";
    b4.innerHTML = "";
    b5.innerHTML = "";
    b6.innerHTML = "";
    b1.style.backgroundColor = "";
    b2.style.backgroundColor = "";
    b3.style.backgroundColor = "";
    b4.style.backgroundColor = "red"; // Corrected property name
    b5.style.backgroundColor = "";
    b6.style.backgroundColor = "";
    text2.innerHTML = "You can click on one button, or the other, but not both!";
    b7.innerHTML = "Click me";
    b8.innerHTML = "Click ME!";
    b7.style.backgroundColor = "";
    b8.style.backgroundColor = "";
}
 
</script>