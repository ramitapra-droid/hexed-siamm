

<!DOCTYPE html>

<html lang="th">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>HEXED: SIAM — The Hidden Kingdom</title>

<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500;600;700&family=Prompt:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>

:root{

  --gold:#d8b878;

  --cream:#f4e8cf;

  --dark:#080b12;

  --muted:#a99d8b;

}

*{box-sizing:border-box}

html{scroll-behavior:smooth}

body{

  margin:0;background:var(--dark);color:var(--cream);

  font-family:'Prompt',sans-serif;overflow-x:hidden;

}

button{font:inherit;cursor:pointer}

#stars{

  position:fixed;inset:0;pointer-events:none;z-index:0;

  background-image:

  radial-gradient(1px 1px at 20% 30%,#fff9 99%,transparent),

  radial-gradient(2px 2px at 70% 60%,#d8b87899 99%,transparent),

  radial-gradient(1px 1px at 40% 80%,#fff8 99%,transparent);

  background-size:190px 190px,270px 270px,130px 130px;

  animation:drift 35s linear infinite;

}

@keyframes drift{to{transform:translateY(-190px)}}

.noise{

  position:fixed;inset:0;pointer-events:none;z-index:1;opacity:.12;

  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.8' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.3'/%3E%3C/svg%3E");

}

nav{

  position:absolute;z-index:5;top:0;left:0;width:100%;

  display:flex;justify-content:space-between;align-items:center;

  padding:25px 7%;border-bottom:1px solid #d8b87830;

}

.logo{font-family:'Cinzel';letter-spacing:5px;color:var(--gold);font-size:15px}

.nav-links{display:flex;gap:28px}

.nav-links a{color:#c9bda9;text-decoration:none;font-size:12px;letter-spacing:1px}

.nav-links a:hover{color:var(--gold)}

.hero{

  min-height:100svh;position:relative;display:flex;align-items:center;

  justify-content:center;text-align:center;overflow:hidden;

  background:

  radial-gradient(ellipse at 50% 70%,#57402c66,transparent 50%),

  linear-gradient(180deg,#080b12 0%,#121723 55%,#090b10 100%);

  padding:120px 20px 90px;

}

.hero:before{

  content:"";position:absolute;width: min(90vw,650px);height:min(90vw,650px);

  border:1px solid #d8b87830;border-radius:50%;

  box-shadow:0 0 80px #c49b5030,inset 0 0 80px #c49b5010;

  animation:glow 5s ease-in-out infinite alternate;

}

.hero:after{

  content:"";position:absolute;bottom:-10%;width:120%;height:42%;

  background:linear-gradient(transparent,#080b12 85%),

  repeating-linear-gradient(90deg,transparent 0 50px,#d8b87809 51px 52px);

  transform:perspective(250px) rotateX(30deg);

}

@keyframes glow{to{box-shadow:0 0 130px #c49b5060,inset 0 0 100px #c49b5020}}

.hero-content{position:relative;z-index:2;max-width:850px}

.eyebrow{color:var(--gold);letter-spacing:5px;font-size:11px;margin-bottom:25px}

.hero h1{

  font-family:'Cinzel',serif;font-size:clamp(54px,11vw,112px);

  letter-spacing:8px;line-height:1;margin:0;

  background:linear-gradient(180deg,#fff5d9,#d8b878 55%,#927044);

  -webkit-background-clip:text;color:transparent;

  text-shadow:0 10px 50px #d8b87820;

}

.hero h2{font-family:'Cinzel';font-size:clamp(15px,3vw,24px);letter-spacing:8px;color:#e5d5b7;font-weight:400;margin:22px 0}

.hero p{max-width:560px;margin:30px auto;color:#bcb3a5;line-height:2;font-weight:300;font-size:14px}

.gold-btn{

  border:1px solid var(--gold);background:linear-gradient(120deg,#b58d4b,#e4c98c);

  color:#17120b;padding:15px 35px;letter-spacing:2px;font-size:12px;

  transition:.3s;box-shadow:0 0 30px #d8b87820;

}

.gold-btn:hover{transform:translateY(-4px);box-shadow:0 0 35px #d8b87870}

.outline-btn{

  background:transparent;color:var(--gold);border:1px solid #d8b87888;

  padding:14px 30px;letter-spacing:2px;font-size:11px;

}

.outline-btn:hover{background:#d8b87818}

.scroll{position:absolute;bottom:30px;z-index:3;color:#8f816d;font-size:10px;letter-spacing:4px}

section{position:relative;z-index:2;padding:110px 7%}

.section-head{text-align:center;margin-bottom:55px}

.kicker{color:var(--gold);font-size:10px;letter-spacing:5px}

.section-head h2{font-family:'Cinzel';font-size:clamp(28px,5vw,45px);font-weight:400;margin:14px 0}

.section-head p{color:var(--muted);font-size:13px;line-height:2}

.story{

  background:linear-gradient(180deg,#090c13,#111622 50%,#090c13);

  text-align:center;

}

.story-inner{max-width:750px;margin:auto}

.story-mark{font-size:50px;color:var(--gold);margin-bottom:15px}

.story h3{font-family:'Cinzel';font-size:25px;font-weight:400;color:var(--gold);letter-spacing:3px}

.story p{font-size:14px;line-height:2.3;color:#b8ad9c;font-weight:300}

.story strong{color:#e4c98c;font-weight:500}

.divider{

  width:100px;height:1px;background:linear-gradient(90deg,transparent,var(--gold),transparent);

  margin:35px auto;

}

.realms{background:#080b12}

.realm-grid{

  display:grid;grid-template-columns:repeat(4,1fr);gap:15px;

  max-width:1200px;margin:auto;

}

.realm{

  min-height:390px;position:relative;overflow:hidden;

  border:1px solid #ffffff20;padding:28px 20px;

  display:flex;flex-direction:column;justify-content:flex-end;

  transition:.45s;cursor:pointer;

}

.realm:hover{transform:translateY(-10px);border-color:var(--gold);box-shadow:0 15px 55px #0009}

.realm:before{

  content:"";position:absolute;inset:0;opacity:.8;transition:.4s;

}

.realm:hover:before{opacity:1}

.realm.aqua:before{background:radial-gradient(ellipse at 50% 25%,#218c9a99,transparent 65%),linear-gradient(180deg,#0a2936,#08121c)}

.realm.ignis:before{background:radial-gradient(ellipse at 50% 25%,#c45b2399,transparent 65%),linear-gradient(180deg,#3b1a16,#130c10)}

.realm.aeris:before{background:radial-gradient(ellipse at 50% 25%,#8b91b899,transparent 65%),linear-gradient(180deg,#252d47,#10121e)}

.realm.terra:before{background:radial-gradient(ellipse at 50% 25%,#68824d99,transparent 65%),linear-gradient(180deg,#243623,#0c130e)}

.realm-symbol{position:absolute;top:35px;left:0;right:0;text-align:center;font-size:75px;filter:drop-shadow(0 0 20px #fff4)}

.realm-info{position:relative;z-index:1}

.realm-code{font-family:'Cinzel';letter-spacing:4px;font-size:12px;color:#e8cf9e}

.realm h3{font-family:'Cinzel';font-size:24px;margin:10px 0}

.realm p{color:#d1c9bc;font-size:12px;line-height:1.9;min-height:70px}

.realm small{color:#d8b878;letter-spacing:2px;font-size:10px}

.realm-detail{

  display:none;max-width:800px;margin:30px auto 0;padding:30px;

  border:1px solid #d8b87855;background:#111722;text-align:center;

}

.realm-detail.show{display:block;animation:appear .4s}

.realm-detail h3{font-family:'Cinzel';color:var(--gold);font-size:25px}

.realm-detail p{color:#c6bba9;line-height:2;font-size:13px}

@keyframes appear{from{opacity:0;transform:translateY(15px)}to{opacity:1;transform:none}}

.academy{

  text-align:center;background:

  radial-gradient(ellipse at 50% 0%,#69502b35,transparent 60%),#10131c;

}

.academy-seal{

  width:125px;height:125px;border:1px solid var(--gold);border-radius:50%;

  margin:0 auto 30px;display:grid;place-items:center;

  font-family:'Cinzel';font-size:45px;color:var(--gold);

  box-shadow:0 0 45px #d8b87822,inset 0 0 30px #d8b87815;

}

.academy h2{font-family:'Cinzel';font-size:clamp(25px,5vw,42px);font-weight:400;letter-spacing:4px}

.academy p{color:#bdb2a1;max-width:600px;margin:20px auto 30px;line-height:2;font-size:13px}

.quiz{background:linear-gradient(180deg,#090c13,#171720,#090c13)}

.quiz-box{

  max-width:760px;margin:auto;border:1px solid #d8b87855;

  padding:clamp(25px,6vw,55px);background:#11151edb;

  box-shadow:0 20px 90px #0008;

}

.progress{height:2px;background:#ffffff20;margin-bottom:35px}

.progress span{display:block;height:100%;width:0;background:var(--gold);transition:.3s}

.question-no{color:var(--gold);font-size:10px;letter-spacing:4px}

.question{font-family:'Cinzel';font-size:clamp(20px,4vw,28px);font-weight:400;line-height:1.5;margin:20px 0 30px}

.answers{display:grid;gap:12px}

.answer{

  width:100%;text-align:left;background:#ffffff08;border:1px solid #ffffff25;

  color:#e8dfd1;padding:17px 20px;font-size:13px;line-height:1.6;transition:.2s;

}

.answer:hover{border-color:var(--gold);background:#d8b87813}

.answer.selected{border-color:var(--gold);background:#d8b87822;color:#fff0c8}

.quiz-actions{display:flex;justify-content:space-between;align-items:center;margin-top:30px}

.result{display:none;text-align:center}

.result.show{display:block;animation:appear .7s}

.result .symbol{font-size:75px}

.result h3{font-family:'Cinzel';font-size:32px;color:var(--gold);letter-spacing:3px}

.result h4{font-size:20px;font-weight:400}

.result p{font-size:13px;line-height:2;color:#c5b9a8}

footer{

  position:relative;z-index:2;text-align:center;padding:45px 20px;

  border-top:1px solid #d8b87825;background:#080b12;

}

footer strong{font-family:'Cinzel';letter-spacing:5px;color:var(--gold)}

footer p{color:#776f64;font-size:10px;letter-spacing:2px}

@media(max-width:850px){

  .realm-grid{grid-template-columns:repeat(2,1fr)}

  .realm{min-height:330px}

}

@media(max-width:520px){

  nav{padding:20px 5%}.nav-links{gap:12px}

  .nav-links a{font-size:9px}

  .logo{font-size:12px;letter-spacing:3px}

  section{padding:80px 6%}

  .realm-grid{gap:9px}

  .realm{min-height:300px;padding:18px 13px}

  .realm-symbol{font-size:58px;top:25px}

  .realm h3{font-size:18px}

  .realm p{font-size:11px;min-height:90px}

}

</style>

</head>

<body>

<div id="stars"></div><div class="noise"></div>

<nav>

  <div class="logo">HEXED : SIAM</div>

  <div class="nav-links">

    <a href="#story">THE LEGEND</a>

    <a href="#realms">REALMS</a>

    <a href="#ceremony">CEREMONY</a>

  </div>

</nav>

<header class="hero">

  <div class="hero-content">

    <div class="eyebrow">A WORLD BEYOND THE ORDINARY</div>

    <h1>HEXED</h1>

    <h2>SIAM</h2>

    <p>

      เบื้องหลังแผ่นดินสยามที่เรารู้จัก

      ยังมีอีกโลกหนึ่งซ่อนอยู่ โลกที่เวทมนตร์ไม่เคยเลือนหาย

      และโชคชะตาของคุณอาจถูกกำหนดไว้แล้ว

    </p>

    <button class="gold-btn" onclick="document.getElementById('story').scrollIntoView({behavior:'smooth'})">

      ENTER THE HIDDEN WORLD

    </button>

  </div>

  <div class="scroll">SCROLL TO DISCOVER ✧</div>

</header>

<section class="story" id="story">

  <div class="story-inner">

    <div class="story-mark">✧</div>

    <div class="kicker">THE FORGOTTEN LEGEND</div>

    <h3>ตำนานแห่ง HEXED: SIAM</h3>

    <div class="divider"></div>

    <p>

      นานมาแล้ว ก่อนที่โลกมนุษย์จะรู้จักคำว่าเวทมนตร์

      ผืนแผ่นดินสยามเคยเป็นศูนย์กลางของพลังลี้ลับ

      ที่เชื่อมโยงระหว่างมนุษย์และสิ่งเหนือธรรมชาติ

    </p>

    <p>

      พลังโบราณได้แบ่งตัวออกเป็น <strong>สี่อาณาจักร</strong>

      แต่ละแห่งมีผู้พิทักษ์และพลังที่แตกต่างกัน

      จนเกิดเป็นสมดุลที่คอยปกป้องโลกทั้งสอง

    </p>

    <p>

      หลายศตวรรษผ่านไป ความลับถูกซ่อนจากสายตามนุษย์

      แต่ในทุกยุคสมัย จะมีผู้ถูกเลือกให้ได้ยินเสียงเรียกจากโลกเวทมนตร์

    </p>

    <div class="divider"></div>

    <p style="color:var(--gold)">และบางที... คนคนนั้นอาจเป็นคุณ</p>

    <button class="outline-btn" onclick="document.getElementById('realms').scrollIntoView({behavior:'smooth'})">

      DISCOVER THE FOUR REALMS ↓

    </button>

  </div>

</section>

<section class="realms" id="realms">

  <div class="section-head">

    <div class="kicker">FOUR KINGDOMS · ONE DESTINY</div>

    <h2>THE FOUR REALMS</h2>

    <p>สี่อาณาจักรแห่งพลังโบราณ เลือกเปิดประตูเพื่อค้นพบโลกของพวกเขา</p>

  </div>

  <div class="realm-grid">

    <article class="realm aqua" onclick="showRealm('aqua')">

      <div class="realm-symbol">🐉</div>

      <div class="realm-info">

        <div class="realm-code">AQUA · WATER</div>

        <h3>อมรนที</h3>

        <p>อาณาจักรแห่งสายน้ำ ผู้สืบทอดพลังแห่งนาคา ลึกลับ ลุ่มลึก และเปี่ยมด้วยสัญชาตญาณ</p>

        <small>DISCOVER REALM ↗</small>

      </div>

    </article>

    <article class="realm ignis" onclick="showRealm('ignis')">

      <div class="realm-symbol">🔥</div>

      <div class="realm-info">

        <div class="realm-code">IGNIS · FIRE</div>

        <h3>สุริยานคร</h3>

        <p>อาณาจักรแห่งเปลวเพลิง ผู้สืบทอดพลังแห่งครุฑ กล้าหาญ ทะเยอทะยาน และทรงพลัง</p>

        <small>DISCOVER REALM ↗</small>

      </div>

    </article>

    <article class="realm aeris" onclick="showRealm('aeris')">

      <div class="realm-symbol">🪽</div>

      <div class="realm-info">

        <div class="realm-code">AERIS · AIR</div>

        <h3>เวหานคร</h3>

        <p>อาณาจักรแห่งสายลม ผู้สืบทอดพลังแห่งกินรี อิสระ อ่อนโยน และมีจินตนาการ</p>

        <small>DISCOVER REALM ↗</small>

      </div>

    </article>

    <article class="realm terra" onclick="showRealm('terra')">

      <div class="realm-symbol">🌳</div>

      <div class="realm-info">

        <div class="realm-code">TERRA · EARTH</div>

        <h3>พนาลัย</h3>

        <p>อาณาจักรแห่งผืนดิน ผู้สืบทอดพลังแห่งยักษ์ หนักแน่น ซื่อสัตย์ และไม่ยอมแพ้</p>

        <small>DISCOVER REALM ↗</small>

      </div>

    </article>

  </div>

  <div class="realm-detail" id="realmDetail">

    <h3 id="detailTitle"></h3>

    <p id="detailText"></p>

    <button class="outline-btn" onclick="document.getElementById('ceremony').scrollIntoView({behavior:'smooth'})">FIND YOUR DESTINY →</button>

  </div>

</section>

<section class="academy">

  <div class="academy-seal">A</div>

  <div class="kicker">THE SCHOOL OF ANCIENT MAGIC</div>

  <h2>AURELIA ACADEMY</h2>

  <p>

    สถาบันเวทมนตร์กลางแห่ง HEXED:SIAM

    สถานที่ซึ่งผู้มีพลังจากทั้งสี่อาณาจักรมารวมตัวกัน

    เพื่อเรียนรู้ศาสตร์โบราณและค้นพบพลังที่แท้จริงของตนเอง

  </p>

  <div class="divider"></div>

  <p style="color:var(--gold)">ทุกคนมีพลังบางอย่างซ่อนอยู่ภายใน เพียงรอวันที่มันจะตื่นขึ้น</p>

</section>

<section class="quiz" id="ceremony">

  <div class="section-head">

    <div class="kicker">THE MOMENT OF TRUTH</div>

    <h2>DESTINY CEREMONY</h2>

    <p>พิธีคัดสรรกำลังจะเริ่มต้น ตอบคำถามจากหัวใจ แล้วค้นพบอาณาจักรที่เรียกหาคุณ</p>

  </div>

  <div class="quiz-box">

    <div id="quizContent">

      <div class="progress"><span id="progressBar"></span></div>

      <div class="question-no" id="questionNo">QUESTION 01 / 06</div>

      <h3 class="question" id="questionText"></h3>

      <div class="answers" id="answers"></div>

      <div class="quiz-actions">

        <button class="outline-btn" id="backBtn" onclick="previousQuestion()" style="visibility:hidden">← BACK</button>

        <button class="gold-btn" id="nextBtn" onclick="nextQuestion()" disabled>NEXT →</button>

      </div>

    </div>

    <div class="result" id="result">

      <div class="kicker">YOUR DESTINY HAS BEEN REVEALED</div>

      <div class="symbol" id="resultSymbol"></div>

      <h3 id="resultRealm"></h3>

      <h4 id="resultName"></h4>

      <p id="resultText"></p>

      <button class="gold-btn" onclick="restartQuiz()">TAKE THE CEREMONY AGAIN</button>

    </div>

  </div>

</section>

<footer>

  <strong>HEXED : SIAM</strong>

  <p>A HIDDEN WORLD WITHIN THAILAND</p>

  <p>✧ THE MAGIC WAS NEVER GONE ✧</p>

</footer>

<script>

const realms={

 aqua:{

  title:"AQUA — อมรนที",symbol:"🐉",

  text:"สายน้ำเลือกคุณ เพราะคุณมีหัวใจที่ลึกซึ้งและเข้าใจความรู้สึกของผู้อื่น คุณอาจดูสงบนิ่ง แต่ภายในเต็มไปด้วยพลังและความมุ่งมั่น ผู้พิทักษ์แห่งนาคายินดีต้อนรับคุณสู่อมรนที"

 },

 ignis:{

  title:"IGNIS — สุริยานคร",symbol:"🔥",

  text:"เปลวเพลิงเลือกคุณ เพราะคุณไม่เคยกลัวที่จะก้าวไปข้างหน้า คุณมีความกล้าหาญ ความมุ่งมั่น และพร้อมต่อสู้เพื่อสิ่งที่เชื่อ ผู้พิทักษ์แห่งครุฑรอคุณอยู่ที่สุริยานคร"

 },

 aeris:{

  title:"AERIS — เวหานคร",symbol:"🪽",

  text:"สายลมเลือกคุณ เพราะคุณมีจิตวิญญาณที่เป็นอิสระ มองโลกได้กว้างไกล และมีความคิดสร้างสรรค์ คุณไม่จำเป็นต้องเดินตามใคร ผู้พิทักษ์แห่งกินรีขอต้อนรับสู่นครแห่งเวหา"

 },

 terra:{

  title:"TERRA — พนาลัย",symbol:"🌳",

  text:"ผืนดินเลือกคุณ เพราะคุณเป็นคนหนักแน่น อดทน และเป็นที่พึ่งให้คนรอบข้างได้ แม้เส้นทางจะยากลำบาก คุณก็ยังยืนหยัด ผู้พิทักษ์แห่งยักษ์ขอต้อนรับสู่พนาลัย"

 }

};

function showRealm(id){

 const r=realms[id];

 document.getElementById('detailTitle').textContent=r.title;

 document.getElementById('detailText').textContent=r.text;

 const box=document.getElementById('realmDetail');

 box.classList.add('show');

 box.scrollIntoView({behavior:'smooth',block:'center'});

}

const questions=[

 {q:"เมื่อคุณต้องเผชิญกับสถานการณ์ที่ไม่คาดคิด คุณจะ...",a:[

  ["ตั้งสติและใช้ความรู้สึกนำทาง","aqua"],

  ["ลุกขึ้นเผชิญหน้าโดยไม่ลังเล","ignis"],

  ["มองหาวิธีใหม่ที่ไม่มีใครคิดถึง","aeris"],

  ["ค่อย ๆ วางแผนและหาทางออก","terra"]

 ]},

 {q:"สิ่งใดสำคัญที่สุดสำหรับคุณ?",a:[

  ["ความเข้าใจและความสัมพันธ์","aqua"],

  ["ความสำเร็จและความกล้าหาญ","ignis"],

  ["อิสรภาพและการค้นพบ","aeris"],

  ["ความมั่นคงและความไว้วางใจ","terra"]

 ]},

 {q:"หากได้รับพลังวิเศษหนึ่งอย่าง คุณจะเลือก...",a:[

  ["ควบคุมสายน้ำและรักษาบาดแผล","aqua"],

  ["ควบคุมเปลวเพลิงและพลังแสง","ignis"],

  ["เหาะเหินและควบคุมสายลม","aeris"],

  ["ควบคุมผืนดินและสร้างเกราะป้องกัน","terra"]

 ]},

 {q:"เพื่อนมักมองคุณเป็นคนแบบไหน?",a:[

  ["เข้าใจคนอื่นและเป็นผู้ฟังที่ดี","aqua"],

  ["เด็ดเดี่ยวและกล้าตัดสินใจ","ignis"],

  ["มีไอเดียแปลกใหม่และรักอิสระ","aeris"],

  ["พึ่งพาได้และรักษาคำพูด","terra"]

 ]},

 {q:"สถานที่ใดเรียกหาคุณมากที่สุด?",a:[

  ["นครลึกลับใต้ผืนน้ำ","aqua"],

  ["นครทองคำกลางแสงอาทิตย์","ignis"],

  ["นครลอยฟ้าท่ามกลางเมฆหมอก","aeris"],

  ["นครโบราณกลางป่าศักดิ์สิทธิ์","terra"]

 ]},

 {q:"หากต้องเลือกคำหนึ่งคำแทนตัวคุณ คุณจะเลือก...",a:[

  ["ลึกซึ้ง","aqua"],

  ["เปล่งประกาย","ignis"],

  ["อิสระ","aeris"],

  ["แข็งแกร่ง","terra"]

 ]}

];

let current=0;

let selected=Array(questions.length).fill(null);

let scores={aqua:0,ignis:0,aeris:0,terra:0};

function renderQuestion(){

 const q=questions[current];

 document.getElementById('questionNo').textContent=

  `QUESTION ${String(current+1).padStart(2,'0')} / 06`;

 document.getElementById('questionText').textContent=q.q;

 document.getElementById('progressBar').style.width=

  `${(current/questions.length)*100}%`;

 document.getElementById('backBtn').style.visibility=current===0?'hidden':'visible';

 document.getElementById('nextBtn').disabled=selected[current]===null;

 document.getElementById('nextBtn').textContent=current===5?'REVEAL MY DESTINY ✧':'NEXT →';

 const wrap=document.getElementById('answers');

 wrap.innerHTML='';

 q.a.forEach(([label,id])=>{

  const b=document.createElement('button');

  b.className='answer'+(selected[current]===id?' selected':'');

  b.textContent=label;

  b.onclick=()=>{

   selected[current]=id;

   renderQuestion();

  };

  wrap.appendChild(b);

 });

}

function nextQuestion(){

 if(selected[current]===null)return;

 if(current<5){current++;renderQuestion()}

 else{showResult()}

}

function previousQuestion(){

 if(current>0){current--;renderQuestion()}

}

function showResult(){

 scores={aqua:0,ignis:0,aeris:0,terra:0};

 selected.forEach(id=>scores[id]++);

 const winner=Object.keys(scores).sort((a,b)=>scores[b]-scores[a])[0];

 const r=realms[winner];

 document.getElementById('quizContent').style.display='none';

 document.getElementById('result').classList.add('show');

 document.getElementById('resultSymbol').textContent=r.symbol;

 document.getElementById('resultRealm').textContent=winner.toUpperCase();

 document.getElementById('resultName').textContent=r.title.split('—')[1];

 document.getElementById('resultText').textContent=r.text;

 document.getElementById('progressBar').style.width='100%';

}

function restartQuiz(){

 current=0;selected=Array(questions.length).fill(null);

 document.getElementById('result').classList.remove('show');

 document.getElementById('quizContent').style.display='block';

 renderQuestion();

}

renderQuestion();

</script>

</body>

</html>
