<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<title>เนื้อในจันท์ — สารานุกรมเนื้อสัมผัสทุเรียนจันทบุรี</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Chonburi&family=IBM+Plex+Sans+Thai:wght@300;400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --cream:#FBF3E1;
    --cream-dim:#F3E9D2;
    --leaf:#2B4736;
    --leaf-light:#4C7259;
    --gold:#E8A93D;
    --gold-deep:#C9862A;
    --husk:#4A3423;
    --maroon:#8B3A3A;
    --ink:#241C14;
    --line: rgba(36,28,20,0.14);
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:var(--cream);
    color:var(--ink);
    font-family:'IBM Plex Sans Thai', sans-serif;
    line-height:1.65;
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3,.display{ font-family:'Chonburi', 'IBM Plex Sans Thai', serif; font-weight:400; }
  .mono{ font-family:'IBM Plex Mono', monospace; letter-spacing:0.02em; }
  a{color:inherit;}
  button{font-family:inherit; cursor:pointer;}

  /* ---------- NAV ---------- */
  .nav{
    position:sticky; top:0; z-index:40;
    display:flex; align-items:center; justify-content:space-between;
    padding:16px 28px;
    background:rgba(251,243,225,0.92);
    backdrop-filter: blur(6px);
    border-bottom:1px solid var(--line);
  }
  .brand{ display:flex; align-items:center; gap:10px; }
  .brand-mark{
    width:30px; height:30px; border-radius:50%;
    background: radial-gradient(circle at 35% 30%, var(--gold), var(--gold-deep));
    position:relative; flex-shrink:0;
    box-shadow: 0 0 0 3px var(--leaf-light) inset;
  }
  .brand-name{ font-size:1.25rem; }
  .brand-name b{ color:var(--maroon); }
  .admin-btn{
    border:1.5px solid var(--husk); background:transparent; color:var(--husk);
    padding:8px 16px; border-radius:999px; font-size:0.82rem; font-weight:600;
    transition:.2s;
  }
  .admin-btn:hover{ background:var(--husk); color:var(--cream); }
  .admin-btn.on{ background:var(--maroon); border-color:var(--maroon); color:var(--cream); }

  /* ---------- HERO ---------- */
  .hero{
    position:relative;
    padding:64px 28px 0;
    max-width:980px; margin:0 auto;
    text-align:left;
  }
  .eyebrow{
    font-size:0.78rem; letter-spacing:0.14em; text-transform:uppercase;
    color:var(--leaf); font-weight:600; margin-bottom:14px;
  }
  .hero h1{
    font-size:clamp(2.1rem, 5vw, 3.4rem);
    line-height:1.25; margin:0 0 20px; color:var(--husk);
  }
  .hero h1 span{ color:var(--maroon); }
  .hero p.lede{ max-width:560px; font-size:1.05rem; color:#3d3126; margin-bottom:30px;}
  .hero-cta{
    display:inline-flex; align-items:center; gap:8px;
    background:var(--leaf); color:var(--cream); border:none;
    padding:13px 26px; border-radius:999px; font-size:0.95rem; font-weight:600;
    margin-bottom:44px;
  }
  .hero-cta:hover{ background:var(--leaf-light); }

  .spike-divider{ width:100%; height:34px; display:block; }

  .stats-bar{
    display:flex; gap:0; flex-wrap:wrap;
    background:var(--husk); color:var(--cream);
  }
  .stat{
    flex:1; min-width:160px; padding:22px 28px; border-right:1px solid rgba(251,243,225,0.15);
  }
  .stat:last-child{ border-right:none; }
  .stat .num{ font-size:1.9rem; color:var(--gold); display:block; }
  .stat .lbl{ font-size:0.78rem; opacity:0.75; }

  /* ---------- SECTION ---------- */
  .section{ max-width:1080px; margin:0 auto; padding:64px 28px; }
  .section-head{ margin-bottom:34px; }
  .section-head h2{ font-size:1.7rem; color:var(--husk); margin:0 0 8px; }
  .section-head p{ color:#5a4b3a; margin:0; max-width:640px; }

  .grid{
    display:grid; grid-template-columns:repeat(auto-fill,minmax(270px,1fr)); gap:22px;
  }
  .card{
    background:var(--cream-dim); border:1px solid var(--line); border-radius:18px;
    padding:22px; position:relative; transition:.2s; cursor:pointer;
  }
  .card:hover{ transform:translateY(-3px); box-shadow:0 10px 24px rgba(74,52,35,0.12); }
  .card-top{ display:flex; align-items:center; gap:14px; margin-bottom:14px; }
  .flesh-dot{
    width:52px; height:52px; border-radius:50%; flex-shrink:0;
    box-shadow: 0 0 0 3px var(--leaf-light) inset;
  }
  .card-name{ font-size:1.15rem; color:var(--husk); margin:0; }
  .card-nick{ font-size:0.78rem; color:var(--leaf); margin:2px 0 0; }
  .card-desc{ font-size:0.88rem; color:#4a3d2f; margin:0 0 14px; min-height:44px; }
  .stars{ display:flex; align-items:center; gap:5px; font-size:0.85rem; }
  .stars .s{ color:var(--gold-deep); }
  .stars .count{ color:#8a7c68; font-size:0.78rem; }
  .card-admin-row{ display:flex; gap:8px; margin-top:14px; }
  .mini-btn{
    border:none; border-radius:8px; padding:6px 10px; font-size:0.75rem; font-weight:600;
  }
  .mini-btn.edit{ background:var(--leaf-light); color:var(--cream); }
  .mini-btn.del{ background:var(--maroon); color:var(--cream); }

  .add-card{
    border:2px dashed var(--leaf-light); background:transparent;
    display:flex; align-items:center; justify-content:center; flex-direction:column; gap:8px;
    color:var(--leaf); font-weight:600; min-height:180px;
  }

  /* ---------- OVERLAY / MODAL ---------- */
  .overlay{
    position:fixed; inset:0; background:rgba(36,28,20,0.55); z-index:80;
    display:flex; align-items:flex-start; justify-content:center; padding:40px 18px;
    overflow-y:auto;
  }
  .modal{
    background:var(--cream); border-radius:20px; max-width:680px; width:100%;
    padding:32px; position:relative; margin-bottom:40px;
  }
  .close-x{
    position:absolute; top:18px; right:18px; background:none; border:none;
    font-size:1.4rem; color:var(--husk); line-height:1;
  }
  .modal h2{ color:var(--husk); margin:0 0 4px; font-size:1.6rem; }
  .modal .nick{ color:var(--leaf); font-size:0.85rem; margin-bottom:6px; }
  .modal .origin{ font-size:0.8rem; color:#7a6c58; margin-bottom:18px; }
  .modal p.desc{ color:#3d3126; margin-bottom:24px; }

  .texture-row{ display:flex; align-items:center; gap:14px; margin-bottom:10px; }
  .texture-label{ width:110px; font-size:0.82rem; color:var(--husk); flex-shrink:0; }
  .spikes{ display:flex; align-items:flex-end; gap:3px; height:34px; flex:1; }
  .spike{
    flex:1; background:var(--gold); clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
    background:linear-gradient(180deg, var(--gold), var(--gold-deep));
  }
  .spike.off{ background:var(--line); opacity:0.5; }
  .texture-val{ width:22px; text-align:right; font-size:0.78rem; color:#7a6c58; }

  .rate-line{ display:flex; align-items:center; gap:10px; margin:22px 0 6px; }
  .avg-star{ font-size:1.3rem; color:var(--gold-deep); }

  .comments{ margin-top:26px; border-top:1px solid var(--line); padding-top:22px; }
  .comments h3{ font-size:1.05rem; color:var(--husk); margin:0 0 14px; }
  .comment{
    background:var(--cream-dim); border-radius:12px; padding:12px 14px; margin-bottom:10px;
    font-size:0.88rem;
  }
  .comment-head{ display:flex; justify-content:space-between; align-items:center; margin-bottom:4px; }
  .comment-name{ font-weight:600; color:var(--husk); }
  .comment-stars{ color:var(--gold-deep); font-size:0.8rem; }
  .comment-del{ background:none; border:none; color:var(--maroon); font-size:0.72rem; }

  .review-form{ margin-top:18px; }
  .review-form input, .review-form textarea{
    width:100%; padding:10px 12px; border:1px solid var(--line); border-radius:10px;
    font-family:inherit; font-size:0.88rem; margin-bottom:10px; background:#fff;
  }
  .review-form textarea{ min-height:70px; resize:vertical; }
  .star-picker{ display:flex; gap:4px; margin-bottom:12px; }
  .star-picker span{ font-size:1.5rem; color:var(--line); }
  .star-picker span.active{ color:var(--gold-deep); }
  .submit-btn{
    background:var(--leaf); color:var(--cream); border:none; padding:10px 20px;
    border-radius:999px; font-weight:600; font-size:0.88rem;
  }
  .submit-btn:hover{ background:var(--leaf-light); }

  .edit-form label{ display:block; font-size:0.8rem; color:var(--husk); margin:12px 0 5px; font-weight:600; }
  .edit-form input, .edit-form textarea{
    width:100%; padding:9px 12px; border:1px solid var(--line); border-radius:10px;
    font-family:inherit; font-size:0.88rem; background:#fff;
  }
  .edit-form textarea{ min-height:60px; }
  .range-row{ display:flex; align-items:center; gap:10px; }
  .range-row input[type=range]{ flex:1; }
  .form-actions{ display:flex; gap:10px; margin-top:20px; }
  .btn-secondary{ background:transparent; border:1.5px solid var(--husk); color:var(--husk); padding:9px 18px; border-radius:999px; font-size:0.85rem; font-weight:600; }

  .empty-note{ font-size:0.82rem; color:#8a7c68; }
  footer{ text-align:center; padding:40px 20px; font-size:0.78rem; color:#8a7c68; }

  @media (max-width:600px){
    .stat{ min-width:50%; }
  }
</style>
</head>
<body>

<nav class="nav">
  <div class="brand">
    <div class="brand-mark"></div>
    <div class="brand-name">เนื้อ<b>ใน</b>จันท์</div>
  </div>
  <button class="admin-btn" id="adminBtn">เข้าสู่ระบบเจ้าของ</button>
</nav>

<header class="hero">
  <div class="eyebrow">โครงงานวิจัยระดับประเทศ · จังหวัดจันทบุรี</div>
  <h1>เปิดเนื้อใน<span>ทุเรียนจันท์</span><br>ทีละสายพันธุ์ ทีละคำ</h1>
  <p class="lede">ฐานข้อมูลเปิดสำหรับบันทึกลักษณะเนื้อสัมผัสของทุเรียนแต่ละสายพันธุ์ในจันทบุรี ทุกคนร่วมให้คะแนนและรีวิวได้ ส่วนข้อมูลหลักดูแลโดยผู้วิจัยเจ้าของโครงงาน</p>
  <button class="hero-cta" onclick="document.getElementById('varietySection').scrollIntoView({behavior:'smooth'})">สำรวจสายพันธุ์ ↓</button>
</header>

<svg class="spike-divider" viewBox="0 0 400 20" preserveAspectRatio="none"><polygon points="0,20 0,10 10,20 20,8 30,20 40,10 50,20 60,6 70,20 80,10 90,20 100,8 110,20 120,10 130,20 140,6 150,20 160,10 170,20 180,8 190,20 200,10 210,20 220,6 230,20 240,10 250,20 260,8 270,20 280,10 290,20 300,6 310,20 320,10 330,20 340,8 350,20 360,10 370,20 380,6 390,20 400,10 400,20" fill="#2B4736"/></svg>

<div class="stats-bar">
  <div class="stat"><span class="num mono" id="statCount">–</span><span class="lbl">สายพันธุ์ที่บันทึก</span></div>
  <div class="stat"><span class="num mono" id="statReviews">–</span><span class="lbl">รีวิวทั้งหมด</span></div>
  <div class="stat"><span class="num mono">อำเภอเมือง · ท่าใหม่ · ขลุง</span><span class="lbl">แหล่งเก็บข้อมูล</span></div>
</div>

<section class="section" id="varietySection">
  <div class="section-head">
    <h2>สายพันธุ์ทุเรียนจันทบุรี</h2>
    <p>แตะการ์ดเพื่อดูโปรไฟล์เนื้อสัมผัสแบบละเอียด ให้ดาว และแสดงความเห็นได้ทุกคน</p>
  </div>
  <div class="grid" id="varietyGrid">
    <div class="empty-note">กำลังโหลดข้อมูล...</div>
  </div>
</section>

<footer>เนื้อในจันท์ · โครงงานวิจัยเพื่อบันทึกลักษณะเฉพาะของทุเรียนจันทบุรี · ข้อมูลหลักแก้ไขได้โดยเจ้าของโครงงานเท่านั้น</footer>

<div id="modalRoot"></div>

<script>
/* ================= CONFIG ================= */
// ตั้งรหัสผ่านเจ้าของที่นี่ (เปลี่ยนก่อนเผยแพร่จริง)
const ADMIN_PASSWORD = "chanthaburi2569";
let isAdmin = false;

const DEFAULT_VARIETIES = [
  { id:"monthong", name:"หมอนทอง", nick:"ราชาทุเรียนจันท์", origin:"อำเภอเมือง, จันทบุรี",
    desc:"เนื้อละเอียด แห้ง เหนียวนุ่ม สีเหลืองอ่อน กลิ่นไม่ฉุนมากเมื่อเทียบกับสายพันธุ์อื่น เมล็ดลีบเล็ก",
    color:"#E8B84A", texture:{sweet:4, fiber:2, moist:2, rich:4} },
  { id:"chanee", name:"ชะนี", nick:"เนื้อเข้มรสจัด", origin:"อำเภอท่าใหม่, จันทบุรี",
    desc:"เนื้อสีเหลืองเข้ม เหนียวแน่นกว่าหมอนทอง กลิ่นแรงปานกลาง รสหวานมันกลมกล่อม พูสวยเรียงตัวดี",
    color:"#D89A2E", texture:{sweet:4, fiber:3, moist:2, rich:4} },
  { id:"kradum", name:"กระดุมทอง", nick:"ลูกเล็กสุกไว", origin:"อำเภอขลุง, จันทบุรี",
    desc:"ผลขนาดเล็ก เนื้อบางแต่ละเอียดนุ่ม หวานจัด สุกเร็วกว่าสายพันธุ์อื่น เหมาะทานทั้งลูก",
    color:"#F0C24C", texture:{sweet:5, fiber:2, moist:3, rich:3} },
  { id:"puangmanee", name:"พวงมณี", nick:"เนื้อแน่นเมล็ดลีบ", origin:"อำเภอมะขาม, จันทบุรี",
    desc:"เนื้อสีเหลืองเข้ม เหนียวแน่น หวานมันชัดเจน เมล็ดลีบเล็กมาก เนื้อต่อพูเยอะ",
    color:"#DE9A28", texture:{sweet:4, fiber:3, moist:2, rich:5} },
  { id:"kanyao", name:"ก้านยาว", nick:"เนื้อนุ่มกลิ่นอ่อน", origin:"อำเภอแก่งหางแมว, จันทบุรี",
    desc:"เนื้อละเอียด สีเหลืองอ่อน เหนียวพอดี หวานมันสมดุล กลิ่นไม่แรง ก้านผลยาวเป็นเอกลักษณ์",
    color:"#E7C066", texture:{sweet:3, fiber:2, moist:3, rich:3} },
  { id:"nokkachip", name:"นกกระจิบ", nick:"พันธุ์พื้นเมืองลูกจิ๋ว", origin:"อำเภอโป่งน้ำร้อน, จันทบุรี",
    desc:"ผลเล็กมาก เนื้อบางแต่เนียนละเอียด รสหวานจัด เป็นสายพันธุ์พื้นเมืองดั้งเดิมของจันทบุรี",
    color:"#F2CD5C", texture:{sweet:5, fiber:1, moist:3, rich:2} }
];

const $ = (sel, root=document) => root.querySelector(sel);
const $$ = (sel, root=document) => [...root.querySelectorAll(sel)];

/* ================= STORAGE HELPERS ================= */
async function getVarieties(){
  try{
    const r = await window.storage.get('varieties', true);
    return r ? JSON.parse(r.value) : null;
  }catch(e){ return null; }
}
async function saveVarieties(list){
  try{ await window.storage.set('varieties', JSON.stringify(list), true); }
  catch(e){ console.error('save varieties failed', e); }
}
async function getComments(id){
  try{
    const r = await window.storage.get('comments:'+id, true);
    return r ? JSON.parse(r.value) : [];
  }catch(e){ return []; }
}
async function saveComments(id, list){
  try{ await window.storage.set('comments:'+id, JSON.stringify(list), true); }
  catch(e){ console.error('save comments failed', e); }
}

/* ================= STATE ================= */
let varieties = [];

async function init(){
  let stored = await getVarieties();
  if(!stored || stored.length===0){
    stored = DEFAULT_VARIETIES;
    await saveVarieties(stored);
  }
  varieties = stored;
  await renderGrid();
}

/* ================= RENDER GRID ================= */
async function renderGrid(){
  const grid = $('#varietyGrid');
  grid.innerHTML = '';
  let totalReviews = 0;

  for(const v of varieties){
    const comments = await getComments(v.id);
    totalReviews += comments.length;
    const avg = comments.length ? (comments.reduce((a,c)=>a+c.rating,0)/comments.length) : 0;

    const card = document.createElement('div');
    card.className = 'card';
    card.innerHTML = `
      <div class="card-top">
        <div class="flesh-dot" style="background:${v.color}"></div>
        <div>
          <p class="card-name">${escapeHtml(v.name)}</p>
          <p class="card-nick">${escapeHtml(v.nick||'')}</p>
        </div>
      </div>
      <p class="card-desc">${escapeHtml(v.desc).slice(0,90)}${v.desc.length>90?'…':''}</p>
      <div class="stars">
        <span class="s">${starString(avg)}</span>
        <span class="count">${comments.length ? avg.toFixed(1)+' · '+comments.length+' รีวิว' : 'ยังไม่มีรีวิว'}</span>
      </div>
      ${isAdmin ? `<div class="card-admin-row">
        <button class="mini-btn edit" data-edit="${v.id}">แก้ไข</button>
        <button class="mini-btn del" data-del="${v.id}">ลบ</button>
      </div>` : ''}
    `;
    card.addEventListener('click', (e)=>{
      if(e.target.closest('[data-edit]') || e.target.closest('[data-del]')) return;
      openDetail(v.id);
    });
    grid.appendChild(card);
  }

  if(isAdmin){
    const addCard = document.createElement('div');
    addCard.className = 'card add-card';
    addCard.innerHTML = `<div style="font-size:1.6rem;">＋</div><div>เพิ่มสายพันธุ์ใหม่</div>`;
    addCard.addEventListener('click', ()=>openEditForm(null));
    grid.appendChild(addCard);
  }

  $$('[data-edit]').forEach(b=>b.addEventListener('click', ()=>openEditForm(b.dataset.edit)));
  $$('[data-del]').forEach(b=>b.addEventListener('click', ()=>deleteVariety(b.dataset.del)));

  $('#statCount').textContent = varieties.length;
  $('#statReviews').textContent = totalReviews;
}

function starString(avg){
  const full = Math.round(avg);
  return '★'.repeat(full) + '☆'.repeat(5-full);
}
function escapeHtml(str){
  return (str||'').replace(/[&<>"']/g, m=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[m]));
}

/* ================= DETAIL MODAL ================= */
async function openDetail(id){
  const v = varieties.find(x=>x.id===id);
  if(!v) return;
  const comments = await getComments(id);
  const avg = comments.length ? (comments.reduce((a,c)=>a+c.rating,0)/comments.length) : 0;

  const root = $('#modalRoot');
  root.innerHTML = `
    <div class="overlay" id="overlay">
      <div class="modal">
        <button class="close-x" id="closeModal">✕</button>
        <h2>${escapeHtml(v.name)}</h2>
        <div class="nick">${escapeHtml(v.nick||'')}</div>
        <div class="origin">แหล่งข้อมูล: ${escapeHtml(v.origin||'-')}</div>
        <p class="desc">${escapeHtml(v.desc)}</p>

        <div class="texture-block">
          ${textureRow('ความหวาน', v.texture.sweet)}
          ${textureRow('เส้นใย', v.texture.fiber)}
          ${textureRow('ความชื้น', v.texture.moist)}
          ${textureRow('ความมัน', v.texture.rich)}
        </div>

        <div class="rate-line">
          <span class="avg-star">${starString(avg)}</span>
          <span class="mono">${comments.length ? avg.toFixed(1) : '–'}</span>
          <span class="empty-note">(${comments.length} รีวิว)</span>
        </div>

        <div class="comments">
          <h3>ความคิดเห็นและคะแนนจากผู้ใช้</h3>
          <div id="commentList">
            ${comments.length ? comments.map(c=>commentHtml(c, id)).join('') : '<p class="empty-note">ยังไม่มีความคิดเห็น เป็นคนแรกที่รีวิวสิ!</p>'}
          </div>

          <div class="review-form">
            <input type="text" id="cName" placeholder="ชื่อของคุณ" maxlength="40">
            <div class="star-picker" id="starPicker">
              ${[1,2,3,4,5].map(n=>`<span data-n="${n}">★</span>`).join('')}
            </div>
            <textarea id="cText" placeholder="เล่าประสบการณ์เนื้อสัมผัส รสชาติ กลิ่น..." maxlength="400"></textarea>
            <button class="submit-btn" id="submitReview">ส่งรีวิว</button>
          </div>
        </div>
      </div>
    </div>
  `;

  $('#closeModal').addEventListener('click', closeModal);
  $('#overlay').addEventListener('click', (e)=>{ if(e.target.id==='overlay') closeModal(); });

  let chosenRating = 0;
  $$('#starPicker span').forEach(s=>{
    s.addEventListener('click', ()=>{
      chosenRating = parseInt(s.dataset.n);
      $$('#starPicker span').forEach(x=> x.classList.toggle('active', parseInt(x.dataset.n)<=chosenRating));
    });
  });

  $('#submitReview').addEventListener('click', async ()=>{
    const name = $('#cName').value.trim() || 'ผู้เยี่ยมชม';
    const text = $('#cText').value.trim();
    if(!chosenRating){ alert('กรุณาเลือกจำนวนดาวก่อนส่งรีวิว'); return; }
    if(!text){ alert('กรุณาเขียนความคิดเห็นสั้นๆ'); return; }
    const newComments = await getComments(id);
    newComments.push({ id: Date.now().toString(), name, rating: chosenRating, text, date: new Date().toLocaleDateString('th-TH') });
    await saveComments(id, newComments);
    await openDetail(id);
    await renderGrid();
  });

  $$('[data-delcomment]').forEach(b=>{
    b.addEventListener('click', async ()=>{
      const cid = b.dataset.delcomment;
      const list = (await getComments(id)).filter(c=>c.id!==cid);
      await saveComments(id, list);
      await openDetail(id);
      await renderGrid();
    });
  });
}

function textureRow(label, val){
  return `<div class="texture-row">
    <div class="texture-label">${label}</div>
    <div class="spikes">${[1,2,3,4,5].map(n=>`<div class="spike ${n<=val?'':'off'}"></div>`).join('')}</div>
    <div class="texture-val mono">${val}/5</div>
  </div>`;
}

function commentHtml(c, varietyId){
  return `<div class="comment">
    <div class="comment-head">
      <span class="comment-name">${escapeHtml(c.name)}</span>
      <span class="comment-stars">${'★'.repeat(c.rating)}${'☆'.repeat(5-c.rating)}</span>
    </div>
    <div>${escapeHtml(c.text)}</div>
    ${isAdmin ? `<button class="comment-del" data-delcomment="${c.id}">ลบความคิดเห็นนี้</button>` : ''}
  </div>`;
}

function closeModal(){ $('#modalRoot').innerHTML = ''; }

/* ================= ADMIN: EDIT / ADD / DELETE VARIETY ================= */
function openEditForm(id){
  const v = id ? varieties.find(x=>x.id===id) : null;
  const root = $('#modalRoot');
  root.innerHTML = `
    <div class="overlay" id="overlay">
      <div class="modal">
        <button class="close-x" id="closeModal">✕</button>
        <h2>${v ? 'แก้ไขสายพันธุ์' : 'เพิ่มสายพันธุ์ใหม่'}</h2>
        <div class="edit-form">
          <label>ชื่อสายพันธุ์</label>
          <input id="fName" value="${v?escapeHtml(v.name):''}">
          <label>ชื่อเล่น / จุดเด่นสั้นๆ</label>
          <input id="fNick" value="${v?escapeHtml(v.nick||''):''}">
          <label>แหล่งข้อมูล (อำเภอ)</label>
          <input id="fOrigin" value="${v?escapeHtml(v.origin||''):''}">
          <label>สีเนื้อ (hex)</label>
          <input id="fColor" type="color" value="${v?v.color:'#E8A93D'}" style="height:42px; padding:4px;">
          <label>คำอธิบายเนื้อสัมผัสแบบละเอียด</label>
          <textarea id="fDesc">${v?escapeHtml(v.desc):''}</textarea>
          <label>ความหวาน (0-5)</label>
          <div class="range-row"><input type="range" id="fSweet" min="0" max="5" value="${v?v.texture.sweet:3}"><span class="mono" id="fSweetVal">${v?v.texture.sweet:3}</span></div>
          <label>เส้นใย (0-5)</label>
          <div class="range-row"><input type="range" id="fFiber" min="0" max="5" value="${v?v.texture.fiber:3}"><span class="mono" id="fFiberVal">${v?v.texture.fiber:3}</span></div>
          <label>ความชื้น (0-5)</label>
          <div class="range-row"><input type="range" id="fMoist" min="0" max="5" value="${v?v.texture.moist:3}"><span class="mono" id="fMoistVal">${v?v.texture.moist:3}</span></div>
          <label>ความมัน (0-5)</label>
          <div class="range-row"><input type="range" id="fRich" min="0" max="5" value="${v?v.texture.rich:3}"><span class="mono" id="fRichVal">${v?v.texture.rich:3}</span></div>

          <div class="form-actions">
            <button class="submit-btn" id="saveVariety">บันทึก</button>
            <button class="btn-secondary" id="cancelEdit">ยกเลิก</button>
          </div>
        </div>
      </div>
    </div>
  `;
  ['Sweet','Fiber','Moist','Rich'].forEach(k=>{
    $('#f'+k).addEventListener('input', ()=>{ $('#f'+k+'Val').textContent = $('#f'+k).value; });
  });
  $('#closeModal').addEventListener('click', closeModal);
  $('#cancelEdit').addEventListener('click', closeModal);
  $('#overlay').addEventListener('click', (e)=>{ if(e.target.id==='overlay') closeModal(); });

  $('#saveVariety').addEventListener('click', async ()=>{
    const name = $('#fName').value.trim();
    if(!name){ alert('กรุณากรอกชื่อสายพันธุ์'); return; }
    const obj = {
      id: v ? v.id : slugify(name) + '-' + Date.now().toString(36),
      name,
      nick: $('#fNick').value.trim(),
      origin: $('#fOrigin').value.trim(),
      color: $('#fColor').value,
      desc: $('#fDesc').value.trim(),
      texture: {
        sweet: parseInt($('#fSweet').value),
        fiber: parseInt($('#fFiber').value),
        moist: parseInt($('#fMoist').value),
        rich: parseInt($('#fRich').value)
      }
    };
    if(v){
      varieties = varieties.map(x=> x.id===v.id ? obj : x);
    } else {
      varieties.push(obj);
    }
    await saveVarieties(varieties);
    closeModal();
    await renderGrid();
  });
}

function slugify(s){
  return s.toLowerCase().replace(/[^a-z0-9ก-๙]+/g,'-').replace(/(^-|-$)/g,'') || 'item';
}

async function deleteVariety(id){
  if(!confirm('ยืนยันการลบสายพันธุ์นี้? ความคิดเห็นทั้งหมดจะถูกลบด้วย')) return;
  varieties = varieties.filter(v=>v.id!==id);
  await saveVarieties(varieties);
  try{ await window.storage.delete('comments:'+id, true); }catch(e){}
  await renderGrid();
}

/* ================= ADMIN LOGIN ================= */
$('#adminBtn').addEventListener('click', ()=>{
  if(isAdmin){
    isAdmin = false;
    $('#adminBtn').textContent = 'เข้าสู่ระบบเจ้าของ';
    $('#adminBtn').classList.remove('on');
    renderGrid();
    return;
  }
  const pw = prompt('กรอกรหัสผ่านเจ้าของโครงงาน:');
  if(pw === null) return;
  if(pw === ADMIN_PASSWORD){
    isAdmin = true;
    $('#adminBtn').textContent = 'ออกจากโหมดเจ้าของ';
    $('#adminBtn').classList.add('on');
    renderGrid();
  } else {
    alert('รหัสผ่านไม่ถูกต้อง');
  }
});

init();
</script>
</body>
</html>
