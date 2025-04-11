# Visbook
Visbook
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Franca - Social Universe</title>
  <style>
    * {margin: 0; padding: 0; box-sizing: border-box;}
    body {font-family: 'Segoe UI', sans-serif; background: #000; color: white;}
    .app {display: flex; flex-direction: column; height: 100vh;}

    /* STORIES */
    .stories {
      display: flex;
      overflow-x: auto;
      padding: 10px;
      background: #111;
    }
    .story {
      min-width: 70px;
      height: 70px;
      margin-right: 10px;
      border: 2px solid #ff004f;
      border-radius: 50%;
      background-size: cover;
      background-position: center;
      cursor: pointer;
      transition: transform 0.2s ease;
    }
    .story:hover {
      transform: scale(1.1);
    }

    /* FEED */
    .feed {
      flex: 1;
      overflow-y: scroll;
      scroll-snap-type: y mandatory;
    }
    .post {
      scroll-snap-align: start;
      border-bottom: 1px solid #333;
      padding: 10px;
    }
    .post img, .post video {
      width: 100%;
      max-height: 400px;
      object-fit: cover;
      border-radius: 12px;
      margin-top: 8px;
    }
    .post .user {
      font-weight: bold;
      margin-bottom: 5px;
    }

    /* REELS */
    .reels {
      display: none;
      position: absolute;
      top: 0; left: 0;
      height: 100%;
      width: 100%;
      background: black;
      overflow-y: scroll;
      scroll-snap-type: y mandatory;
      z-index: 5;
    }
    .reel {
      height: 100vh;
      scroll-snap-align: start;
      position: relative;
    }
    .reel video {
      height: 100%;
      width: 100%;
      object-fit: cover;
    }
    .reel .info {
      position: absolute;
      bottom: 80px;
      left: 15px;
      color: white;
    }

    /* NAVIGATION */
    .nav {
      display: flex;
      justify-content: space-around;
      padding: 10px;
      background: #111;
      border-top: 1px solid #222;
    }
    .nav button {
      background: none;
      border: 2px solid white;
      padding: 10px;
      border-radius: 50%;
      color: white;
      cursor: pointer;
      transition: all 0.2s ease;
    }
    .nav button:hover {
      transform: scale(1.1);
      background: #ff004f;
      border-color: #ff004f;
    }

    /* CAMERA DUMMY */
    .camera {
      display: none;
      position: absolute;
      top: 0; left: 0;
      width: 100%;
      height: 100%;
      background: #222;
      justify-content: center;
      align-items: center;
      z-index: 10;
    }

    /* CHAT & PROFILE PLACEHOLDERS */
    .chat, .profile {
      padding: 20px;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="app">

    <!-- STORIES -->
    <div class="stories">
      <div class="story" style="background-image:url('https://i.pravatar.cc/70?img=1')"></div>
      <div class="story" style="background-image:url('https://i.pravatar.cc/70?img=2')"></div>
      <div class="story" style="background-image:url('https://i.pravatar.cc/70?img=3')"></div>
      <div class="story" style="background-image:url('https://i.pravatar.cc/70?img=4')"></div>
    </div>

    <!-- FEED -->
    <div class="feed" id="feed">
      <div class="post">
        <div class="user">@captain_code</div>
        <img src="https://source.unsplash.com/400x300/?tech" />
        <p>Exploring AI with ChatGPT!</p>
      </div>
      <div class="post">
        <div class="user">@snapqueen</div>
        <video src="https://www.w3schools.com/html/mov_bbb.mp4" controls muted></video>
        <p>New vlog is live!</p>
      </div>
    </div>

    <!-- REELS -->
    <div class="reels" id="reels">
      <div class="reel">
        <video src="https://www.w3schools.com/html/movie.mp4" autoplay loop muted></video>
        <div class="info">@trendy_user - Dance Challenge</div>
      </div>
      <div class="reel">
        <video src="https://www.w3schools.com/html/mov_bbb.mp4" autoplay loop muted></video>
        <div class="info">@vibecreator - Chill vibes</div>
      </div>
    </div>

    <!-- CAMERA (Dummy UI) -->
    <div class="camera" id="camera">
      <h1>Camera Activated</h1>
    </div>

    <!-- NAVIGATION -->
    <div class="nav">
      <button onclick="showSection('feed')">🏠</button>
      <button onclick="showSection('reels')">▶️</button>
      <button onclick="showSection('camera')">📷</button>
      <button onclick="alert('Chat feature coming soon')">💬</button>
      <button onclick="alert('Profile feature coming soon')">👤</button>
    </div>
  </div>

  <script>
    function showSection(id) {
      document.getElementById('feed').style.display = 'none';
      document.getElementById('reels').style.display = 'none';
      document.getElementById('camera').style.display = 'none';
      if(document.getElementById(id)) {
        document.getElementById(id).style.display = 'block';
      }
    }
  </script>
</body>
</html>
