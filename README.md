# Daddy-
Think of me during your day 
<!DOCTYPE html>
<html>
<head>
<title>For You ❤️</title>

<style>

body{
margin:0;
height:100vh;
background:pink;
display:flex;
justify-content:center;
align-items:center;
font-family:Arial;
overflow:hidden;
}

/* glitch light background */

body::before{
content:"";
position:absolute;
width:200%;
height:200%;
background:linear-gradient(45deg,#ff99cc,#ff66b2,#ffb3d9,#ff66cc);
animation:glitch 3s infinite;
opacity:0.4;
}

@keyframes glitch{
0%{transform:translate(0,0);}
20%{transform:translate(-10px,5px);}
40%{transform:translate(10px,-5px);}
60%{transform:translate(-5px,10px);}
80%{transform:translate(5px,-10px);}
100%{transform:translate(0,0);}
}

/* message */

.message{
position:relative;
color:white;
font-size:28px;
text-align:center;
z-index:2;
max-width:600px;
padding:20px;
}

/* button */

button{
position:relative;
z-index:2;
padding:15px 30px;
font-size:18px;
border:none;
border-radius:25px;
background:#ff4da6;
color:white;
cursor:pointer;
}

/* floating hearts */

.heart{
position:absolute;
bottom:-50px;
font-size:25px;
animation:floatUp linear infinite;
z-index:1;
}

@keyframes floatUp{
0%{
transform:translateY(0);
opacity:1;
}
100%{
transform:translateY(-120vh);
opacity:0;
}
}

</style>
</head>

<body>

<div class="message">
<button onclick="startMessage()">Tap to open your message ❤️</button>
<div id="text"></div>

<br><br>

<iframe id="spotify"
style="border-radius:12px; display:none;"
src="https://open.spotify.com/embed/track/4LbSWDu37crNaiXqey5LDP?utm_source=generator"
width="300"
height="80"
frameBorder="0"
allowfullscreen=""
allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture">
</iframe>

</div>

<script>

let message = "Think less of what happened yesterday & have a productive day instead. Know I'm daydreaming of your hot ass daddy. Hope this made you smile munchkin.";

let i = 0;

function typeWriter(){
if(i < message.length){
document.getElementById("text").innerHTML += message.charAt(i);
i++;
setTimeout(typeWriter,60);
}
}

function startMessage(){

document.querySelector("button").style.display="none";

document.getElementById("spotify").style.display="block";

typeWriter();

}

/* floating hearts */

function createHeart(){

let heart = document.createElement("div");

heart.className="heart";

heart.innerHTML="❤️";

heart.style.left=Math.random()*100+"vw";

heart.style.animationDuration=(Math.random()*3+3)+"s";

document.body.appendChild(heart);

setTimeout(()=>{
heart.remove();
},6000);

}

setInterval(createHeart,300);

</script>

</body>
</html>
