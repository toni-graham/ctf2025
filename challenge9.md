---
layout: default
title: Save Chip!
permalink: /challenge9/
---

# Save Chip!

Dr.Evil has taken chip hostage! Your mission is to enter Dr. Evil's laboratory and free Chip from Dr. Evil's vices. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: 
# __________________________________________________________
Type your answer below and submit to see if you're correct:

<div class="answer-box">
  <form id="answer-form">
    <input type="text" id="user-answer" placeholder="Enter your flag..." required>
    <button type="submit">Submit</button>
  </form>
  <div id="feedback"></div>
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    const form = document.getElementById("answer-form");
    const feedback = document.getElementById("feedback");
    const scoreDisplay = document.getElementById("scoreDisplay");

    // Make sure the score is a number
    let score = parseInt(localStorage.getItem("ctfScore")) || 0;
    scoreDisplay.textContent = score;

    form.addEventListener("submit", function(e) {
      e.preventDefault();
      const userAnswer = document.getElementById("user-answer").value.trim().toLowerCase();

      const correctAnswer = "FLAG{w4rm1ng_Up_w1tH_jAv4_3808d338b46}";

      if (userAnswer === correctAnswer) {
        feedback.textContent = "✅ Correct!";
        feedback.style.color = "#00ff99";

        // Add 100 points properly
        score = parseInt(score) + 100;
        localStorage.setItem("ctfScore", score);
        scoreDisplay.textContent = score;
      } else {
        feedback.textContent = "❌ Wrong answer, try again!";
        feedback.style.color = "#ff0066";
      }
    });
  });
</script>
