<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>WD Resume Fix</title>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700&display=swap" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/emailjs-com@3/dist/email.min.js"></script>
  <script>
    (function(){
      emailjs.init("C6K9PyesFwf9DIt9l");
    })();
  </script>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      background-color: #111;
      font-family: Arial, sans-serif;
      color: white;
    }
    header {
      background-color: #000;
      padding: 15px 40px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    nav { display: flex; width: 100%; justify-content: space-between; align-items: center; }
    .logo-circle {
      width: 25px;
      height: 25px;
      background: linear-gradient(to right, red 50%, white 50%);
      border-radius: 50%;
    }
    .right-icons { display: flex; gap: 10px; }
    .circle-icon {
      width: 20px;
      height: 20px;
      background-color: #333;
      border-radius: 50%;
    }
    .hero {
      text-align: center;
      padding: 60px 20px;
    }
    .brand-name {
      font-family: 'Cinzel', serif;
      color: red;
      font-size: 70px;
      letter-spacing: 6px;
      animation: popOut 1s ease-out forwards;
    }
    @keyframes popOut {
      0% { transform: scale(0.5); opacity: 0; }
      60% { transform: scale(1.2); opacity: 1; }
      100% { transform: scale(1); }
    }
    .deadpool-img {
      max-width: 300px;
      width: 100%;
      height: auto;
    }
    .buttons { margin-top: 30px; }
    button {
      padding: 12px 25px;
      font-size: 16px;
      margin: 0 10px;
      border: none;
      cursor: pointer;
      border-radius: 30px;
      transition: 0.3s;
    }
    .book-now { background-color: red; color: white; }
    .book-now:hover { background-color: darkred; }
    .modal {
      display: none;
      position: fixed;
      z-index: 10;
      left: 0; top: 0;
      width: 100%; height: 100%;
      background-color: rgba(0,0,0,0.7);
    }
    .modal-content {
      background-color: #1f1f1f;
      margin: 10% auto;
      padding: 20px;
      width: 90%; max-width: 400px;
      border-radius: 10px;
      text-align: center;
      color: white;
    }
    .modal-content input,
    .modal-content select,
    .modal-content textarea {
      width: 80%;
      padding: 10px;
      margin-top: 15px;
      font-size: 16px;
      border-radius: 8px;
      border: none;
    }
    .close {
      color: #aaa;
      float: right;
      font-size: 28px;
      font-weight: bold;
      cursor: pointer;
    }
    .close:hover { color: white; }
    .socials {
      text-align: center;
      margin-top: 40px;
    }
    .socials a {
      color: #f44336;
      margin: 0 10px;
      font-weight: bold;
      text-decoration: none;
    }
  </style>
</head>
<body>

  <header>
    <nav>
      <div class="logo-circle"></div>
      <div class="right-icons">
        <div class="circle-icon"></div>
        <div class="circle-icon"></div>
      </div>
    </nav>
  </header>

  <section class="hero">
    <h1 class="brand-name">WD Resume Fix</h1>
    <img src="https://i.ibb.co/Kx7JF0Bh/426a79ea78b44abd1c36414389a57d31.jpg" alt="Character" class="deadpool-img" />
    <div class="buttons">
      <button class="book-now" onclick="openModal()">Book Now</button>
    </div>
  </section>

  <div id="bookingModal" class="modal">
    <div class="modal-content">
      <span class="close" onclick="closeModal()">&times;</span>
      <h2>What do you want to build?</h2>
      <form id="emailForm">
        <input type="text" name="from_name" placeholder="Your Name" required />
        <input type="email" name="reply_to" placeholder="Your Email" required />
        <select name="service">
          <option value="Resume">Resume</option>
          <option value="Logo">Logo</option>
          <option value="Design">Design</option>
          <option value="Photo">Custom Photo Made</option>
        </select>
        <textarea name="message" rows="4" placeholder="Message (Optional)"></textarea>
        <button type="submit">Submit</button>
      </form>
    </div>
  </div>

  <div class="socials">
    <p>Follow us on Instagram:</p>
    <a href="https://www.instagram.com/wins_chauhan/" target="_blank">Wins</a>
    <a href="https://www.instagram.com/daksh471/" target="_blank">Daksh</a>
  </div>

  <script>
    function openModal() {
      document.getElementById("bookingModal").style.display = "block";
    }

    function closeModal() {
      document.getElementById("bookingModal").style.display = "none";
    }

    window.onclick = function(event) {
      const modal = document.getElementById("bookingModal");
      if (event.target === modal) {
        modal.style.display = "none";
      }
    }

    document.getElementById("emailForm").addEventListener("submit", function(e) {
      e.preventDefault();
      emailjs.sendForm("service_xotibp9", "template_tzvdsh4", this)
        .then(function() {
          alert("Message sent successfully!");
          closeModal();
        }, function(error) {
          alert("Failed to send: " + JSON.stringify(error));
        });
    });
  </script>
</body>
</html>
