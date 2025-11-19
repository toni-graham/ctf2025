<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>True Grit Bank Login</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #0d1117;
      color: #e6edf3;
      text-align: center;
      padding: 40px;
    }
    input {
      padding: 10px;
      margin: 8px;
      width: 250px;
      border-radius: 6px;
      border: 1px solid #30363d;
      background: #161b22;
      color: white;
    }
    button {
      padding: 10px 18px;
      border: none;
      background: #238636;
      color: white;
      border-radius: 6px;
      cursor: pointer;
    }
    #result {
      margin-top: 20px;
      font-size: 1.1em;
      white-space: pre-wrap;
    }
    .box {
      max-width: 500px;
      margin: auto;
      background: #161b22;
      padding: 30px;
      border-radius: 10px;
      border: 1px solid #30363d;
    }
  </style>
</head>
<body>
  <h1>True Grit Bank Login</h1>
  <p>Please enter your username and password.</p>

  <div class="box">
    <input type="text" id="user" placeholder="Username" />
    <br />
    <input type="password" id="pass" placeholder="Password" />
    <br />
    <button onclick="login()">Login</button>

    <div id="result"></div>
  </div>

  <script>
    /* Simulated database */
    const users = [
      { username: "admin", password: "supersecret", flag: "FLAG{Inj3ct10n_Succ3ss}" }
    ];

    /* Vulnerable login simulation: builds a fake SQL query string */
    function login() {
      const u = document.getElementById("user").value;
      const p = document.getElementById("pass").value;

      const query = `SELECT * FROM users WHERE username = '${u}' AND password = '${p}'`;

      // Display query to help players see vulnerability
      document.getElementById("result").innerText = `Query executed:\n${query}\n`;

      // Naive parser: checks if attacker uses ' OR '1'='1 style payload
      if (u.includes("'")) {
        document.getElementById("result").innerText += "\nLogin bypassed!\nFLAG{you_exploited_the_query}";
        return;
      }

      // Normal login check
      const match = users.find(acc => acc.username === u && acc.password === p);

      if (match) {
        document.getElementById("result").innerText += `\nWelcome, admin!\n${match.flag}`;
      } else {
        document.getElementById("result").innerText += "\nInvalid credentials.";
      }
    }
  </script>
</body>
</html>
