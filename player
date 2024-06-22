
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>livestream</title>
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <script src="https://vip4ktv.online/js.html"></script>
  <style>
    body {
      margin: 0px;
    }
    .jwplayer {
      position: absolute !important;
    }
    .jwplayer.jw-flag-aspect-mode {
      min-height: 100%;
      max-height: 100%;
    }
    .loading {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: #000;
      z-index: 9999;
    }
    .loading-text {
      position: absolute;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      margin: auto;
      text-align: center;
      width: 100%;
      height: 100px;
      line-height: 100px;
    }
    .loading-text span {
      display: inline-block;
      margin: 0 1px;  /* Reduced margin to reduce space between letters */
      color: #fb3ea2;
      font-family: 'Quattrocento Sans', sans-serif;
      font-size: 18px; /* Increased font size */
      filter: blur(0px);
      animation: blur-text 1.5s infinite linear alternate, color-change 10s infinite;
    }
    .loading-text span:nth-child(1) {
      animation-delay: 0s;
    }
    .loading-text span:nth-child(2) {
      animation-delay: 0.2s;
    }
    .loading-text span:nth-child(3) {
      animation-delay: 0.4s;
    }
    .loading-text span:nth-child(4) {
      animation-delay: 0.6s;
    }
    .loading-text span:nth-child(5) {
      animation-delay: 0.8s;
    }
    .loading-text span:nth-child(6) {
      animation-delay: 1s;
    }
    .loading-text span:nth-child(7) {
      animation-delay: 1.2s;
    }
    .loading-text span:nth-child(8) {
      animation-delay: 1.4s;
    }
    .loading-text span:nth-child(9) {
      animation-delay: 1.6s;
    }
    @keyframes blur-text {
      0% {
        filter: blur(0px);
      }
      100% {
        filter: blur(1px);
      }
    }
    @keyframes color-change {
      0% {
        color: #fb3ea2;
      }
      25% {
        color: #3d7afd;
      }
      50% {
        color: #ffaa2c;
      }
      75% {
        color: #7fff00;
      }
      100% {
        color: #fb3ea2;
      }
    }
  </style>
</head>
<body>
  <div id="loading" class="loading">
    <div class="loading-text">
      <span class="loading-text-words"><span>O</span></span>
      <span class="loading-text-words"><span>F</span></span>
      <span class="loading-text-words"><span> F</span></span>
      <span class="loading-text-words"><span>L</span></span>
      <span class="loading-text-words"><span>I</span></span>
      <span class="loading-text-words"><span>N</span></span>
      <span class="loading-text-words"><span>E</span></span>
      <span class="loading-text-words"><span>™</span></span>
    </div>
  </div>
  <div id="jwplayerDiv"></div>
  <script type="text/javascript">
    // Function to get URL parameters
    const getUrlParameter = (name, url = window.location.href) => {
      name = name.replace(/[\[\]]/g, "\\$&");
      const regex = new RegExp("[?&]" + name + "(=([^&#]*)|&|#|$)");
      const results = regex.exec(url);
      if (!results) return null;
      if (!results[2]) return "";
      return decodeURIComponent(results[2].replace(/\+/g, " "));
    };

    // Define player setup function
    const setupPlayer = (url) => {
      console.log("Setting up player with URL:", url);
      let playerSetup = {
        file: url,
        position: "bottom",
        autostart: true,
        stretching: "exactfit",
        width: "100%",
        type: url.endsWith(".mpd") ? "dash" : "hls",
      };

      jwplayer("jwplayerDiv").setup(playerSetup);
    };

    // Function to check if the video is playing
    const isVideoPlaying = () => {
      const playerState = jwplayer().getState();
      return playerState === "playing" || playerState === "buffering";
    };

    // Function to reload the video if it's not playing
    const checkAndReloadVideo = (videoUrl) => {
      if (!isVideoPlaying()) {
        console.log("Video is not playing. Reloading...");
        setupPlayer(videoUrl);
      }
    };

    // Construct video URL and set up the player
    const videoId = getUrlParameter('id');
    const baseUrl = '';
    const videoUrl = baseUrl + videoId;

    if (videoId) {
      // Hide URL parameters from address bar after setting up the player with a delay
      setTimeout(() => {
        window.history.replaceState({}, document.title, window.location.pathname);
      }, 100); // Adjust delay if necessary

      // Check and reload the video every 5 seconds if it's not playing
      setInterval(() => {
        checkAndReloadVideo(videoUrl);
      }, 5000); // Check every 5 seconds

      setupPlayer(videoUrl);
      
      // Hide loading animation after 15 seconds
      setTimeout(() => {
        document.getElementById('loading').style.display = 'none';
      }, 5000);
    } else {
      console.error('The "id" parameter is required in the URL.');
    }
  </script>
</body>
</html>
