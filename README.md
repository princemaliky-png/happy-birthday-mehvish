# happy-birthday-mehvish
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday Mehvish 💖</title>

<style>
body{
    margin:0;
    height:100vh;
    overflow:hidden;
    font-family:'Segoe UI', sans-serif;
    color:white;
    background:linear-gradient(120deg,#ff5fa2,#ff9acb,#ffc1dd);
    background-size:400% 400%;
    animation:pinkGlow 8s ease infinite;
}

@keyframes pinkGlow{
    0%{background-position:0% 50%;}
    50%{background-position:100% 50%;}
    100%{background-position:0% 50%;}
}

/* Sparkles */
.sparkle{
    position:absolute;
    width:6px;
    height:6px;
    background:white;
    border-radius:50%;
    opacity:0.7;
    animation:spark 6s linear infinite;
}
@keyframes spark{
    from{transform:translateY(100vh) scale(0);}
    to{transform:translateY(-10vh) scale(1);}
}

/* Content */
.container{
    position:absolute;
    top:12%;
    left:50%;
    transform:translateX(-50%);
    width:90%;
    max-width:900px;
    text-align:center;
}

/* Headings */
.small-title{
    font-size:46px;
    font-weight:700;
    text-shadow:0 0 15px rgba(255,255,255,0.6);
}
.big-title{
    font-size:64px;
    font-weight:800;
    margin-top:10px;
    text-shadow:0 0 20px rgba(255,255,255,0.8);
}

/* Divider */
.line{
    width:75%;
    height:4px;
    margin:30px auto;
    background:linear-gradient(90deg,transparent,white,transparent);
    border-radius:10px;
}

/* Typing text */
#text{
    font-size:30px;
    line-height:2;
    white-space:pre-line;
    text-shadow:0 0 10px rgba(255,255,255,0.4);
}

.tap{
    margin-top:30px;
    font-size:20px;
    opacity:0.9;
}

/* watermark */
.watermark{
    position:fixed;
    bottom:10px;
    right:15px;
    opacity:0.5;
    font-size:14px;
}
</style>
</head>

<body onclick="playSong()">

<!-- Sparkles -->
<script>
for(let i=0;i<40;i++){
    let s=document.createElement("div");
    s.className="sparkle";
    s.style.left=Math.random()*100+"%";
    s.style.animationDuration=(4+Math.random()*4)+"s";
    document.body.appendChild(s);
}
</script>

<div class="container">
    <div class="small-title">✨ Happy Birthday ✨</div>
    <div class="big-title">Happy Birthday Mehvish 💕</div>

    <div class="line"></div>

    <div id="text"></div>
    <div class="tap">👉 Screen tap karo (song start hoga 🎵)</div>
</div>

<div class="watermark">— Alex</div>

<audio id="song" loop>
    <source src="https://cdn.pixabay.com/audio/2023/03/29/audio_9e9b8d5bda.mp3">
</audio>

<script>
const message = `Aaj ka din sirf ek birthday nahi,
balki tumhari khoobsurat zindagi ka celebration hai.

Tumhari smile me ek alag hi magic hai,
jo bina kuch kahe dil ko sukoon de jata hai.
Tum jahan hoti ho, wahan positivity khud aa jati hai.

Dua hai ki tumhari zindagi hamesha
isi pink roshni ki tarah chamakti rahe,
har sapna poora ho,
aur har din ek nayi wajah de khush rehne ki.

Tum special ho, tum important ho,
aur tumhari jagah koi aur nahi le sakta.

💖 Happy Birthday chudail bhutni 😄 💖`;

let i=0;
function typeText(){
    if(i<message.length){
        document.getElementById("text").innerHTML+=message.charAt(i);
        i++;
        setTimeout(typeText,30);
    }
}
typeText();

let started=false;
function playSong(){
    if(!started){
        document.getElementById("song").play();
        started=true;
    }
}
</script>

</body>
</html>
