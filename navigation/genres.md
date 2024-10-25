<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Music Genre Poll</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
        }
        h1 {
            margin-bottom: 20px;
        }
        .button-container {
            width: 80%;
            max-width: 400px;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .genre-button {
            padding: 15px;
            font-size: 18px;
            background-color: #4CAF50;
            color: #000;
            border: none;
            cursor: pointer;
            text-align: center;
            transition: background-color 0.3s;
        }
        .genre-button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <h1>What is your favorite music genre?</h1>
    <div class="button-container">
        <button class="genre-button">Rock</button>
        <button class="genre-button">Pop</button>
        <button class="genre-button">Hip-Hop</button>
        <button class="genre-button">Jazz</button>
        <button class="genre-button">Classical</button>
    </div>

</body>
</html>