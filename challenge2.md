---
layout: default
title: Chip's Birthday?
permalink: /challenge2/
---

# Chip's Birthday?

As the students continue their conversation (and you continue eavesdropping) you hear them talk about Chip's birthday. They can’t seem to come up with an exact date - it’s a mystery.

What is Chip’s birthday?

# __________________________________________________________
Type your answer below and submit to see if you're correct:

<div class="answer-box">
  <input type="text" id="answerInput" placeholder="Enter your flag..." />
  <button onclick="checkAnswer()">Submit</button>
  <p id="feedback"></p>
</div>

<script>
  function checkAnswer() {
    const correctAnswer = "CTF{6/23/2019}";
    const userAnswer = document.getElementById("answerInput").value.trim();
    const feedback = document.getElementById("feedback");

    if (userAnswer === correctAnswer) {
      feedback.textContent = "✅ Correct! You solved it!";
      feedback.style.color = "#00ffcc";
      feedback.style.textShadow = "0 0 10px #00ffcc, 0 0 20px #00ffcc";
      answerBox.classList.remove("shake");
    } else {
      feedback.textContent = "❌ Incorrect, try again.";
      feedback.style.color = "#ff0066";
      feedback.style.textShadow = "0 0 10px #ff0066, 0 0 20px #ff0066";

      // Trigger shake animation
      answerBox.classList.remove("shake");
      void answerBox.offsetWidth; // restart animation
      answerBox.classList.add("shake");
    }
  }
</script>
