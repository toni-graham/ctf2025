---
layout: default
title: Woof Woof?
permalink: /challenge8/
---

# Woof Woof?

True Grit wants to tell you something; he does NOT want anybody else to know though. So he encrypted it using one of the methods you learned this weekend. Find out what True Grit is saying using an online decoder.

# Message: 
Mknx Zkbm ltrl matm NFUV bl max zkxtmxlm ngboxklbmr xoxk!

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

      const correctAnswer = "FLAG{True Grit says that UMBC is the greatest university ever!}";

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
