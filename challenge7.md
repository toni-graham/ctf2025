---
layout: default
title: Crack the Safe?
permalink: /challenge7/
---

# Crack the Safe?

Can you open this safe? I forgot the key to my safe but this program is supposed to help me with retrieving the lost key. Can you help me unlock my safe?
You can download the secret file [SafeOpener](SafeOpener.java){:download="SafeOpener.java"}.


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

      const correctAnswer = "FLAG{pl3as3_l3t_m3_1nt0_th3_saf3}";

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
