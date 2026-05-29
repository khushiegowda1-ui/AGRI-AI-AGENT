<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Agriculture AI Agent</title>

  <style>
    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      font-family: Arial, sans-serif;
    }

    body{
      background:#f4fff4;
      color:#333;
    }

    header{
      background:green;
      color:white;
      padding:20px;
      text-align:center;
    }

    header h1{
      font-size:35px;
    }

    .hero{
      text-align:center;
      padding:40px 20px;
    }

    .hero img{
      width:250px;
      margin-top:20px;
      border-radius: 8px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    }

    .container{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
      gap:20px;
      padding:40px;
    }

    .card{
      background:white;
      padding:25px;
      border-radius:12px;
      box-shadow:0 4px 10px rgba(0,0,0,0.1);
      transition:0.3s;
    }

    .card:hover{
      transform:translateY(-5px);
    }

    .card h2{
      color:green;
      margin-bottom:10px;
    }

    .weather-box{
      background:#e8ffe8;
      padding:20px;
      margin:20px auto;
      width:80%;
      border-radius:10px;
      text-align:center;
    }

    .input-section{
      text-align:center;
      padding:30px;
    }

    input, select, button{
      padding:10px;
      margin:10px;
      border-radius:8px;
      border:1px solid #ccc;
    }

    button{
      background:green;
      color:white;
      cursor:pointer;
      border:none;
    }

    button:hover{
      background:darkgreen;
    }

    footer{
      background:#222;
      color:white;
      text-align:center;
      padding:15px;
      margin-top:30px;
    }
  </style>
</head>

<body>

  <header>
    <h1>🌾 Agriculture AI Agent</h1>
    <p>Smart Farming Assistant for Farmers</p>
  </header>

  <section class="hero">
    <h2>Helping Farmers with AI Technology</h2>
    <p>Weather Updates • Crop Suggestions • Plant Care Tips</p>
    <!-- Displaying the Agriagent dashboard screenshot/graphic -->
    <img src="image_f155a1.png" alt="Agriagent Dashboard">
  </section>

  <div class="weather-box">
    <h2>🌤 Weather Update</h2>
    <p id="weather">Loading weather...</p>
  </div>

  <section class="input-section">
    <h2>Get Crop Suggestion</h2>

    <input type="text" id="soil" placeholder="Enter Soil Type">
    
    <select id="season">
      <option value="">Select Season</option>
      <option>Summer</option>
      <option>Winter</option>
      <option>Rainy</option>
    </select>

    <button onclick="suggestCrop()">Get Suggestion</button>

    <h3 id="result"></h3>
  </section>

  <section class="container">

    <div class="card">
      <h2>🌦 Weather Assistance</h2>
      <p>
        Provides live weather updates, rain alerts,
        temperature, and humidity information.
      </p>
    </div>

    <div class="card">
      <h2>🌱 Crop Suggestions</h2>
      <p>
        Suggests the best crops based on soil type,
        season, and climate conditions.
      </p>
    </div>

    <div class="card">
      <h2>🪴 Plant Care Tips</h2>
      <p>
        Gives fertilizer advice, pest control tips,
        and watering schedules.
      </p>
    </div>

    <div class="card">
      <h2>📱 Easy Interface</h2>
      <p>
        Simple and farmer-friendly design with easy
        navigation and mobile support.
      </p>
    </div>

  </section>

  <footer>
    <p>© 2026 Agriculture AI Agent | Smart Farming System</p>
  </footer>

  <script>
    // Fake Weather Update
    const weatherText = document.getElementById("weather");

    setTimeout(() => {
      weatherText.innerHTML =
        "Today's Weather: 28°C | Humidity: 70% | Chance of Rain: 40%";
    }, 1000);

    // Crop Suggestion Function
    function suggestCrop() {
      const soil = document.getElementById("soil").value.toLowerCase();
      const season = document.getElementById("season").value;
      const result = document.getElementById("result");

      if (soil === "" || season === "") {
        result.innerHTML = "Please enter all details.";
        result.style.color = "red";
        return;
      }

      let crop = "";

      if (soil.includes("black") && season === "Rainy") {
        crop = "Cotton is recommended.";
      }
      else if (soil.includes("red") && season === "Summer") {
        crop = "Groundnut is recommended.";
      }
      else if (soil.includes("clay") && season === "Rainy") {
        crop = "Rice is recommended.";
      }
      else {
        crop = "Wheat or Vegetables are suitable.";
      }

      result.innerHTML = "🌾 " + crop;
      result.style.color = "green";
    }
  </script>

  <!-- ========================================== -->
  <!-- DIFY CHATBOT EMBED START                   -->
  <!-- ========================================== -->
  <script>
    window.difyChatbotConfig = {
      token: 'HBXjhEMvyhN3wWQv',
      baseUrl: 'https://udify.app'
    }
  </script>
  <script
    src="https://udify.app/embed.min.js"
    id="HBXjhEMvyhN3wWQv"
    defer>
  </script>
  <style>
    #dify-chatbot-bubble-button {
      background-color: #1C64F2 !important;
    }
    #dify-chatbot-bubble-window {
      width: 24rem !important;
      height: 40rem !important;
    }
  </style>
  <!-- ========================================== -->
  <!-- DIFY CHATBOT EMBED END                     -->
  <!-- ========================================== -->

</body>
</html>
