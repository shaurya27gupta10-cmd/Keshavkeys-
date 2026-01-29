<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Keshav Chabi Workshop</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- GOOGLE ANALYTICS (optional) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-ABC123XYZ"></script>
<script>
window.dataLayer = window.dataLayer || [];
function gtag(){dataLayer.push(arguments);}
gtag('js', new Date());
gtag('config', 'G-ABC123XYZ');
</script>

<style>
body{
  margin:0;
  font-family:Arial, sans-serif;
  background:#f2f5f9;
  animation:fadeIn 1s ease;
}
@keyframes fadeIn{
  from{opacity:0;}
  to{opacity:1;}
}

.container{
  max-width:420px;
  margin:auto;
  background:#fff;
  min-height:100vh;
}

/* HEADER */
.header{
  background:#eaf2ff;
  text-align:center;
  padding:20px;
  animation:slideDown 0.8s ease;
}
@keyframes slideDown{
  from{transform:translateY(-20px);opacity:0;}
  to{transform:translateY(0);opacity:1;}
}

.logo{
  width:130px;
  height:130px;
  border-radius:50%;
  border:5px solid #000;
}
h1{margin:10px 0 5px;font-size:22px;}
.subtitle{color:#555;font-size:14px;}

.section{padding:15px;}

/* BUTTONS */
.btn{
  display:flex;
  align-items:center;
  justify-content:center;
  padding:14px;
  margin-bottom:12px;
  background:#f5f6fa;
  border-radius:12px;
  text-decoration:none;
  color:#000;
  font-size:16px;
  border:1px solid #ddd;
  transition:all 0.25s ease;
}
.btn:hover{
  transform:scale(1.03);
  background:#e9ebf5;
}
.btn:active{
  transform:scale(0.96);
}

/* ROW */
.row{display:flex;gap:10px;}
.row a{flex:1;}

/* ADDRESS */
.address{
  background:#f9fafc;
  padding:12px;
  border-radius:10px;
  font-size:14px;
}

/* STICKY BUTTONS */
.sticky{
  position:fixed;
  bottom:15px;
  left:50%;
  transform:translateX(-50%);
  display:flex;
  gap:12px;
  z-index:999;
}
.sticky a{
  padding:14px 18px;
  border-radius:30px;
  color:#fff;
  text-decoration:none;
  font-size:16px;
  animation:bounce 2s infinite;
}
.call{background:#007bff;}
.whatsapp{background:#25D366;}

@keyframes bounce{
  0%,100%{transform:translateY(0);}
  50%{transform:translateY(-4px);}
}

.footer{
  text-align:center;
  font-size:13px;
  color:#777;
  padding:80px 15px 15px;
}
</style>
</head>

<body>

<div class="container">

<!-- HEADER -->
<div class="header">
  <img src="logo.png" class="logo">
  <h1>Keshav Chabi Workshop</h1>
  <div class="subtitle">Vehicle Key Making Shop</div>
</div>

<!-- MAIN BUTTONS -->
<div class="section row">
  <a class="btn" href="tel:+919893216520"
     onclick="gtag('event','call_click',{event_category:'contact'});">
     📞 Call
  </a>
  <a class="btn" href="https://wa.me/919893216520"
     onclick="gtag('event','whatsapp_click',{event_category:'contact'});">
     💬 WhatsApp
  </a>
</div>

<div class="section">
  <a class="btn" href="https://www.instagram.com/">📸 Instagram</a>
  <a class="btn" href="https://www.youtube.com/">▶️ YouTube</a>
  <a class="btn" href="https://maps.app.goo.gl/">⭐ Google Review</a>
  <a class="btn" href="https://www.facebook.com/">📘 Facebook</a>
</div>

<div class="section">
  <div class="address">
    📍 Pandariya – 491559<br>
    Chhattisgarh, India
  </div>
</div>

<div class="footer">
  © 2026 Keshav Chabi Workshop
</div>

</div>

<!-- STICKY CALL / WHATSAPP -->
<div class="sticky">
  <a href="tel:+919893216520" class="call">📞 Call</a>
  <a href="https://wa.me/919893216520" class="whatsapp">💬 WhatsApp</a>
</div>

</body>
</html>
