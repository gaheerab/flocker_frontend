---
toc: true
layout: post
description: Select A Channel and Start Discussing!
title: Voting Chatroom
permalink: /chatroom
comments: true
---
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chat Platform</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #1c1e24;
            color: #fff;
            margin: 0;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center !important;
        }

        .container {
            width: 300%;
            max-width: 800px;
        }

        h1 {
            font-size: 2em;
            margin-bottom: 10px;
        }

        .card {
            background-color: pink;
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 20px;
            margin-right: 200px;
        }

        .card h2 {
            font-size: 1.5em;
            margin-bottom: 10px;
        }

        .card label {
            display: block;
            margin-top: 10px;
        }

        .card select,
        .card input[type="text"],
        .card textarea {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border-radius: 5px;
            border: none;
            background-color: #1c1e24;
            color: #fff;
        }

        .button {
            background-color: #4a90e2;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
        }

        .post-item {
            background-color: #DE3163;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 20px;
            border: 1px solid #444;
        }

        .post-item h3 {
            margin: 0;
            font-size: 1.2em;
        }

        .post-item p {
            margin: 10px 0;
            color: #ddd;
        }

        .post-item small {
            color: #aaa;
        }

        .like-button {
            background: none;
            border: none;
            color: #ff69b4;
            font-size: 15px;
            cursor: pointer;
            margin-top: 10px;
        }

        .like-button span {
            margin-left: 5px;
            color: #fff;
        }
    </style>
</head>
<body>
    <div class="container">

        <!-- Group and Channel Selection -->
        <div class="card">
            <label for="group">Group:</label>
            <select id="group">
                <option value="general">General</option>
                <option value="private">Private</option>
            </select>

            <label for="channel">Channel:</label>
            <select id="channel">
                <option value="The Weeknd OR Lana Del Rey">The Weeknd or Lana Del Rey</option>
                <option value="RHCP OR Guns N' Roses">RHCP or Guns N' Roses</option>
                <option value="Ella Fitzgerald OR Billie Holiday">Ella Fitzgerald or Billie Holiday</option>
                <option value="Calvin Harris OR Alan Walker">Calvin Harris or Alan Walker</option>
                <option value="Drake OR Kanye West">Drake or Kanye West</option>
                <option value="Mozart OR Beethoven">Mozart or Beethoven</option>
            </select>

            <button class="button" onclick="loadPosts()">Select</button>
        </div>

        <!-- Post Creation -->
        <div class="card">

            <label for="title">Title:</label>
            <input type="text" id="title" placeholder="Enter title...">

            <label for="comment">Comment:</label>
            <textarea id="comment" rows="4" placeholder="Enter your comment..."></textarea>

            <button class="button" onclick="addPost()">Add Post</button>
        </div>

        <!-- Post Feed -->
        <div class="card" id="post-feed">
            <h2>Posts</h2>
            <div id="posts"></div>
        </div>
    </div>

    <script>
        const postFeedDiv = document.getElementById('posts');
        const titleInput = document.getElementById('title');
        const commentInput = document.getElementById('comment');
        const groupSelect = document.getElementById('group');
        const channelSelect = document.getElementById('channel');

        // Load posts from localStorage when the page loads
        let posts = JSON.parse(localStorage.getItem('chatPosts')) || {};

        // Function to add a new post
        function addPost() {

            const channel = document.getElementById("channel").value;

            let channel_id = 17

            if (channel === "The Weeknd OR Lana Del Rey") {
                let channel_id = 17
            } else if (channel === "RHCP OR Guns N Roses") {
                let channel_id = 19
            } else if (channel === "Ella Fitzgerald OR Billie Holiday") {
                let channel_id = 20
            } else if (channel === "Drake OR Kanye West") {
                let channel_id = 21
            } else if (channel === "Mozart OR Bethoven") {
                let channel_id = 22
            }

            const title = titleInput.value.trim();
            const comment = commentInput.value.trim();

            if (title === '' || comment === '') {
                alert("Please enter both a title and a comment.");
            }

            const myHeaders = new Headers();
            myHeaders.append("Content-Type", "application/json");
            myHeaders.append("Cookie", "jwt_python_flask=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfdWlkIjoibmlrbyJ9.q7FKOl0eGTDRhPKYBAROAP9FB3kv_wHzZatcAxihso4");

            const raw = JSON.stringify({
                "title": title,
                "comment": title,
                "channel_id": channel_id
            });

            const requestOptions = {
                method: "POST",
                headers: myHeaders,
                body: raw,
                redirect: "follow"
            };

            fetch("http://127.0.0.1:8887/api/post", requestOptions)
                .then((response) => response.text())
                .then((result) => console.log(result))
                .catch((error) => console.error(error));

            // Clear the input fields
            titleInput.value = '';
            commentInput.value = '';

            // Reload posts
            loadPosts();
        }

        // Function to load posts for the selected group and channel
        function loadPosts() {
            const group = groupSelect.value;
            const channel = channelSelect.value;

            // Clear the post feed display
            postFeedDiv.innerHTML = '';

            // Display posts for the selected group and channel
            if (posts[group] && posts[group][channel]) {
                posts[group][channel].forEach(post => {
                    const postDiv = document.createElement('div');
                    postDiv.classList.add('post-item');
                    postDiv.innerHTML = `
                        <h3>${post.title}</h3>
                        <p>${post.comment}</p>
                        <small>Posted on: ${post.timestamp}</small><br>
                        <button class="like-button" onclick="likePost(event)">
                            ${post.likedByUser ? '❤️' : '🤍'} <span id="like-count-${post.timestamp}">${post.likes}</span>
                        </button>
                    `;
                    postFeedDiv.appendChild(postDiv);
                });
            } else {
                postFeedDiv.innerHTML = '<p>No posts available for this channel. Be the first to add one!</p>';
            }
        }

        // Function to like or unlike a post
        function likePost(event) {
            const postDiv = event.target.closest('.post-item');
            const postTitle = postDiv.querySelector('h3').innerText;

            const group = groupSelect.value;
            const channel = channelSelect.value;

            let post = posts[group][channel].find(p => p.title === postTitle);

            // Toggle like state
            if (post.likedByUser) {
                post.likes--;
                post.likedByUser = false;
            } else {
                post.likes++;
                post.likedByUser = true;
            }

            // Update the like count and button
            const likeCount = postDiv.querySelector('span');
            const likeButton = postDiv.querySelector('button');

            likeCount.textContent = post.likes;
            likeButton.innerHTML = post.likedByUser ? '❤️ <span>' + post.likes + '</span>' : '🤍 <span>' + post.likes + '</span>';

            // Save the updated post
            localStorage.setItem('chatPosts', JSON.stringify(posts));
        }

        // Initial load of posts
        loadPosts();
    </script>
</body>
</html>
