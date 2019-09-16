# Login-Hotspot-Dengan-QR-Scan-Barcode

Syarat:<br>
1.Pemahaman Web terutama JavaScript, HTML dan CSS sangat di perlukan.<br>
2.Karena script saya share nanti menggunakan HTML5 Video berarti mau tidak mau kita harus mengaktifkan secure sertifikat SSL/TLS di mikrotik karena memang wajib menggunakan https agar script bisa bekerja. (saya tidak menjawab pertanyaan kenapa muncul peringatan 'SSL Redirect Warning' karena kalo gak mau muncul ya beli SSL Certificate dengan Trusted Certificate Authority.<br>
3.iKuti tutorial ini sampe sukses http://www.mikrotik.co.id/artikel_lihat.php?id=272<br>
4.Silahkan download scriptnya script QR Scan disini https://drive.google.com/file/d/1pKvOEB1FWBStAteF6cy42MhOq_FO8kKD/view<br>

<img border="0" src="https://3.bp.blogspot.com/-Mt7pTJj938E/W3oOs2OsAPI/AAAAAAAAO-I/PUWSbilXkMcfPKKlOzsm3eF9RE7T-Qv3ACLcBGAs/s1600/Untitled2.png"/>

OK langsung ke tutorial.

Pertama silahkan copy - paste file javascript llqrcode.js dan myqr.js dan letakan ke dua file ini dalam folder hotspot

Kemudian buka login.html dan letakan Javascript dibawah ini tepat diatas kode </head>
<script type="text/javascript" src="llqrcode.js"></script>
<script type="text/javascript" src="myqr.js"></script>

Masih pada login.html dan letakan CSS dibawah ini tepat dibawah kode <style type="text/css">
.modal {
display: none; 
position: fixed; 
z-index: 1;
padding-top: 30px;
left: 0;
top: 0;
width: 100%; 
height: 100%; 
overflow: auto; 
background-color: rgb(0,0,0); 
background-color: rgba(0,0,0,0.4); 
}
.modal-content {
background-color: #000;
margin: auto;
padding: 10px;
border: 2px solid #111;
width: 260px;
-moz-border-radius:3px; 
-khtml-border-radius:5px; 
-webkit-border-radius:5px ; 
border-radius:5px ;
color:red;
font-weight:bold
}
.close {float: right;
font-size: 15px;
font-weight: bold;}
.close:hover,.close:focus {
text-decoration: none;
cursor: pointer;
}
#mainbody{
width:100%;
display:none;
}
.selector{
display:none;
visibility: hidden;
}
#result{
display:none;
visibility: hidden;
}
#v{
width:240px;
height:200px;
}
#qr-canvas{
display:none;
}
#outdiv{
padding:0;
width:240px;
height:200px;
border: solid;
border-width: 3px 3px 3px 3px;
-moz-border-radius:3px; 
-khtml-border-radius:5px; 
-webkit-border-radius:5px ; 
border-radius:5px ;
color:#555;
background: #000;
}
.tsel{
padding:0;
}
blink {
-webkit-animation: 2s linear infinite condemned_blink_effect; // for android
animation: 2s linear infinite condemned_blink_effect;
}
@-webkit-keyframes condemned_blink_effect { // for android
0% {
visibility: hidden;
}
50% {
visibility: hidden;
}
100% {
visibility: visible;
}
}
@keyframes condemned_blink_effect {
0% {
visibility: hidden;
}
50% {
visibility: hidden;
}
100% {
visibility: visible;
}
}

Masih login.html dan letakan script dibawah ini tepat dibawah kode </body>
<div id="myModal" class="modal">
<div class="modal-content">
<center><span class="scanning">▒▒▒▒▒<blink> ▓ scanning ▓ </blink>▒▒▒▒▒</span></center>
<div id="mainbody">
<div class="selector" id="webcamimg" onclick="setwebcam()" align="left" ></div>
<table class="tsel" border="0" width="100%">
<td valign="top" align="center" width="50%">
<table class="tsel" border="0">
<td colspan="1" align="center">
<div id="outdiv"></div>
</td>
</table>
</td>
<div id="result"></div>
</table>
<span class="close"></span>
<center><span style="font-weight:bold;font-size:12px; color:#999;">Scan QR code yang ada pada voucher anda</span></center>
</div>
<canvas id="qr-canvas" width="100%" height="100%"></canvas>
</div>
</div>
<script type="text/javascript">
var modal = document.getElementById('myModal');
var btn = document.getElementById("myBtn");
var span = document.getElementsByClassName("close")[0];
btn.onclick = function() {
modal.style.display = "block";
}
span.onclick = function() {
modal.style.display = "none";
}
window.onclick = function(event) {
if (event.target == modal) {
modal.style.display = "none";
}
}
</script>
<script type="text/javascript">load();</script>

yang terakhir letakan kode button ini dan sesuikan dengan template masing-masing
<button style="margin-right:10px; width: 120px;height: 35px;background: #888;border: 2px solid #999;cursor: pointer;border-radius: 2px; color: #fff;font-family: 'Open Sans', sans-serif;font-size: 16px;font-weight: bold;padding: 6px;margin-top: 10px;" id="myBtn">QR SCAN</button>

Jangan lupa juga mengganti semua QR code script yang awalnya contoh: http://namahotspot.net dan ganti dengan https://namahotspot.net semoga sukses :)
