---
layout: default
title: Student Blog
---

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Binary Project</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }

        h1 {
            color: black;
        }

        .button-container {
            display: flex;
            flex-direction: column;
            gap: 20px;
            margin-top: 20px;
        }

        .button {
            padding: 15px 30px;
            font-size: 18px;
            text-align: center;
            text-decoration: none;
            color: white;
            background-color: #007bff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <h1>Binary Project</h1>
    <div class="button-container">
        <button onclick="navigate('https://lin-ct.github.io/binary/binary/logicGates.html')" class="button"><a href="https://lin-ct.github.io/binary/binary/logicGates.html"></a>Logic Gates</button>
        <button href="#binary-to-color" class="button">Binary to Color Converter</button>
        <button href="#letters-to-binary" class="button">Letters to Binary Converter</button>
    </div>
</body>
<script>
    function navigate(url) {
        window.location.href = url;
    }
</script>
