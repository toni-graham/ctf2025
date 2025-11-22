---
layout: default
title: Inject Me!
permalink: /challenge9/
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

Enter the flag you found:

<form action="" onsubmit="return checkFlag(event)">
  <input type="text" id="flag" placeholder="Enter your flag here" style="padding:10px;width:300px;">
  <button style="padding:10px;">Submit</button>
</form>

<p id="result"></p>

<script>
  const correctFlag = "FLAG{Inj3ct10n_Succ3ss}";

  function checkFlag(e) {
    e.preventDefault();
    const val = document.getElementById("flag").value.trim();
    if (val === correctFlag) {
      document.getElementById("result").innerText = "✅ Correct! Challenge completed.";
      score = parseInt(score) + 100;
      localStorage.setItem("ctfScore", score);
      scoreDisplay.textContent = score;
    } else {
      document.getElementById("result").innerText = "❌ Incorrect flag. Try again.";
    }
  }
</script>

