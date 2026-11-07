


<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HEXED:SIAM | The Hidden World</title>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500;600;700&family=Prompt:wght@300;400;500&display=swap" rel="stylesheet">
<style>
:root {
 --gold:#dfbd7b;
 --cream:#f3e8d2;
 --bg:#080a10;
 --muted:#b8ad9c;
}
*{box-sizing:border-box}
html,body{margin:0;width:100%;min-height:100%;background:var(--bg);color:var(--cream)}
body{font-family:Prompt,sans-serif;overflow:hidden}
button{font-family:inherit;cursor:pointer}
#magic{
 position:fixed;inset:0;pointer-events:none;z-index:20;
 overflow:hidden;
}
.spark{
 position:absolute;width:3px;height:3px;border-radius:50%;
 background:#f4dca6;box-shadow:0 0 10px #f4dca6;
 animation:float linear infinite;opacity:0;
}
@keyframes float{
 0%{transform:translateY(20px) scale(.5);opacity:0}
 20%{opacity:.8}
 80%{opacity:.6}
 100%{transform:translateY(-110vh) scale(1.4);opacity:0}
}
.screen{
 display:none;position:fixed;inset:0;overflow-y:auto;
 opacity:0;transform:scale(1.025);
 transition:opacity .7s ease,transform .9s ease;
}
.screen.active{display:flex;flex-direction:column}
.screen.visible{opacity:1;transform:scale(1)}
.content{position:relative;z-index:2;width:100%;min-height:100%;padding:100px 7% 60px}
.bg{
 position:fixed;inset:0;z-index:0;pointer-events:none;
 background:
 radial-gradient(ellipse at 50% 40%,#7d5b3230,transparent 60%),
 linear-gradient(180deg,#0c111c,#080a10);
}
.bg:before{
 content:"";position:absolute;inset:0;opacity:.4;
 background:
 radial-gradient(circle at 20% 30%,#c5a15a22,transparent 25%),
 radial-gradient(circle at 80% 65%,#536c8b22,transparent 30%);
}
.bg:after{
 content:"";position:absolute;inset:0;
 background:linear-gradient(0deg,#080a10 0%,transparent 35%,#080a1080 100%);
}
.topbar{
 position:fixed;z-index:15;top:0;left:0;right:0;
 height:68px;padding:0 6%;
 display:flex;align-items:center;justify-content:space-between;
 border-bottom:1px solid #d8b87830;
 background:#080a10a8;backdrop-filter:blur(12px);
}
.brand{font-family:Cinzel,serif;letter-spacing:4px;color:var(--gold);font-size:14px}
.nav{display:flex;align-items:center;gap:20px}
.nav button{
 background:none;border:0;color:#c8bba6;font-size:10px;
 letter-spacing:1px;padding:10px 0;
}
.nav button:hover{color:var(--gold)}
.sound{
 border:1px solid #d8b87855!important;padding:8px 12px!important;
 color:var(--gold)!important;
}
h1,h2,h3{font-family:Cinzel,serif;font-weight:400}
.kicker{font-size:10px;letter-spacing:5px;color:var(--gold);text-align:center}
.heading{text-align:center;font-size:clamp(29px,5vw,50px);letter-spacing:3px;margin:16px 0}
.description{
 max-width:650px;margin:15px auto;color:var(--muted);
 font-size:13px;line-height:2.2;text-align:center;font-weight:300;
}
.btn{
 display:inline-block;padding:15px 32px;
 border:1px solid var(--gold);background:linear-gradient(110deg,#b78c4c,#eed39a);
 color:#17120b;letter-spacing:2px;font-size:11px;
 transition:.3s;
}
.btn:hover{box-shadow:0 0 35px #d8b87877;transform:translateY(-3px)}
.ghost{
 padding:14px 25px;border:1px solid #d8b87877;
 color:var(--gold);background:#090c1480;letter-spacing:2px;font-size:10px;
}
.ghost:hover{background:#d8b87820}
.center{text-align:center}
.line{width:100px;height:1px;margin:30px auto;background:linear-gradient(90deg,transparent,var(--gold),transparent)}
/* GATE */
#gate{justify-content:center;align-items:center;text-align:center}
.gate-art{
 position:absolute;inset:0;
 background:
 radial-gradient(ellipse at 50% 72%,#b18b4b45,transparent 28%),
 linear-gradient(180deg,#101725,#0b101a 55%,#080a10);
}
.gate-art:before{
 content:"";position:absolute;width:min(80vw,650px);height:min(80vw,650px);
 border:1px solid #d9b87945;border-radius:50%;
 left:50%;top:48%;transform:translate(-50%,-50%);
 box-shadow:0 0 90px #d8b87825,inset 0 0 90px #d8b87818;
 animation:seal 8s linear infinite;
}
.gate-art:after{
 content:"";position:absolute;left:50%;top:48%;
 width:min(65vw,490px);height:min(65vw,490px);
 border:1px solid #d9b87925;border-radius:50%;
 transform:translate(-50%,-50%) rotateX(65deg);
}
@keyframes seal{to{transform:translate(-50%,-50%) rotate(360deg)}}
.gate-content{position:relative;z-index:3;padding:90px 20px}
.gate-content h1{
 font-size:clamp(60px,13vw,130px);letter-spacing:10px;line-height:1;
 margin:20px 0 0;
 background:linear-gradient(#fff5d9,#d8b878 55%,#8e6537);
 -webkit-background-clip:text;color:transparent;
 text-shadow:0 0 50px #d8b87830;
}
.gate-content h2{font-size:clamp(17px,4vw,28px);letter-spacing:13px;color:#e9d5b2;margin:15px 0 30px}
.gate-content p{font-size:13px;color:#c6b8a4;line-height:2;max-width:550px;margin:0 auto 35px}
.gate-seal{font-size:48px;color:var(--gold);text-shadow:0 0 30px #d8b878}
/* LEGEND */
.legend-layout{
 max-width:950px;margin:45px auto;display:grid;
 grid-template-columns:1fr 1fr;gap:50px;align-items:center;
}
.legend-art{
 min-height:390px;display:grid;place-items:center;
 border:1px solid #d8b87855;position:relative;overflow:hidden;
 background:
 radial-gradient(ellipse at center,#bd925540,transparent 55%),
 linear-gradient(135deg,#18202c,#090c13);
}
.legend-art:before{
 content:"✧";font-size:180px;color:#d8b878;
 text-shadow:0 0 60px #d8b87880;
 animation:pulse 4s infinite;
}
@keyframes pulse{50%{transform:scale(1.1);opacity:.65}}
.legend-text h2{color:var(--gold);font-size:27px;letter-spacing:2px}
.legend-text p{font-size:13px;line-height:2.3;color:#c0b6a7;font-weight:300}
.legend-text strong{color:#ead19d;font-weight:400}
/* REALMS */
.realm-grid{
 max-width:1150px;margin:40px auto;
 display:grid;grid-template-columns:repeat(4,1fr);gap:15px;
}
.realm{
 min-height:360px;border:1px solid #ffffff28;
 position:relative;overflow:hidden;cursor:pointer;
 display:flex;flex-direction:column;justify-content:flex-end;
 padding:22px;transition:.4s;
}
.realm:hover{transform:translateY(-9px);border-color:var(--gold)}
.realm:before{content:"";position:absolute;inset:0;transition:.5s}
.realm:hover:before{filter:brightness(1.5)}
.aqua:before{background:radial-gradient(ellipse at 50% 25%,#268ca5aa,transparent 65%),linear-gradient(#102e3d,#081019)}
.ignis:before{background:radial-gradient(ellipse at 50% 25%,#cc5629aa,transparent 65%),linear-gradient(#431d16,#100c11)}
.aeris:before{background:radial-gradient(ellipse at 50% 25%,#929ac5aa,transparent 65%),linear-gradient(#252b45,#0b101c)}
.terra:before{background:radial-gradient(ellipse at 50% 25%,#70894daa,transparent 65%),linear-gradient(#273c2b,#0c130e)}
.realm-symbol{position:absolute;top:30px;left:0;right:0;text-align:center;font-size:76px;filter:drop-shadow(0 0 20px #fff5)}
.realm-info{position:relative;z-index:2}
.realm-info small{font-family:Cinzel;color:var(--gold);letter-spacing:3px}
.realm-info h3{font-size:24px;margin:10px 0}
.realm-info p{font-size:11px;line-height:1.9;color:#e1d7c7;min-height:65px}
.realm-info span{font-size:10px;color:var(--gold);letter-spacing:2px}
.realm-detail{
 display:none;max-width:750px;margin:20px auto;padding:30px;
 background:#111824;border:1px solid #d8b87877;text-align:center;
}
.realm-detail.show{display:block;animation:fade .5s}
.realm-detail h2{color:var(--gold)}
.realm-detail p{font-size:13px;line-height:2;color:#c9bdab}
@keyframes fade{from{opacity:0;transform:translateY(15px)}to{opacity:1;transform:none}}
/* ACADEMY */
.academy-seal{
 width:150px;height:150px;border:1px solid var(--gold);
 border-radius:50%;margin:30px auto;display:grid;place-items:center;
 font-family:Cinzel;font-size:65px;color:var(--gold);
 box-shadow:0 0 60px #d8b87833,inset 0 0 40px #d8b87822;
 position:relative;
}
.academy-seal:after{content:"✧";position:absolute;inset:-12px;border:1px solid #d8b87833;border-radius:50%;animation:seal 20s linear infinite}
/* QUIZ */
.quiz-box{
 max-width:720px;margin:35px auto;background:#111722e8;
 border:1px solid #d8b87866;padding:clamp(22px,5vw,45px);
}
.progress{height:2px;background:#ffffff20;margin-bottom:30px}
.progress span{display:block;height:100%;background:var(--gold);transition:.4s}
.q-no{color:var(--gold);font-size:10px;letter-spacing:4px}
.q-title{font-family:Cinzel;font-size:clamp(20px,4vw,27px);line-height:1.6;margin:20px 0 25px}
.answers{display:grid;gap:12px}
.answer{
 text-align:left;width:100%;padding:17px 18px;
 border:1px solid #ffffff30;background:#ffffff08;color:#e9dfd0;
 font-size:13px;line-height:1.6;
}
.answer:hover,.answer.selected{border-color:var(--gold);background:#d8b87820}
.quiz-actions{display:flex;justify-content:space-between;margin-top:30px}
.quiz-result{display:none;text-align:center}
.quiz-result.show{display:block;animation:fade .6s}
.quiz-result .symbol{font-size:80px}
.quiz-result h2{font-size:35px;color:var(--gold)}
.quiz-result p{font-size:13px;line-height:2;color:#c9bdab}
@media(max-width:800px){
 .realm-grid{grid-template-columns:repeat(2,1fr)}
 .legend-layout{grid-template-columns:1fr;gap:20px}
 .legend-art{min-height:220px}
 .legend-art:before{font-size:130px}
}
@media(max-width:480px){
 .topbar{height:60px;padding:0 4%}
 .brand{font-size:11px;letter-spacing:2px}
 .nav{gap:10px}
 .nav button{font-size:8px}
 .content{padding:85px 5% 45px}
 .realm{min-height:285px;padding:14px}
 .realm-symbol{font-size:55px}
 .realm-info h3{font-size:18px}
 .realm-info p{font-size:10px}
 .realm-info small{font-size:9px}
}
</style>
</head>
<body>

<div id="magic"></div>

<div class="topbar">
 <div class="brand">HEXED : SIAM</div>
 <div class="nav">
  <button onclick="go('gate')">HOME</button>
  <button onclick="go('legend')">LEGEND</button>
  <button onclick="go('realms')">REALMS</button>
  <button onclick="go('academy')">ACADEMY</button>
 </div>
</div>

<!-- SCREEN 1: GATE -->
<main class="screen active visible" id="gate">
 <div class="gate-art"></div>
 <div class="gate-content">
  <div class="gate-seal">✧</div>
  <div class="kicker">A SECRET WORLD WITHIN SIAM</div>
  <h1>HEXED</h1>
  <h2>SIAM</h2>
  <p>
   บางสิ่งที่ถูกลืม ไม่ได้หมายความว่ามันไม่เคยมีอยู่จริง<br>
   หลังม่านแห่งโลกมนุษย์ ยังมีอาณาจักรเวทมนตร์ที่รอการค้นพบ
  </p>
  <button class="btn" onclick="go('legend')">✧ ENTER THE HIDDEN WORLD ✧</button>
  <div class="line"></div>
  <div class="kicker">THE MAGIC WAS NEVER GONE</div>
 </div>
</main>

<!-- SCREEN 2: LEGEND -->
<section class="screen" id="legend">
 <div class="bg"></div>
 <div class="content">
  <div class="kicker">THE FORGOTTEN CHRONICLE</div>
  <h1 class="heading">THE LEGEND OF SIAM</h1>
  <div class="legend-layout">
   <div class="legend-art"></div>
   <div class="legend-text">
    <h2>ตำนานแห่ง HEXED:SIAM</h2>
    <p>
     ก่อนที่โลกมนุษย์จะรู้จักคำว่าเวทมนตร์
     แผ่นดินสยามเคยเป็นศูนย์กลางของพลังลี้ลับ
     ที่เชื่อมโยงมนุษย์กับสิ่งเหนือธรรมชาติ
    </p>
    <p>
     พลังโบราณได้แบ่งตัวออกเป็น <strong>สี่อาณาจักร</strong>
     แต่ละอาณาจักรมีผู้พิทักษ์และพลังที่แตกต่างกัน
     ทั้งสายน้ำ เปลวเพลิง สายลม และผืนดิน
    </p>
    <p>
     หลายศตวรรษผ่านไป ประตูระหว่างสองโลกถูกปิดผนึก
     แต่คำทำนายกล่าวว่า วันหนึ่งจะมีผู้ถูกเลือก
     ให้กลับมาเปิดประตูอีกครั้ง
    </p>
    <button class="btn" onclick="go('realms')">DISCOVER THE FOUR REALMS →</button>
   </div>
  </div>
 </div>
</section>

<!-- SCREEN 3: REALMS -->
<section class="screen" id="realms">
 <div class="bg"></div>
 <div class="content">
  <div class="kicker">FOUR POWERS · FOUR DESTINIES</div>
  <h1 class="heading">THE FOUR REALMS</h1>
  <p class="description">สี่อาณาจักรแห่งพลังโบราณ เลือกประตูที่เรียกหาคุณ เพื่อค้นพบความลับที่ซ่อนอยู่</p>

  <div class="realm-grid">
   <article class="realm aqua" onclick="openRealm('aqua')">
    <div class="realm-symbol">🐉</div>
    <div class="realm-info">
     <small>AQUA · WATER</small>
     <h3>อมรนที</h3>
     <p>ผู้สืบทอดพลังแห่งนาคา ลุ่มลึก ลึกลับ และมีสัญชาตญาณอันเฉียบคม</p>
     <span>OPEN THE GATE ↗</span>
    </div>
   </article>
   <article class="realm ignis" onclick="openRealm('ignis')">
    <div class="realm-symbol">🔥</div>
    <div class="realm-info">
     <small>IGNIS · FIRE</small>
     <h3>สุริยานคร</h3>
     <p>ผู้สืบทอดพลังแห่งครุฑ กล้าหาญ ทะเยอทะยาน และทรงพลัง</p>
     <span>OPEN THE GATE ↗</span>
    </div>
   </article>
   <article class="realm aeris" onclick="openRealm('aeris')">
    <div class="realm-symbol">🪽</div>
    <div class="realm-info">
     <small>AERIS · AIR</small>
     <h3>เวหานคร</h3>
     <p>ผู้สืบทอดพลังแห่งกินรี อิสระ อ่อนโยน และเปี่ยมจินตนาการ</p>
     <span>OPEN THE GATE ↗</span>
    </div>
   </article>
   <article class="realm terra" onclick="openRealm('terra')">
    <div class="realm-symbol">🌳</div>
    <div class="realm-info">
     <small>TERRA · EARTH</small>
     <h3>พนาลัย</h3>
     <p>ผู้สืบทอดพลังแห่งยักษ์ หนักแน่น อดทน และไม่ยอมแพ้</p>
     <span>OPEN THE GATE ↗</span>
    </div>
   </article>
  </div>

  <div class="realm-detail" id="realmDetail">
   <div class="kicker">THE GATE HAS AWAKENED</div>
   <h2 id="detailTitle"></h2>
   <p id="detailText"></p>
   <button class="btn" onclick="go('academy')">CONTINUE TO AURELIA →</button>
  </div>
  <div class="center">
   <button class="ghost" onclick="go('academy')">ENTER AURELIA ACADEMY →</button>
  </div>
 </div>
</section>

<!-- SCREEN 4: ACADEMY -->
<section class="screen" id="academy">
 <div class="bg"></div>
 <div class="content center">
  <div class="kicker">THE SCHOOL OF ANCIENT MAGIC</div>
  <div class="academy-seal">A</div>
  <h1 class="heading">AURELIA ACADEMY</h1>
  <p class="description">
   สถาบันเวทมนตร์กลางแห่ง HEXED:SIAM<br>
   สถานที่ซึ่งผู้มีพลังจากทั้งสี่อาณาจักรมารวมตัวกัน
   เพื่อเรียนรู้ศาสตร์โบราณและค้นพบพลังที่แท้จริงของตนเอง
  </p>
  <div class="line"></div>
  <p class="description" style="color:var(--gold)">
   ผู้มาเยือนทุกคนต้องผ่านพิธีคัดสรร<br>
   เพื่อค้นหาว่าพลังใดเป็นส่วนหนึ่งของโชคชะตาคุณ
  </p>
  <button class="btn" onclick="startQuiz()">BEGIN THE DESTINY CEREMONY ✧</button>
 </div>
</section>

<!-- SCREEN 5: QUIZ -->
<section class="screen" id="ceremony">
 <div class="bg"></div>
 <div class="content">
  <div class="kicker">THE MOMENT OF TRUTH</div>
  <h1 class="heading">DESTINY CEREMONY</h1>
  <p class="description">จงเลือกคำตอบที่สะท้อนตัวตนของคุณมากที่สุด</p>

  <div class="quiz-box" id="quizBox">
   <div id="quizContent">
    <div class="progress"><span id="progressBar"></span></div>
    <div class="q-no" id="qNo">QUESTION 01 / 06</div>
    <div class="q-title" id="qTitle"></div>
    <div class="answers" id="answers"></div>
    <div class="quiz-actions">
     <button class="ghost" onclick="prevQuestion()">← BACK</button>
     <button class="btn" id="nextBtn" onclick="nextQuestion()" disabled>NEXT →</button>
    </div>
   </div>
   <div class="quiz-result" id="quizResult">
    <div class="kicker">YOUR DESTINY HAS BEEN REVEALED</div>
    <div class="symbol" id="resultSymbol"></div>
    <h2 id="resultRealm"></h2>
    <h3 id="resultName"></h3>
    <p id="resultText"></p>
    <button class="btn" onclick="restartQuiz()">REPEAT THE CEREMONY</button>
    <br><br>
    <button class="ghost" onclick="go('realms')">EXPLORE THE REALMS</button>
   </div>
  </div>
 </div>
</section>

<script>
/* SCREEN TRANSITIONS */
let currentScreen='gate';
function go(id){
 const old=document.getElementById(currentScreen);
 const next=document.getElementById(id);
 if(!next)return;
 if(old===next)return;
 old.classList.remove('visible');
 setTimeout(()=>{
  old.classList.remove('active');
  next.classList.add('active');
  requestAnimationFrame(()=>next.classList.add('visible'));
  currentScreen=id;
  window.scrollTo(0,0);
 },450);
}

/* MAGIC PARTICLES */
const magic=document.getElementById('magic');
for(let i=0;i<45;i++){
 const s=document.createElement('i');
 s.className='spark';
 s.style.left=Math.random()*100+'%';
 s.style.top=(Math.random()*100+20)+'%';
 s.style.animationDuration=(7+Math.random()*13)+'s';
 s.style.animationDelay=(-Math.random()*15)+'s';
 s.style.width=(1+Math.random()*3)+'px';
 s.style.height=s.style.width;
 magic.appendChild(s);
}

/* REALMS */
const realmData={
 aqua:{
  title:'AQUA — อมรนที',
  text:'อาณาจักรแห่งสายน้ำ ผู้สืบทอดพลังแห่งนาคา ผู้มีจิตใจลึกซึ้ง เข้าใจความรู้สึกของผู้อื่น และมีความแข็งแกร่งที่ซ่อนอยู่ภายใน สายน้ำอาจอ่อนโยน แต่สามารถเปลี่ยนแปลงทุกสิ่งได้'
 },
 ignis:{
  title:'IGNIS — สุริยานคร',
  text:'อาณาจักรแห่งเปลวเพลิง ผู้สืบทอดพลังแห่งครุฑ ผู้มีความกล้าหาญ ทะเยอทะยาน และไม่กลัวการเริ่มต้นใหม่ เปลวไฟของพวกเขาเป็นสัญลักษณ์แห่งความมุ่งมั่นและการเกิดใหม่'
 },
 aeris:{
  title:'AERIS — เวหานคร',
  text:'อาณาจักรแห่งสายลม ผู้สืบทอดพลังแห่งกินรี ผู้มีจิตวิญญาณอิสระ ความคิดสร้างสรรค์ และมองโลกได้กว้างไกล พวกเขาไม่ยอมให้สิ่งใดมาจำกัดความฝัน'
 },
 terra:{
  title:'TERRA — พนาลัย',
  text:'อาณาจักรแห่งผืนดิน ผู้สืบทอดพลังแห่งยักษ์ ผู้มีความหนักแน่น อดทน และเป็นที่พึ่งของผู้อื่น พลังของพวกเขาไม่ได้อยู่ที่ความแข็งแกร่งเพียงอย่างเดียว แต่อยู่ที่หัวใจที่ไม่ยอมแพ้'
 }
};
function openRealm(id){
 const d=realmData[id];
 document.getElementById('detailTitle').textContent=d.title;
 document.getElementById('detailText').textContent=d.text;
 document.getElementById('realmDetail').classList.add('show');
 document.getElementById('realmDetail').scrollIntoView({behavior:'smooth',block:'center'});
}

/* DESTINY QUIZ */
const questions=[
 {q:'เมื่อคุณเผชิญกับสิ่งที่ไม่คาดคิด คุณจะ...',a:[
 ['ตั้งสติและใช้ความรู้สึกนำทาง','aqua'],
 ['ลุกขึ้นเผชิญหน้าโดยไม่ลังเล','ignis'],
 ['มองหาวิธีใหม่ที่ไม่มีใครคิดถึง','aeris'],
 ['ค่อย ๆ วางแผนและหาทางออก','terra']]},
 {q:'สิ่งใดสำคัญที่สุดสำหรับคุณ?',a:[
 ['ความเข้าใจและความสัมพันธ์','aqua'],
 ['ความสำเร็จและความกล้าหาญ','ignis'],
 ['อิสรภาพและการค้นพบ','aeris'],
 ['ความมั่นคงและความไว้วางใจ','terra']]},
 {q:'หากเลือกพลังวิเศษได้หนึ่งอย่าง คุณจะเลือก...',a:[
 ['ควบคุมสายน้ำและรักษาบาดแผล','aqua'],
 ['ควบคุมเปลวเพลิงและพลังแสง','ignis'],
 ['เหาะเหินและควบคุมสายลม','aeris'],
 ['ควบคุมผืนดินและสร้างเกราะป้องกัน','terra']]},
 {q:'เพื่อนมักมองคุณเป็นคนแบบไหน?',a:[
 ['เข้าใจคนอื่นและเป็นผู้ฟังที่ดี','aqua'],
 ['เด็ดเดี่ยวและกล้าตัดสินใจ','ignis'],
 ['มีไอเดียแปลกใหม่และรักอิสระ','aeris'],
 ['พึ่งพาได้และรักษาคำพูด','terra']]},
 {q:'สถานที่ใดเรียกหาคุณมากที่สุด?',a:[
 ['นครลึกลับใต้ผืนน้ำ','aqua'],
 ['นครทองคำกลางแสงอาทิตย์','ignis'],
 ['นครลอยฟ้าท่ามกลางเมฆหมอก','aeris'],
 ['นครโบราณกลางป่าศักดิ์สิทธิ์','terra']]},
 {q:'หากต้องเลือกคำหนึ่งคำแทนตัวคุณ คุณจะเลือก...',a:[
 ['ลึกซึ้ง','aqua'],
 ['เปล่งประกาย','ignis'],
 ['อิสระ','aeris'],
 ['แข็งแกร่ง','terra']]}
];
let qi=0;
let choices=Array(6).fill(null);
function startQuiz(){
 qi=0;choices=Array(6).fill(null);
 document.getElementById('quizContent').style.display='block';
 document.getElementById('quizResult').classList.remove('show');
 drawQuestion();go('ceremony');
}
function drawQuestion(){
 const q=questions[qi];
 document.getElementById('qNo').textContent=`QUESTION ${String(qi+1).padStart(2,'0')} / 06`;
 document.getElementById('qTitle').textContent=q.q;
 document.getElementById('progressBar').style.width=(qi/6*100)+'%';
 document.getElementById('nextBtn').disabled=!choices[qi];
 document.getElementById('nextBtn').textContent=qi===5?'REVEAL MY DESTINY ✧':'NEXT →';
 const wrap=document.getElementById('answers');
 wrap.innerHTML='';
 q.a.forEach(([label,id])=>{
  const b=document.createElement('button');
  b.className='answer'+(choices[qi]===id?' selected':'');
  b.textContent=label;
  b.onclick=()=>{choices[qi]=id;drawQuestion()};
  wrap.appendChild(b);
 });
}
function nextQuestion(){
 if(!choices[qi])return;
 if(qi<5){qi++;drawQuestion()}
 else{reveal()}
}
function prevQuestion(){
 if(qi>0){qi--;drawQuestion()}
}
function reveal(){
 const scores={aqua:0,ignis:0,aeris:0,terra:0};
 choices.forEach(x=>scores[x]++);
 const max=Math.max(...Object.values(scores));
 const winners=Object.keys(scores).filter(k=>scores[k]===max);
 const winner=winners[Math.floor(Math.random()*winners.length)];
 const d=realmData[winner];
 const symbols={aqua:'🐉',ignis:'🔥',aeris:'🪽',terra:'🌳'};
 document.getElementById('quizContent').style.display='none';
 document.getElementById('quizResult').classList.add('show');
 document.getElementById('resultSymbol').textContent=symbols[winner];
 document.getElementById('resultRealm').textContent=winner.toUpperCase();
 document.getElementById('resultName').textContent=d.title.split('—')[1];
 document.getElementById('resultText').textContent=d.text;
 document.getElementById('progressBar').style.width='100%';
}
function restartQuiz(){
 qi=0;choices=Array(6).fill(null);
 document.getElementById('quizResult').classList.remove('show');
 document.getElementById('quizContent').style.display='block';
 drawQuestion();
}
</script>
</body>
</html>
