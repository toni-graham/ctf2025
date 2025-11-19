---
layout: default
title: Inject Me!
permalink: /challenge9/
---

# Inject Me!

Your task is to visit the external SQL Injection challenge, exploit the vulnerability, retrieve the flag, and return here to submit it.

---

## 🔗 Challenge URL

👉 **[Start the SQL Injection Challenge](https://yourusername.github.io/sqli-challenge)**  
*(Replace this link with your actual GitHub Pages URL.)*

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
      document.getElementById("result").innerText = "Correct! Challenge completed.";
    } else {
      document.getElementById("result").innerText = "Incorrect flag. Try again.";
    }
  }
</script>

---

## 📌 Instructions for Players

1. Click the link above to open the vulnerable login page.  
2. Perform an SQL Injection attack to bypass authentication.  
   
