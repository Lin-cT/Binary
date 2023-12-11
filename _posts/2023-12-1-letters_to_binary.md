---
toc: True
comments: True
layout: post
title: Letters to Binary
courses: {'compsci': {'week': 7}}
type: hacks
permalink: "ltb"
---

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <body style="background-color:lightsteelblue;">
        <div style="text-align:center">
            <p>
                Binary is used by a computer, and is made up of various sequences of zeros and ones.
            </p>
        <div style="text-align:center">
            <p>
                Different sequences of binary can represent letters.
            </p>
            </div>
        <div style="text-align:center">
            <p>
                This program will show you different letters as their binary counterparts.
            </p>
        </div>
<br>
<br>
            <div style="text-align: center;">
                <div style="text-align: center;">
                    <p>
                        <font color="lightsteelblue">divider</font> 
                    </p>
                </div>
        <div style="text-align: center;">
        <input type="text" style="height:50px; width:200px;" id="letterInput" placeholder="Enter a letter" maxlength="1">
        <button onclick="convertToBinary()">
            <font size="5">Convert</font>
        </button>
        <font size="6"> <p id="binaryOutput"></p> </font>
        <p id="binaryOutput"></p>
        <script>
            function convertToBinary() {
                var letter = document.getElementById('letterInput').value;
                if (letter.length === 1) {
                    var binary = letter.charCodeAt(0).toString(2);
                    document.getElementById('binaryOutput').innerText = 'Binary: ' + binary;
                }
                    else {
                        document.getElementById('binaryOutput').innerText = 'Please enter a single letter.';
                    }
                }
        </script>
    </div>