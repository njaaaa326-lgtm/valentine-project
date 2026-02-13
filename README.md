<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Be My Valentine ❤️</title>
<style>
body{
    margin:0;
    background:linear-gradient(135deg,#ffeef2,#ffd6e0);
    font-family:sans-serif;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    overflow:hidden;
}
.container{
    background:white;
    padding:50px;
    border-radius:25px;
    text-align:center;
    box-shadow:0 15px 40px rgba(255,77,109,.3);
    position:relative;
    z-index:2;
}
h1{color:#ff4d6d;}
p{color:#555;}
button{
    padding:15px 30px;
    border:none;
    border-radius:50px;
    font-size:18px;
    cursor:pointer;
    transition:.3s;
}
#yes{
    background:#ff4d6d;
    color:white;
}
#no{
    background:#ddd;
    position:absolute;
}
.heart{
    position:fixed;
    color:#ff4d6d;
    animation:fall linear infinite;
}
@keyframes fall{
    to{transform:translateY(110vh);}
}
</style>
</head>
<body>

<div class="container">
    <h1>ถึง... คนพิเศษของฉัน 💖</h1>
    <p>สุขสันต์วันวาเลนไทน์นะ ✨<br>อยู่ด้วยกันไปนาน ๆ เลยนะ ❤️</p>
    <div style="margin-top:30px;">
        <button id="yes">ตกลง 💕</button>
        <button id="no">ไม่เอา 😜</button>
    </div>
</div>

<script>
const yes = document.getElementById('yes');
const no = document.getElementById('no');

no.addEventListener('mouseover',()=>{
    const x=Math.random()*(window.innerWidth-no.offsetWidth);
    const y=Math.random()*(window.innerHeight-no.offsetHeight);
    no.style.left=x+'px';
    no.style.top=y+'px';
});

yes.addEventListener('click',()=>{
    document.querySelector('.container').innerHTML=
    "<h1>เย้! 💖</h1><p>เป็นแฟนกันแล้วนะ 🥰</p>";
});

function heart(){
    const h=document.createElement('div');
    h.className='heart';
    h.innerHTML='❤️';
    h.style.left=Math.random()*100+'vw';
    h.style.animationDuration=(Math.random()*3+2)+'s';
    document.body.appendChild(h);
    setTimeout(()=>h.remove(),5000);
}
setInterval(heart,300);
</script>

</body>
</html>
