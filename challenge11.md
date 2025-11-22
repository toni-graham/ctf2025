---
layout: default
title: Chirp Chirp!
permalink: /challenge11/
---

# Chirp Chirp

You just got out of your 11:30am class and your 1pm class was just canceled. With no class until 4pm you decide to eat lunch by the library pond. A charm of sparrows land on the railing, you think they are trying to tell you something.

What are the birds trying to tell you?


![Click here to find out what the birds are trying to tell you!](Screenshot 2025-11-22 162146.png)

(capitalize and separate you words with underscores when submitting your flag)

---

## 🏁 Submit Your Flag

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

    let score = parseInt(localStorage.getItem("ctfScore")) || 0;
    scoreDisplay.textContent = score;

    form.addEventListener("submit", function(e) {
      e.preventDefault();

      const userAnswer = document.getElementById("user-answer").value.trim().toUpper();
      const correctAnswer = "FLAG{DONT_FORGET_THE_EXAM}";

      if (userAnswer === correctAnswer) {
        feedback.textContent = "✅ Correct!";
        feedback.style.color = "#00ff99";
        score += 100;
        localStorage.setItem("ctfScore", score);
        scoreDisplay.textContent = score;
      } else {
        feedback.textContent = "❌ Wrong answer, try again!";
        feedback.style.color = "#ff0066";
      }
    });
  });
</script>
