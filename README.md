<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Game Earn Pro</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background-color: #f2f2f2;
    }
    header {
      background-color: #222;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    nav {
      background: #444;
      display: flex;
      justify-content: center;
      gap: 1rem;
      padding: 0.5rem;
    }
    nav a {
      color: white;
      text-decoration: none;
    }
    section {
      padding: 2rem;
      max-width: 1000px;
      margin: auto;
    }
    .game-box, .ad-box {
      border: 2px dashed #aaa;
      padding: 2rem;
      text-align: center;
      background: white;
      margin-top: 1rem;
    }
    button {
      padding: 0.5rem 1rem;
      background: #28a745;
      color: white;
      border: none;
      cursor: pointer;
      font-size: 1rem;
    }
    #coin-display {
      font-size: 1.2rem;
      margin-top: 1rem;
      font-weight: bold;
      color: #333;
    }
    .ad-box p.timer {
      font-size: 1.5rem;
      color: #e74c3c;
      font-weight: bold;
    }
    footer {
      background: #222;
      color: white;
      text-align: center;
      padding: 1rem;
      margin-top: 2rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>🎮 Game Earn Pro</h1>
    <p>Play Games. Watch Ads. Win Rewards!</p>
  </header>

  <nav>
    <a href="#home">Home</a>
    <a href="#play">Play & Earn</a>
    <a href="#how">How It Works</a>
    <a href="#contact">Contact</a>
  </nav>

  <section id="home">
    <h2>Welcome to Game Earn Pro</h2>
    <p>Start earning today by playing simple games and watching sponsored ads.</p>
  </section>

  <section id="play">
    <h2>🎯 Play & Earn</h2>
    <div class="game-box">
      <p>Click the button as fast as you can!</p>
      <button onclick="earnCoin()">Click Me!</button>
      <div id="coin-display">Coins: 0</div>
    </div>
    <div class="ad-box">
      <p>Watch this ad to earn 5 more coins 💰</p>
      <p class="timer" id="ad-timer">Ad in: 5</p>
      <button onclick="startAdTimer()">Watch Ad</button>
    </div>
  </section>

  <section id="how">
    <h2>📜 How It Works</h2>
    <ul>
      <li>1. Play mini games and have fun.</li>
      <li>2. Watch short ads during or after gameplay.</li>
      <li>3. Earn coins that can be redeemed (demo only).</li>
    </ul>
  </section>

  <section id="contact">
    <h2>📧 Contact Us</h2>
    <form>
      <label>Name:</label><br />
      <input type="text" /><br /><br />
      <label>Email:</label><br />
      <input type="email" /><br /><br />
      <label>Message:</label><br />
      <textarea rows="4" cols="40"></textarea><br /><br />
      <button type="submit">Send</button>
    </form>
  </section>

  <footer>
    &copy; 2025 Game Earn Pro | Designed for Demo Purpose
  </footer>

  <script>
    let coins = 0;
    const coinDisplay = document.getElementById('coin-display');

    function earnCoin() {
      coins++;
      coinDisplay.textContent = 'Coins: ' + coins;
    }

    function startAdTimer() {
      let timeLeft = 5;
      const timer = document.getElementById('ad-timer');
      timer.textContent = 'Ad in: ' + timeLeft;

      const countdown = setInterval(() => {
        timeLeft--;
        timer.textContent = 'Ad in: ' + timeLeft;
        if (timeLeft <= 0) {
          clearInterval(countdown);
          coins += 5;
          coinDisplay.textContent = 'Coins: ' + coins;
          timer.textContent = 'Thanks for watching! +5 coins';
        }
      }, 1000);
    }
  </script>
</body>
</html>
