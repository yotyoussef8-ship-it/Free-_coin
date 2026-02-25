<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>متجر شحن احترافي - تعليمي</title>

<style>
body{
    margin:0;
    font-family: 'Segoe UI', sans-serif;
    background: radial-gradient(circle at top,#0f2027,#203a43,#000);
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    color:white;
}

.container{
    width:360px;
    background:rgba(0,0,0,0.85);
    border-radius:20px;
    padding:25px;
    text-align:center;
    box-shadow:0 0 30px #00ffcc33;
    position:relative;
    overflow:hidden;
}

h2{
    margin-bottom:15px;
    color:#00ffcc;
}

.balance{
    background:#111;
    padding:10px;
    border-radius:10px;
    margin-bottom:15px;
    font-size:14px;
}

.cards{
    display:flex;
    justify-content:space-between;
    margin-bottom:15px;
}

.card{
    width:30%;
    background:#111;
    padding:10px;
    border-radius:10px;
    cursor:pointer;
    transition:0.3s;
    border:1px solid transparent;
}

.card:hover{
    transform:scale(1.05);
    border:1px solid #00ffcc;
    box-shadow:0 0 10px #00ffcc;
}

.card.active{
    border:1px solid #00ffcc;
    box-shadow:0 0 15px #00ffcc;
}

button{
    width:100%;
    padding:12px;
    border:none;
    border-radius:10px;
    background:#00ffcc;
    color:black;
    font-weight:bold;
    cursor:pointer;
    transition:0.3s;
}

button:hover{
    background:#00ccaa;
}

.success{
    display:none;
    animation:fade 0.6s ease-in-out;
}

.notice{
    font-size:11px;
    margin-top:10px;
    color:#aaa;
}

img.logo{
    width:80px;
    margin-bottom:10px;
    border-radius:50%;
    border:2px solid #00ffcc;
}

@keyframes fade{
    from{opacity:0; transform:scale(0.9);}
    to{opacity:1; transform:scale(1);}
}
</style>
</head>

<body>

<div class="container" id="mainBox">

<!-- صورة مدمجة بصيغة Base64 -->
<img class="logo" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEAAAABACAYAAACqaXHeAAABUUlEQVR4nO3aQQrCMBAF0BbgU6dOABpOg9iF3nYfO5zJCWnP0sRmmLh9V75e33XbC1r3V7sjwDQKYKKM1YCqBB6ACBQKoEKgAIFQqgQqAAgVCqBCoACCkKALxRfxRDX5xX5M1lD6gk8hkcI98ocQWZlFllnYZ8ZnSxRWhZn+g5vGrt0Y2Dfn2ZxVf7Xe31gMfchj+n8gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPchj+p4gz9xib1gMPcP7b/+BaCQq7LkAtGZAAAAAElFTkSuQmCC">

<h2>⚽ متجر الشحن التعليمي</h2>

<div class="balance">
رصيدك الحالي: <span id="coins">0</span> عملة
</div>

<div class="cards">
    <div class="card" onclick="selectPackage(this,100)">100</div>
    <div class="card" onclick="selectPackage(this,500)">500</div>
    <div class="card" onclick="selectPackage(this,1000)">1000</div>
</div>

<button onclick="buy()">شراء الآن</button>

<div class="notice">
⚠️ صفحة تدريبية فقط – لا يتم حفظ أي بيانات.
</div>

</div>

<div class="container success" id="successBox">
<h2>✅ تمت العملية</h2>
<p>تمت إضافة العملات بنجاح (محاكاة)</p>
<button onclick="restart()">رجوع للمتجر</button>
</div>

<script>
let selected = 0;

function selectPackage(element, value){
    document.querySelectorAll(".card").forEach(c=>c.classList.remove("active"));
    element.classList.add("active");
    selected = value;
}

function buy(){
    if(selected === 0){
        alert("اختر باقة أولاً");
        return;
    }

    let coins = document.getElementById("coins");
    let current = parseInt(coins.innerText);
    coins.innerText = current + selected;

    document.getElementById("mainBox").style.display="none";
    document.getElementById("successBox").style.display="block";
}

function restart(){
    document.getElementById("mainBox").style.display="block";
    document.getElementById("successBox").style.display="none";
}
</script>

</body>
</html>
