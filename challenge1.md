---
layout: default
title: Challenge 1
permalink: /Chip-Or-Treat!/
---

# Chip-Or-Treat!

You are sitting in the commons and overhear some students talking about our police dog Chip. 
“Did you see Chip's Halloween costume?”
“Yeah! She was so cute! ..”

You love dogs but somehow missed seeing Chip during halloween, What was chip for Halloween?

#__________________________________________________________

Type your answer below and submit to see if you're correct:

<div class="answer-box">
  <input type="text" id="answerInput" placeholder="Enter your flag..." />
  <button onclick="checkAnswer()">Submit</button>
  <p id="feedback"></p>
</div>

<script>
  function checkAnswer() {
    const correctAnswer = "CTF{dinosaur}";
    const userAnswer = document.getElementById("answerInput").value.trim();
    const feedback = document.getElementById("feedback");

    if (userAnswer === correctAnswer) {
      feedback.textContent = "✅ Correct! You solved it!";
      feedback.style.color = "#00ffcc";
      feedback.style.textShadow = "0 0 10px #00ffcc, 0 0 20px #00ffcc";
    } else {
      feedback.textContent = "❌ Incorrect, try again.";
      feedback.style.color = "#ff0066";
      feedback.style.textShadow = "0 0 10px #ff0066, 0 0 20px #ff0066";
    }
  }
</script>
