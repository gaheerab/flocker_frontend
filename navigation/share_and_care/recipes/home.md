---
layout: post
title: The Hungry Games (Home, Chat, Hunger Calls)
permalink: share_and_care/hungry_games
comments: true
author: Ryan, Jowan, Gabriela, Michelle
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: 'Calibri', sans-serif; 
            background-color: #f8f9fa;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center; 
            min-height: 100vh;
            margin: 0;
        }
        .button {
            display: inline-block;
            padding: 10px 20px;
            font-size: 16px;
            color: white;
            background-color: #007bff;
            text-decoration: none;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }
        .button:hover {
            background-color: #0056b3;
        }
        .image-row {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            padding: 20px;
            border: 10px solid #FFD700;
            border-radius: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            background-color: #fff7e6;
            max-width: 1200px; 
            margin: 20px auto; 
        }
        .image-row img {
            width: 300px;
            height: 300px;
            border-radius: 20px;
            transition: transform 0.3s ease-in-out;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            object-fit: cover;
        }
        .image-row img:hover {
            transform: scale(1.1);
        }
        .chat-container {
            width: 1000px;  
            height: 600px; 
            display: flex;
            flex-direction: column;
            border: 2px solid #ff8c00;
            border-radius: 12px;
            padding: 10px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
            background-color: #fff3e0;
            margin-top: 20px;
            text-align: center; 
        }
        .chat-box {
            flex: 1;
            overflow-y: auto;
            padding: 10px;
            border: 1px solid #ffe0b2;
            border-radius: 10px;
            margin-bottom: 10px;
            background-color: #ffffff;
        }
        .chat-message {
            padding: 10px;
            margin: 5px 0;
            border-radius: 10px;
            background-color: #ffcc80;
            word-wrap: break-word;
            max-width: 80%;
            position: relative; 
            color: #000; 
        }
        .chat-label {
            color: #333;
            margin-bottom: 10px;
            font-weight: bold;
        }
        .input-box {
            display: flex;
        }
        .input-box input {
            flex: 1;
            padding: 10px;
            border: 1px solid #ffcc80;
            border-radius: 10px;
            outline: none;
            font-size: 14px;
        }
        .input-box button {
            padding: 10px 15px;
            margin-left: 5px;
            background-color: #ff8c00;
            border: none;
            color: #fff;
            border-radius: 10px;
            cursor: pointer;
            font-size: 14px;
        }
        .input-box button:hover {
            background-color: #e67e22;
        }
        .restaurant-list {
            list-style: none;
            padding: 0;
        }
        .restaurant-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 10px 0;
            font-weight: bold; 
        }
        .heart {
            margin-left: 15px; 
            font-size: 50px;
            color: grey;
            cursor: pointer;
            transition: color 0.3s;
        }
        .heart.liked {
            color: red;
        }
        .about-header,
        .rules-header {
            color: #DFAF8A; /* Pastel orange */
        }
        .about-paragraph,
        .rules-paragraph {
            color: #C88F66; /* Darker pastel orange */
        }
        .link-row {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            padding: 20px;
            border: 10px solid #D7C9E5; 
            border-radius: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            background-color: #fff7e6; 
            max-width: 90%;
            margin: 20px 0;
        }
        .link-row a {
            text-decoration: none;
            color: #6A0DAD; /* Text color */
            font-size: 20px; /* Font size */
        }
        h1 {
            color: #ff8c00; 
        }
        .collapsible {
    background-color: #333; /* Black background */
    color: white; /* White text */
    cursor: pointer;
    padding: 15px; 
    width: 80%; /* Set width to 80% for alignment */
    margin: 10px auto; /* Center it horizontally */
    border: none;
    text-align: left;
    outline: none;
    font-size: 40px; 
    transition: 0.4s;
    border-radius: 5px; 
    font-family: 'Calibri', sans-serif; /* Set font to Calibri */
}

        .content {
            padding: 0 18px;
            display: none;
            overflow: hidden;
            background-color: #222; /* Darker background for content */
            color: white; /* White text for content */
        }
    </style>
</head>
<body>

<h1 class="about-header">ABOUT THIS HANGOUT:</h1>
<p class="about-paragraph">This is a hangout all about people's favorite food, restaurants, and more! We have a (local) backend running that stores chat messages in a database. We have a list of local restaurants where you can browse. Explore and have fun!</p>

<button class="collapsible">MODERATION RULES</button>
<div class="content">
    <p class="rules-paragraph">1. Please do not use profanity in the hangout.</p>
    <p class="rules-paragraph">2. Please be respectful of others. Think before you chat or use any of the interactive features.</p>
    <p class="rules-paragraph">3. Reminder that your data is stored in a (local) backend.</p>
    <p class="rules-paragraph">4. Please do NOT spam flood the chat.</p>
    <p class="rules-paragraph">5. Stay on task. This hangout is for people to talk about food, recipes, and restaurants.</p>
    <p class="rules-paragraph">6. Do NOT impersonate people.</p>
</div>

<div class="image-row">
    <img src="https://cdn.prod.website-files.com/56f03b1536442f6b27f0f08c/5f03324cbb2506842953d137_worlds-best-foods-pizza.jpg" alt="Pizza">
    <img src="https://www.eatingwell.com/thmb/iCdLRBC1BMcDYKRYMTyyToQ8mRs=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/8401873-ad2429ae1858464a92229875c91c093d.jpg" alt="Pasta">
    <img src="https://thatdeliciousdish.com/wp-content/uploads/2020/07/Garlic-Mushroom-Noodles-Recipe-web1-1-800x840.jpg" alt="Ramen">
</div>

<div class="image-row">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTWAt_iSo2fSLH7dyuHxy4y-wsdsJ5dvH3FfQ&s" alt="Image 1">
    <img src="https://www.theglowwellness.com/wp-content/uploads/2022/03/208e6e4a-8cb0-1aca-65b2-29883634b00a-1080x1080.jpg" alt="Image 2">
    <img src="https://images-prod.healthline.com/hlcmsresource/images/AN_images/benefits-of-yerba-mate-1296x728-feature.jpg" alt="Image 3">
</div>

<div class="chat-container">
    <div class="chat-label">Chat Box</div>
    <div class="chat-box" id="chatBox">
        <!-- Messages will appear here -->
    </div>
    <div class="input-box">
        <input type="text" id="userName" placeholder="Enter your name..." />
        <input type="text" id="userInput" placeholder="Share a recipe or restaurant...">
        <button onclick="sendMessage()">Send</button>
    </div>
</div>

<h1>Local Restaurants</h1>
<ul class="restaurant-list">
    <li class="restaurant-item">
        <strong>Burger Lounge (Del Sur)</strong>
        <span class="heart" onclick="toggleHeart(this)">♡</span>
    </li>
    <li class="restaurant-item">
        <strong>Chick-fil-A (Del Sur)</strong>
        <span class="heart" onclick="toggleHeart(this)">♡</span>
    </li>
    <li class="restaurant-item">
        <strong>Board And Brew (Del Sur)</strong>
        <span class="heart" onclick="toggleHeart(this)">♡</span>
    </li>
    <li class="restaurant-item">
        <strong>Luna Grill (Del Sur)</strong>
        <span class="heart" onclick="toggleHeart(this)">♡</span>
    </li>
    <li class="restaurant-item">
        <strong>Piacere Mio Del Sur</strong>
        <span class="heart" onclick="toggleHeart(this)">♡</span>
    </li>
</ul>


<script>
    async function fetchMessages() {
        const response = await fetch('http://localhost:5000/messages');
        const messages = await response.json();
        messages.forEach(message => {
            displayMessage(message);
        });
    }

    async function sendMessage() {
        const userName = document.getElementById("userName").value.trim();
        const inputText = document.getElementById("userInput").value.trim();

        if (inputText !== "" && userName !== "") {
            const response = await fetch('http://localhost:5000/messages', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify({ user: userName, text: inputText }),
            });
            const message = await response.json();
            displayMessage(message);
            document.getElementById("userInput").value = ''; // Clear input box
        } else {
            alert("Please enter both your name and a message.");
        }
    }

    function displayMessage(message) {
        const messageDiv = document.createElement("div");
        messageDiv.classList.add("chat-message");
        messageDiv.innerHTML = `<strong>${message.user}</strong>: ${message.text}`; // Bold user name

        document.getElementById("chatBox").appendChild(messageDiv);
        document.getElementById("chatBox").scrollTop = document.getElementById("chatBox").scrollHeight; // Scroll to the bottom
    }

    // Fetch existing messages when the page loads
    window.onload = fetchMessages;

    function toggleHeart(element) {
        element.classList.toggle('liked');
        element.textContent = element.classList.contains('liked') ? '❤️' : '♡';
    }

    // Collapsible functionality for moderation rules
    const coll = document.getElementsByClassName("collapsible");
    for (let i = 0; i < coll.length; i++) {
        coll[i].addEventListener("click", function() {
            this.classList.toggle("active");
            const content = this.nextElementSibling;
            if (content.style.display === "block") {
                content.style.display = "none";
            } else {
                content.style.display = "block";
            }
        });
    }
</script>

</html>



<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Food Chat</title>
  
  <!-- Link to Google Fonts for Comfortaa font -->
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Comfortaa:wght@300;400;700&display=swap">
  
  <style>
    body { 
      font-family: 'Comfortaa', sans-serif; 
      display: flex; 
      justify-content: center; 
      background-color: #fafafa;
    }
    #chat-container { 
      width: 400px; 
      border: 2px solid #FFECB3; /* Pale yellow border */
      padding: 20px; 
      border-radius: 10px;
      background-color: #ffffff;
    }
    #chat-container h2 {
      color: black; /* Changed title color to black */
    }
    #messages { 
      height: 300px; 
      overflow-y: scroll; 
      border: 1px solid #FFECB3; /* Pale yellow border */
      padding: 10px; 
      margin-bottom: 10px; 
      border-radius: 5px;
      background-color: #fff8e1;
    }
    .message { 
      margin-bottom: 10px; 
      padding: 5px; 
      background: #fff8e1; /* Light yellow background */
      border-radius: 8px; 
      color: black; /* Message text color set to black */
    }
    .user { 
      font-weight: bold; 
      color: #333; 
    }
  </style>
</head>
<body>

<div id="chat-container">
  <h2>Food Chat Box</h2>

  <div id="messages"></div>

  <form id="chat-form">
    <input type="text" id="username" placeholder="Your name" required style="width: 100%; margin-bottom: 5px;">
    <textarea id="message" placeholder="Type a message" required style="width: 100%; height: 50px; margin-bottom: 5px;"></textarea>
    <input type="file" id="image" accept="image/*" style="width: 100%; margin-bottom: 5px;">
    <button type="submit" style="width: 100%;">Send</button>
  </form>
</div>

<script>
  const messagesContainer = document.getElementById('messages');
  const chatForm = document.getElementById('chat-form');

  chatForm.addEventListener('submit', function(e) {
    e.preventDefault();
    
    const username = document.getElementById('username').value;
    const message = document.getElementById('message').value;
    const imageFile = document.getElementById('image').files[0];

    // Create the message element
    const messageElement = document.createElement('div');
    messageElement.classList.add('message');
    messageElement.innerHTML = `<span class="user">${username}:</span> ${message}`;

    // Add image if uploaded
    if (imageFile) {
      const reader = new FileReader();
      reader.onload = function(event) {
        const img = document.createElement('img');
        img.src = event.target.result;
        img.style.maxWidth = '100%';
        img.style.marginTop = '5px';
        messageElement.appendChild(img);
      };
      reader.readAsDataURL(imageFile);
    }

    // Add the message element to messages container
    messagesContainer.appendChild(messageElement);
    messagesContainer.scrollTop = messagesContainer.scrollHeight; // Auto-scroll to latest message

    // Clear form inputs
    chatForm.reset();
  });
</script>

</body>
</html>
