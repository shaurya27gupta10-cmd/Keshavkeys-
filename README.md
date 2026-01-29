<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Keshav Chabi Workshop</title>

<style>
body{margin:0;font-family:Arial;background:#f4f6fb}
header{position:sticky;top:0;background:#6a5cff;color:#fff;padding:14px;text-align:center;font-size:20px;font-weight:bold;z-index:1000}
marquee{background:#000;color:#fff;padding:8px;font-weight:bold}
.ad img{width:100%}
.card{background:#fff;margin:15px;padding:20px;border-radius:18px;box-shadow:0 10px 25px rgba(0,0,0,.1)}
.btn{display:block;text-align:center;padding:14px;border-radius:14px;background:#6a5cff;color:#fff;text-decoration:none;margin-top:10px}
input,select,textarea{width:100%;padding:12px;margin-bottom:10px;border-radius:10px;border:1px solid #ccc}
button{padding:12px 16px;border:none;border-radius:12px;background:#6a5cff;color:#fff}
.float{position:fixed;right:15px;bottom:20px}
.float a{display:block;margin-top:10px;padding:14px;border-radius:50%;color:#fff;text-decoration:none}
.call{background:#28a745}
.wa{background:#25d366}
</style>
</head>

<body>

<header>Keshav Chabi Workshop</header>
<marquee>🚗 All Car & Bike Key Solution | Call: +91 9893216520</marquee>
<div class="ad"><img src="ad.jpg"></div>

<div class="card">
  <img src="logo.png" style="width:120px;border-radius:50%;display:block;margin:auto">
  <h2 style="text-align:center">Vehicle Key Making</h2>
  <p style="text-align:center">Pandariya, Chhattisgarh</p>
</div>

<div class="card">
  <a class="btn" href="tel:+919893216520">📞 Call</a>
  <a class="btn" href="https://wa.me/919893216520">💬 WhatsApp</a>
</div>

<div class="card">
<h3>Customer Enquiry</h3>
<form onsubmit="sendEnquiry();return false;">
<input id="name" placeholder="Name" required>
<input id="phone" placeholder="Phone" required>
<select id="vehicle">
<option>Bike</option><option>Car</option><option>Scooter</option>
</select>
<textarea id="msg" placeholder="Message"></textarea>
<button>Send</button>
</form>
</div>

<div class="float">
<a class="call" href="tel:+919893216520">📞</a>
<a class="wa" href="https://wa.me/919893216520">💬</a>
</div>

<!-- LOGIN -->
<div id="login" style="display:none;padding:40px;text-align:center">
<h2>Admin Login</h2>
<input id="lid" placeholder="ID">
<input id="lpass" type="password" placeholder="Password">
<button onclick="login()">Login</button>
</div>

<!-- ADMIN -->
<div id="admin" style="display:none;padding:20px">
<h2>📊 Business Dashboard</h2>
<div id="stats"></div>

<h3>Add Staff</h3>
<input id="sid" placeholder="Staff ID">
<input id="spass" placeholder="Password">
<button onclick="addStaff()">Add</button>

<h3>Change Admin Password</h3>
<input id="newpass" placeholder="New Password">
<button onclick="changePass()">Update</button>

<br><br>
<button onclick="downloadCSV()">⬇ Excel</button>
<button onclick="clearData()">🗑 Clear</button>

<h3>Enquiries</h3>
<div id="elist"></div>
</div>

<script>
/* INIT */
if(!localStorage.enquiries)localStorage.enquiries="[]";
if(!localStorage.creds)localStorage.creds=JSON.stringify({admin:"9893"});

/* ENQUIRY */
function sendEnquiry(){
let data=JSON.parse(localStorage.enquiries);
data.push({
name:name.value,phone:phone.value,
vehicle:vehicle.value,msg:msg.value,
time:new Date().toLocaleString()
});
localStorage.enquiries=JSON.stringify(data);
window.open(`https://wa.me/919893216520?text=Name:${name.value}`,"_blank");
alert("Sent");
}

/* LOGIN */
if(location.hash=="#admin"){
document.body.innerHTML=login.outerHTML;
}

function login(){
let c=JSON.parse(localStorage.creds);
if(c[lid.value]==lpass.value){
location.hash="#dashboard";location.reload();
}else alert("Wrong login");
}

/* ADMIN */
if(location.hash=="#dashboard"){
document.body.innerHTML=admin.outerHTML;
let data=JSON.parse(localStorage.enquiries);
stats.innerHTML=`Total: ${data.length}`;
let h="";
data.forEach(e=>{
h+=`<div class="card">${e.name} - ${e.phone}<br>${e.vehicle}<br>${e.msg}<br>${e.time}</div>`;
});
elist.innerHTML=h||"No data";
}

/* STAFF */
function addStaff(){
let c=JSON.parse(localStorage.creds);
c[sid.value]=spass.value;
localStorage.creds=JSON.stringify(c);
alert("Staff added");
}

/* CHANGE PASS */
function changePass(){
let c=JSON.parse(localStorage.creds);
c.admin=newpass.value;
localStorage.creds=JSON.stringify(c);
alert("Password changed");
}

/* CSV */
function downloadCSV(){
let d=JSON.parse(localStorage.enquiries);
let csv="Name,Phone,Vehicle,Message,Time\n";
d.forEach(e=>csv+=`${e.name},${e.phone},${e.vehicle},${e.msg},${e.time}\n`);
let a=document.createElement("a");
a.href=URL.createObjectURL(new Blob([csv]));
a.download="enquiries.csv";a.click();
}

/* CLEAR */
function clearData(){
if(confirm("Delete all?")){
localStorage.enquiries="[]";location.reload();
}
}
</script>

</body>
</html>
