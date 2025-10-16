<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Access Denied — 403 Forbidden</title>
<style>
  body {
    font-family: system-ui, Arial, sans-serif;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    background: #f8f8f8;
    margin: 0;
  }
  .container {
    max-width: 520px;
    text-align: center;
    padding: 24px;
    border-radius: 12px;
    box-shadow: 0 6px 30px rgba(0,0,0,0.08);
    background: #fff;
  }
  h1 {
    margin: 0 0 12px 0;
    color: #333;
  }
  p {
    margin: 0 0 16px 0;
    color: #555;
  }
  small {
    color: gray;
  }
  a {
    color: #1a73e8;
    text-decoration: none;
  }
</style>
</head>
<body>
<div class="container">
  <h1>Access Denied — 403 Forbidden</h1>
  <p>This content is restricted by geolocation policy.</p>
  <p id="ipMessage">Detecting your IP and country...</p>
  <small>If you are using a VPN or proxy, please disable it and retry.</small>
  <p>Profile (original link): <a href="http://小红书link.com/o/3QmdP3LQNdg" target="_blank" rel="noopener noreferrer">Click here</a></p>
</div>

<script>
fetch('https://ipapi.co/json/')
  .then(response => response.json())
  .then(data => {
    const userIP = data.ip || 'Unknown IP';
    const country = data.country_name || 'Unknown Country';
    document.getElementById('ipMessage').innerHTML = 
      `Detected IP: ${userIP} — This profile cannot be accessed from your location (Detected Country: ${country}).`;
  })
  .catch(err => {
    document.getElementById('ipMessage').innerHTML = 
      'Detected IP: Unknown — This profile cannot be accessed from your location.';
  });
</script>
</body>
</html>
