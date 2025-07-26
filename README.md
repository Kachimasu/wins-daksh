<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Daksh & Wins</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

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

    nav {
      display: flex;
      width: 100%;
      justify-content: space-between;
      align-items: center;
    }

    .nav-links {
      list-style: none;
      display: flex;
      gap: 25px;
    }

    .nav-links li a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      transition: 0.3s;
    }

    .nav-links li a:hover {
      color: #f44336;
    }

    .logo-circle {
      width: 25px;
      height: 25px;
      background: linear-gradient(to right, red 50%, white 50%);
      border-radius: 50%;
    }

    .right-icons {
      display: flex;
      gap: 10px;
    }

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

    .hero h1 {
      font-size: 70px;
      font-weight: bold;
      color: white;
      letter-spacing: 8px;
      margin-bottom: 20px;
      animation: popOut 1s ease-out forwards;
    }

    @keyframes popOut {
      0% {
        transform: scale(0.5);
        opacity: 0;
      }
      60% {
        transform: scale(1.2);
        opacity: 1;
      }
      100% {
        transform: scale(1);
      }
    }

    .deadpool-img {
      max-width: 300px;
      width: 100%;
      height: auto;
    }

    .buttons {
      margin-top: 30px;
    }

    button {
      padding: 12px 25px;
      font-size: 16px;
      margin: 0 10px;
      border: none;
      cursor: pointer;
      border-radius: 30px;
      transition: 0.3s;
    }

    .book-now {
      background-color: red;
      color: white;
    }

    .book-now:hover {
      background-color: darkred;
    }

    .tickets {
      background-color: transparent;
      border: 2px solid white;
      color: white;
    }

    .tickets:hover {
      background-color: white;
      color: black;
    }

    /* Modal */
    .modal {
      display: none;
      position: fixed;
      z-index: 10;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background-color: rgba(0,0,0,0.7);
    }

    .modal-content {
      background-color: #1f1f1f;
      margin: 10% auto;
      padding: 20px;
      border: 1px solid #888;
      width: 90%;
      max-width: 400px;
      border-radius: 10px;
      text-align: center;
    }

    .modal-content select,
    .modal-content input[type="email"] {
      width: 80%;
      padding: 10px;
      margin-top: 15px;
      font-size: 16px;
      border-radius: 8px;
      border: none;
    }

    .modal-content button[type="submit"] {
      margin-top: 15px;
      background-color: red;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 8px;
      cursor: pointer;
      font-size: 16px;
    }

    .close {
      color: #aaa;
      float: right;
      font-size: 28px;
      font-weight: bold;
      cursor: pointer;
    }

    .close:hover {
      color: white;
    }
  </style>
</head>
<body>

  <header>
    <nav>
      <div class="logo-circle"></div>
      <ul class="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">Booking</a></li>
        <li><a href="#">Tickets</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Socials</a></li>
      </ul>
      <div class="right-icons">
        <div class="circle-icon"></div>
        <div class="circle-icon"></div>
      </div>
    </nav>
  </header>

  <section class="hero">
    <h1>DAKSH & WINS</h1>
    <img src="https://i.ibb.co/Kx7JF0Bh/426a79ea78b44abd1c36414389a57d31.jpg" alt="Character" class="deadpool-img" />
    <div class="buttons">
      <button class="book-now" onclick="openModal()">Book Now</button>
      <button class="tickets">Tickets</button>
    </div>
  </section>

  <!-- Modal Form -->
  <div id="bookingModal" class="modal">
    <div class="modal-content">
      <span class="close" onclick="closeModal()">&times;</span>
      <form action="https://formsubmit.co/winschauhan8@gmail.com" method="POST">
        <h2>What do you want to build?</h2>
        <select name="service" required>
          <option value="">-- Select --</option>
          <option value="Resume">Resume</option>
          <option value="Logo">Logo</option>
          <option value="Design">Design</option>
          <option value="Custom Photo Made">Custom Photo Made</option>
        </select>
        <input type="email" name="email" placeholder="Your Email" required />
        <button type="submit">Submit</button>
      </form>
    </div>
  </div>

  <script>
    function openModal() {
      document.getElementById('bookingModal').style.display = 'block';
    }

    function closeModal() {
      document.getElementById('bookingModal').style.display = 'none';
    }

    window.onclick = function(event) {
      const modal = document.getElementById('bookingModal');
      if (event.target === modal) {
        modal.style.display = 'none';
      }
    }
  </script>

</body>
</html>
