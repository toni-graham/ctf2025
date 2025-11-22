---
layout: default
title: The Curious Whois Tool
permalink: /challenge11/
---

# The Curious Whois Tool

The True Grit IT Department created a “simple” domain lookup tool to help students check whether their project domains are available.

The developer, however, made one small mistake…

They take user input and directly place it into a system command.

### Your Mission  
Use OS Command Injection to make the server run **your** command, locate the hidden flag on the system, and submit it below.

---

## 🔗 Vulnerable Whois Tool  
👉 **[Open the Whois Lookup](./osinj-app/)**

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

      const userAnswer = document.getElementById("user-answer").value.trim();
      const correctAnswer = "FLAG{0S_1NJ3CT10N_C0MP13T3}";

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
