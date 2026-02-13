<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Stellar's Universe ✨</title>

<style>
body {
    margin:0;
    padding:0;
    height:100vh;
    background: radial-gradient(circle at top, #1a1a40, #000);
    overflow:hidden;
    font-family: Arial, sans-serif;
    color:white;
    display:flex;
    justify-content:center;
    align-items:center;
    transition: all 1.5s ease;
}

/* Stars */
.star {
    position:absolute;
    width:2px;
    height:2px;
    background:white;
    animation: twinkle 2s infinite alternate;
}

@keyframes twinkle {
    from {opacity:0.2;}
    to {opacity:1;}
}

/* Container */
.container {
    background: rgba(255,255,255,0.1);
    backdrop-filter: blur(10px);
    padding:40px;
    border-radius:20px;
    text-align:center;
    width:90%;
    max-width:400px;
}

input {
    padding:10px;
    border-radius:10px;
    border:none;
    width:100%;
}

button {
    margin-top:15px;
    padding:10px 20px;
    border:none;
    background:#ff66cc;
    color:white;
    border-radius:10px;
    cursor:pointer;
}

#error {color:#ff4d4d; margin-top:10px;}

.zoom-out {
    transform: scale(3);
    opacity:0;
}

/* Fade */
.fade-in {
    animation: fadeIn 2s forwards;
}
@keyframes fadeIn {
    from {opacity:0;}
    to {opacity:1;}
}

/* Hearts */
.heart {
    position:absolute;
    font-size:20px;
    animation: floatUp 5s linear infinite;
}
@keyframes floatUp {
    0% {transform: translateY(0); opacity:1;}
    100% {transform: translateY(-100vh); opacity:0;}
}

/* Shooting Star */
.shooting-star {
    position:absolute;
    width:100px;
    height:2px;
    background:linear-gradient(-45deg, white, transparent);
    animation: shoot 3s linear infinite;
}
@keyframes shoot {
    0% {transform: translateX(-100px) translateY(-100px);}
    100% {transform: translateX(100vw) translateY(100vh);}
}
</style>
</head>

<body>

<div class="container">
    <h1>🔒 Stellar's Universe ✨</h1>
    <p>Only Mchangani can unlock this galaxy 💫</p>
    <input type="password" id="password" placeholder="Enter cosmic key">
    <button onclick="unlock()">Unlock 💖</button>
    <p id="error"></p>
</div>

<script>

/* Create Stars */
for (let i=0; i<120; i++){
    let star=document.createElement("div");
    star.className="star";
    star.style.top=Math.random()*100+"vh";
    star.style.left=Math.random()*100+"vw";
    star.style.animationDuration=(Math.random()*3+2)+"s";
    document.body.appendChild(star);
}

/* Shooting Stars */
setInterval(()=>{
    let s=document.createElement("div");
    s.className="shooting-star";
    s.style.top=Math.random()*50+"vh";
    document.body.appendChild(s);
    setTimeout(()=>s.remove(),3000);
},4000);

/* Days Counter */
function daysSince(){
    const start=new Date("2025-04-09");
    const now=new Date();
    const diff=Math.floor((now-start)/(1000*60*60*24));
    return diff;
}

function unlock(){
    const correct="mchangani";
    const entered=document.getElementById("password").value.trim().toLowerCase();
    const error=document.getElementById("error");

    if(entered===correct){

        document.body.classList.add("zoom-out");

        setTimeout(()=>{
            document.body.classList.remove("zoom-out");

            document.body.innerHTML=`
            <div style="text-align:center;" class="fade-in">
                <h1>✨ Access Granted, Stellar ✨</h1>
                <p>Since Mamaila Mall...</p>
                <p>Since our Shoprite perfume crime 😭😂</p>
                <p>Since 09/04/2025...</p>
                <h2>You became my entire universe ❤️</h2>
                <h3>It's been ${daysSince()} days since our stars aligned 💫</h3>

                <audio autoplay loop>
                    <source src="birds.mp3" type="audio/mpeg">
                </audio>

                <video width="80%" controls autoplay style="margin-top:20px; border-radius:15px;">
                    <source src="stellar-message.mp4" type="video/mp4">
                </video>

                <p id="future" style="margin-top:20px; font-size:18px; opacity:0; transition:2s;">
                💍 Future Wife loading...
                </p>

                <p id="finalMessage" style="margin-top:30px; font-size:20px; opacity:0; transition:3s; font-weight:bold; line-height:1.6;">
                Stellar…<br><br>

                You loved me when I was at my lowest.<br>
                And I appreciate that more than you will ever understand.<br><br>

                May God bless you abundantly for the way you love me.<br>
                Thank you for being selfless.<br><br>

                You are such a kind and beautiful spirit, Lala ❤️✨<br><br>

                From Mamaila Mall…<br>
                From mchangani…<br>
                From 09/04/2025…<br><br>

                I choose you. Every time.<br><br>

                — Yours, always.
                </p>
            </div>
            `;

            /* Floating Hearts */
            setInterval(()=>{
                let heart=document.createElement("div");
                heart.className="heart";
                heart.innerHTML="💖";
                heart.style.left=Math.random()*100+"vw";
                document.body.appendChild(heart);
                setTimeout(()=>heart.remove(),5000);
            },500);

            /* Reveal Future */
            setTimeout(()=>{
                document.getElementById("future").style.opacity="1";
            },15000);

            /* Reveal Final Message */
            setTimeout(()=>{
                document.getElementById("finalMessage").style.opacity="1";
            },22000);

        },1500);

    } else {
        error.innerText="Hint: Our Mamaila Mall criminal name 👀✨";
    }
}
</script>

</body>
</html>
