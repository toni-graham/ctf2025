---
layout: default
title: Inject Me!
permalink: /challenge10/
---

# Inject Me!

The True Grit Bank prides itself on having spirit, determination, and… well, not much in the way of web security.

The bank's login page has been acting suspiciously lately. Customers claim they can “log in” without knowing any real credentials. The developers insist everything is perfectly safe, which—let's be honest—is usually the first sign that something is very wrong.

That's where you come in.

You've been hired as a digital troubleshooter:
Part detective, part hacker, part “I can't believe they deployed this to production.”

Your mission:

Visit the bank's external login page, poke at its weak spots, exploit the vulnerability lurking in plain sight, recover the hidden flag, and return here to submit your findings.

Stay sharp.
Stay clever.
Stay gritty.

Because at the True Grit Bank, the security may be flimsy…
but the challenge definitely isn't.
---

## 🔗

👉 **[True Grit Bank Account Login](https://toni-graham.github.io/sqli-challenge/)**  

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

    // Make sure the score is a number
    let score = parseInt(localStorage.getItem("ctfScore")) || 0;
    scoreDisplay.textContent = score;

    form.addEventListener("submit", function(e) {
      e.preventDefault();
      const userAnswer = document.getElementById("user-answer").value.trim().toLowerCase();

      const correctAnswer = "FLAG{Inj3ct10n_Succ3ss}";

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
