<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Hemant AI - The Virus ChatBot</title>
  <style>
    body {
      background-color: black;
      color: #00ff00;
      font-family: 'Courier New', monospace;
      margin: 0;
      padding: 0;
    }

    .container {
      max-width: 600px;
      margin: 40px auto;
      padding: 20px;
      border: 2px solid #00ff00;
      border-radius: 10px;
      background-color: #111;
    }

    #chat {
      height: 300px;
      overflow-y: auto;
      margin-bottom: 10px;
      padding-right: 10px;
    }

    .msg {
      margin: 10px 0;
    }

    .user { color: #00ffff; }
    .bot { color: #00ff00; }

    input {
      width: 100%;
      padding: 10px;
      background-color: #000;
      color: #00ff00;
      border: 1px solid #00ff00;
      font-size: 16px;
    }
  </style>
</head>
<body>
  <div class="container">
    <div id="chat">
      <p class="msg bot"><strong>Hemant AI:</strong> Welcome to the system, Hemant Virus activated...</p>
    </div>
    <input type="text" id="userInput" placeholder="Ask me anything..." autofocus />
  </div>

  <script>
    const chat = document.getElementById("chat");
    const input = document.getElementById("userInput");

    const smartReplies = (text) => {
      text = text.toLowerCase();
      if (text.includes("hello") || text.includes("hi")) return "Hey! Hemant AI is listening.";
      if (text.includes("your name")) return "I'm Hemant AI – a friendly virus!";
      if (text.includes("time")) return "Current time is: " + new Date().toLocaleTimeString();
      if (text.includes("date")) return "Today is: " + new Date().toDateString();
      if (text.includes("joke")) return "Why do hackers wear glasses? Because they can't C#!";
      if (text.includes("who made you")) return "I was coded by Hemant the Virus!";
      if (text.includes("bye")) return "Goodbye friend... System will sleep.";
      return [
        "Interesting...",
        "Processing...",
        "Hmmm... let me think...",
        "Hemant AI didn't understand that, try again!",
        "Accessing memory banks..."
      ][Math.floor(Math.random() * 5)];
    };

    input.addEventListener("keypress", function (e) {
      if (e.key === "Enter") {
        const userText = input.value.trim();
        if (userText === "") return;
        addMessage("You", userText, "user");

        setTimeout(() => {
          const reply = smartReplies(userText);
          addMessage("Hemant AI", reply, "bot");
        }, 600);

        input.value = "";
      }
    });

    function addMessage(sender, text, cls) {
      const msg = document.createElement("p");
      msg.className = `msg ${cls}`;
      msg.innerHTML = `<strong>${sender}:</strong> ${text}`;
      chat.appendChild(msg);
      chat.scrollTop = chat.scrollHeight;
    }
  </script>
</body>
</html>
