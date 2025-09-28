# Dandiya-NIght
This HTML page showcases a vibrant event booking form for Dandiya Nights at Dev Bhoomi Uttarakhand University. It features animated gradient backgrounds, styled event details, a student pass registration form, and a dynamically generated QR code for more info.

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Dandiya Nights – Dev Bhoomi Uttarakhand University</title>
  <script src="https://cdn.jsdelivr.net/npm/qrcode/build/qrcode.min.js"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');

    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      color: #333;
      background: linear-gradient(-45deg, #ff6ec4, #7873f5, #f9d423, #ff4e50);
      background-size: 400% 400%;
      animation: gradientBG 15s ease infinite;
    }

    @keyframes gradientBG {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .content {
      max-width: 800px;
      margin: 60px auto;
      background: #fff0e6; /* Changed from white to peach */
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 20px rgba(0,0,0,0.2);
    }

    h2 {
      text-align: center;
      color: #d81b60;
      font-family: 'Anton', sans-serif;
      font-size: 2em;
      letter-spacing: 1px;
    }

    .details {
      font-family: 'Anton', sans-serif;
      font-size: 1.2em;
      letter-spacing: 0.5px;
      line-height: 1.6;
      color: #444;
    }

    .details p {
      margin: 10px 0;
    }

    form {
      margin-top: 30px;
    }

    label {
      display: block;
      margin-top: 15px;
      font-weight: bold;
    }

    input, select, button {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    button {
      background-color: #d81b60;
      color: white;
      font-weight: bold;
      cursor: pointer;
      margin-top: 20px;
    }

    button:hover {
      background-color: #ad1457;
    }

    #qrcode {
      margin-top: 40px;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="content">
    <h2>Event Details</h2>
    <div class="details">
      <p><strong>📍 Venue:</strong> College Sports Ground</p>
      <p><strong>📅 Date:</strong> October 5, 2025</p>
      <p><strong>🕕 Time:</strong> 6:00 PM onwards</p>
      <p><strong>🎟️ Entry:</strong> Free</p>
      <p>Experience the most exciting performances, competitions, and cultural celebrations at Dev Bhoomi Uttarakhand University!</p>
    </div>

    <form id="bookingForm">
      <h2>Book Your Pass</h2>
      <label for="name">Student Name</label>
      <input type="text" id="name" required />

      <label for="email">Email</label>
      <input type="email" id="email" required />

      <label for="seat">Seat Type</label>
      <select id="seat" required>
        <option value="">--Select--</option>
        <option value="General">General</option>
        <option value="Front Row">Front Row</option>
        <option value="VIP">VIP</option>
      </select>

      <button type="submit">Confirm Booking</button>
    </form>

    <div id="qrcode">
      <h2>Scan for More Info</h2>
    </div>
  </div>

  <script>
    const eventInfo = `Dandiya Nights 💃\nDev Bhoomi Uttarakhand University\nVenue: College Sports Ground\nDate: October 5, 2025\nTime: 6:00 PM onwards\nEntry: Free`;
    QRCode.toCanvas(document.createElement('canvas'), eventInfo, function (error, canvas) {
      if (error) console.error(error);
      const qrDiv = document.getElementById('qrcode');
      qrDiv.appendChild(canvas);
    });

    document.getElementById('bookingForm').addEventListener('submit', function(e) {
      e.preventDefault();
      alert("Your booking is confirmed! See you at Dandiya Nights 🎉");
    });
  </script>
</body>
</html>