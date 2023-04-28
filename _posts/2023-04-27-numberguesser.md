---
toc: true
layout: base
description: Game
categories: [markdown, Week 20]
title: Number Guesser
---
## Hacks Part 3

<html>
<head>
  <title>Guess the Number</title>
  <link rel="stylesheet" href="/devops/assets/css/game.css">
</head>
<body>

  <h1>Guess the Number</h1>
  <p id="numberguessor">Try to guess the number between 1 and 100.</p>
  <input type="text" id="guess" placeholder="Enter your guess">
  <button is="button" onclick="checkGuess()">Submit</button>
  <p id="result"></p>
  <script>
    // Generate a random number between 1 and 100
    const randomNumber = Math.floor(Math.random() * 100) + 1;
    let attempts = 0;

    function checkGuess() {
      // Get the user's guess
      const guess = parseInt(document.getElementById("guess").value);

      // Increase the number of attempts
      attempts++;

      // Check if the guess is correct
      if (guess === randomNumber) {
        document.getElementById("result").innerHTML = `Congratulations! You guessed the number in ${attempts} attempts.`;
      } else if (guess < randomNumber) {
        document.getElementById("result").innerHTML = "Too low. Guess again.";
      } else {
        document.getElementById("result").innerHTML = "Too high. Guess again.";
      }
    }
  </script>
</body>
</html>
