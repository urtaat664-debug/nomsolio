<!DOCTYPE html>
<html lang="mn">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>НомСолио — сурах бичгээ солилц, зар, ав</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Manrope:wght@400;500;600;700;800&family=Unbounded:wght@600;700;800&display=swap&subset=cyrillic" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<style>
:root{
  --bg:#FFFCF5; --surface:#FFFFFF; --surface2:#F6F3FF; --ink:#1F1D3D; --muted:#69668A; --line:#E9E4F4;
  --sun:#FFC43D; --coral:#FF5A6E; --cobalt:#3B5BFD; --mint:#16BF9E; --violet:#8E5CF7; --orange:#FF8A3D;
  --onaccent:#FFFFFF; --shadow:0 2px 0 rgba(31,29,61,.08);
  --display:"Unbounded","Arial Black",system-ui,sans-serif;
  --body:"Manrope",system-ui,-apple-system,"Segoe UI",Roboto,sans-serif;
  color-scheme:light;
  box-sizing:border-box;
  padding-top:env(safe-area-inset-top,0px);
  padding-bottom:env(safe-area-inset-bottom,0px);
}
@media (prefers-color-scheme:dark){
  :root:not([data-theme="light"]){
    --bg:#15142A; --surface:#211F3B; --surface2:#2A2849; --ink:#F4F2FF; --muted:#A9A6CB; --line:#36335C;
    --shadow:0 2px 0 rgba(0,0,0,.3); color-scheme:dark;
  }
}
:root[data-theme="dark"]{
  --bg:#15142A; --surface:#211F3B; --surface2:#2A2849; --ink:#F4F2FF; --muted:#A9A6CB; --line:#36335C;
  --shadow:0 2px 0 rgba(0,0,0,.3); color-scheme:dark;
}
,::before,*::after{box-sizing:inherit}
html{scroll-padding-top:calc(env(safe-area-inset-top,0px) + 72px)}
body{margin:0;background:var(--bg);color:var(--ink);font-family:var(--body);font-size:16px;line-height:1.5;-webkit-font-smoothing:antialiased}
body::before{content:"";position:fixed;inset:0 0 auto;height:env(safe-area-inset-top,0px);z-index:10;background:var(--bg)}
img{max-width:100%;display:block}
button,input,select,textarea{font:inherit;color:inherit}
button{cursor:pointer}
:focus-visible{outline:3px solid var(--cobalt);outline-offset:2px}
.wrap{max-width:1120px;margin:0 auto;padding:0 16px}

/* header */
header{position:sticky;top:env(safe-area-inset-top,0px);z-index:9;background:var(--bg);border-bottom:1px solid var(--line)}
.bar{display:flex;align-items:center;gap:10px;height:64px}
.logo{display:flex;align-items:center;gap:8px;font-family:var(--display);font-weight:800;font-size:19px;text-decoration:none;color:var(--ink);margin-right:auto}
.logo i{display:flex;gap:2px;align-items:flex-end;height:26px}
.logo i b{width:6px;border-radius:2px}
.hbtn{border:1.5px solid var(--line);background:var(--surface);border-radius:12px;height:40px;padding:0 12px;display:flex;align-items:center;gap:6px;font-weight:700;font-size:14px}
.hbtn.primary{background:var(--ink);color:var(--bg);border-color:var(--ink)}
.hbtn svg{width:18px;height:18px}

/* hero */
.hero{padding:36px 0 0;position:relative;overflow:hidden}
.hero h1{font-family:var(--display);font-weight:800;font-size:clamp(30px,7vw,60px);line-height:1.05;letter-spacing:-.02em;margin:0 0 14px;max-width:14ch}
.hero p{color:var(--muted);max-width:52ch;margin:0 0 22px;font-size:17px}
.search{display:flex;align-items:center;gap:10px;background:var(--surface);border:2.5px solid var(--ink);border-radius:18px;padding:6px 6px 6px 16px;max-width:620px;box-shadow:5px 5px 0 var(--sun)}
.search input{flex:1;border:0;background:transparent;font-size:17px;padding:10px 0;min-width:0}
.search input:focus{outline:none}
.search button{border:0;background:var(--cobalt);color:var(--onaccent);border-radius:12px;padding:0 18px;height:46px;font-weight:800}
.spines{display:flex;align-items:flex-end;gap:5px;height:90px;margin-top:34px}
.spines span{flex:1;border-radius:6px 6px 0 0;min-width:10px;transform-origin:bottom;animation:rise .7s cubic-bezier(.2,.9,.3,1.2) both}
@keyframes rise{from{transform:scaleY(0)}}
@media (prefers-reduced-motion:reduce){.spines span{animation:none}}

/* sections */
section{padding:30px 0}
.shead{display:flex;align-items:flex-end;justify-content:space-between;gap:12px;margin-bottom:14px;flex-wrap:wrap}
h2{font-family:var(--display);font-weight:700;font-size:clamp(20px,3.6vw,26px);margin:0;letter-spacing:-.01em}
.sub{color:var(--muted);font-size:14px;margin:4px 0 0}

/* level switch */
.levels{display:grid;grid-template-columns:1fr 1fr;gap:10px;max-width:620px}
.level{border:2.5px solid var(--line);background:var(--surface);border-radius:16px;padding:14px;text-align:left;display:flex;gap:12px;align-items:center}
.level .ic{width:42px;height:42px;border-radius:12px;display:grid;place-items:center;font-size:22px;flex:none}
.level strong{display:block;font-size:16px}
.level small{color:var(--muted);font-size:13px}
.level[aria-pressed="true"]{border-color:var(--ink);box-shadow:4px 4px 0 var(--ink)}
.chips{display:flex;gap:8px;overflow-x:auto;padding:14px 0 6px;scrollbar-width:none}
.chips::-webkit-scrollbar{display:none}
.chip{flex:none;border:2px solid var(--line);background:var(--surface);border-radius:999px;padding:7px 14px;font-weight:700;font-size:14px;white-space:nowrap}
.chip[aria-pressed="true"]{background:var(--c,var(--ink));border-color:var(--c,var(--ink));color:#fff}
.seg{display:inline-flex;background:var(--surface2);border-radius:12px;padding:4px;gap:2px}
.seg button{border:0;background:transparent;border-radius:9px;padding:6px 12px;font-weight:700;font-size:14px;color:var(--muted)}
.seg button[aria-pressed="true"]{background:var(--surface);color:var(--ink);box-shadow:var(--shadow)}

/* demand */
.demand{display:grid;grid-auto-flow:column;grid-auto-columns:minmax(150px,180px);gap:14px;overflow-x:auto;padding-bottom:8px;scrollbar-width:thin}
.dcard{position:relative;background:var(--surface);border-radius:16px;border:1.5px solid var(--line);overflow:hidden;text-align:left;padding:0}
.dcard .img{aspect-ratio:3/4;background:var(--surface2)}
.dcard .img img{width:100%;height:100%;object-fit:cover}
.rank{position:absolute;top:8px;left:8px;font-family:var(--display);font-weight:800;font-size:18px;width:38px;height:38px;border-radius:50%;display:grid;place-items:center;color:#fff;border:3px solid var(--surface)}
.dcard .t{padding:10px 12px 12px}
.dcard .t b{display:block;font-size:14px;line-height:1.3;overflow:hidden;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical}
.dcard .t span{font-size:13px;color:var(--coral);font-weight:800}

/* listing grid */
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(165px,1fr));gap:14px}
.card{background:var(--surface);border:1.5px solid var(--line);border-radius:16px;overflow:hidden;text-align:left;padding:0;display:flex;flex-direction:column}
.card .img{aspect-ratio:4/5;background:var(--surface2);position:relative}
.card .img img{width:100%;height:100%;object-fit:cover}
.badge{position:absolute;top:8px;left:8px;font-size:12px;font-weight:800;padding:3px 9px;border-radius:999px;color:#fff}
.badge.new{background:var(--mint)} .badge.used{background:var(--orange)}
.sold{position:absolute;inset:0;background:rgba(21,20,42,.55);display:grid;place-items:center;color:#fff;font-family:var(--display);font-weight:800;font-size:18px}
.card .t{padding:10px 12px 12px;display:flex;flex-direction:column;gap:2px;flex:1}
.card .title{font-weight:800;font-size:15px;line-height:1.3;overflow:hidden;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical}
.card .author{color:var(--muted);font-size:13px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.card .foot{display:flex;justify-content:space-between;align-items:center;margin-top:auto;padding-top:6px;gap:6px}
.price{font-weight:800;font-size:15px}
.tag{font-size:12px;font-weight:700;background:var(--surface2);border-radius:8px;padding:2px 7px;color:var(--muted);white-space:nowrap}
.noimg{width:100%;height:100%;display:grid;place-items:center;font-size:42px;opacity:.5}

/* requests */
.reqs{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:14px}
.req{display:flex;gap:12px;background:var(--surface);border:1.5px solid var(--line);border-radius:16px;padding:12px}
.req .img{width:84px;flex:none;aspect-ratio:3/4;border-radius:10px;overflow:hidden;background:var(--surface2)}
.req .img img{width:100%;height:100%;object-fit:cover}
.req .body{flex:1;min-width:0;display:flex;flex-direction:column;gap:4px}
.req b{font-size:15px;line-height:1.3}
.req .meta{font-size:13px;color:var(--muted)}
.req .acts{display:flex;gap:6px;flex-wrap:wrap;margin-top:auto}
.sbtn{border:1.5px solid var(--line);background:var(--surface);border-radius:10px;padding:6px 10px;font-weight:700;font-size:13px;text-decoration:none;color:var(--ink);display:inline-flex;align-items:center;gap:4px}
.sbtn.on{background:var(--coral);border-color:var(--coral);color:#fff}
.sbtn.go{background:var(--mint);border-color:var(--mint);color:#fff}

.empty{border:2px dashed var(--line);border-radius:16px;padding:26px;text-align:center;color:var(--muted)}
.empty button{margin-top:10px}

/* FAB */
.fab{position:fixed;right:16px;bottom:calc(16px + env(safe-area-inset-bottom,0px));z-index:8;display:flex;flex-direction:column;gap:10px;align-items:flex-end}
.fab button{border:0;border-radius:16px;height:52px;padding:0 18px;font-weight:800;font-size:15px;display:flex;align-items:center;gap:8px;box-shadow:0 6px 20px rgba(31,29,61,.25)}
.fab .main{background:var(--coral);color:#fff}
.fab .alt{background:var(--sun);color:#1F1D3D;height:44px;font-size:14px}

/* modal */
dialog{border:0;padding:0;background:transparent;max-width:100%;max-height:100%;width:100%;height:100%;margin:0}
dialog::backdrop{background:rgba(21,20,42,.55)}
.sheet{background:var(--surface);color:var(--ink);width:min(560px,100%);max-height:calc(100% - 24px);overflow:auto;margin:auto;border-radius:22px;padding:22px;position:absolute;left:0;right:0;top:50%;transform:translateY(-50%)}
@media (max-width:600px){.sheet{top:auto;bottom:0;transform:none;border-radius:22px 22px 0 0;max-height:92%;padding-bottom:calc(22px + env(safe-area-inset-bottom,0px))}}
.sheet h3{font-family:var(--display);font-size:21px;margin:0 0 4px;padding-right:40px}
.x{position:absolute;top:14px;right:14px;width:38px;height:38px;border-radius:50%;border:0;background:var(--surface2);font-size:20px;line-height:1}
.field{display:flex;flex-direction:column;gap:5px;margin-top:14px}
.field label{font-weight:700;font-size:14px}
.field input,.field select,.field textarea{border:2px solid var(--line);background:var(--bg);border-radius:12px;padding:11px 12px;font-size:16px;width:100%}
.field textarea{min-height:90px;resize:vertical}
.field input:focus,.field select:focus,.field textarea:focus{outline:none;border-color:var(--cobalt)}
.row2{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.opts{display:flex;gap:8px;flex-wrap:wrap}
.opt{border:2px solid var(--line);background:var(--bg);border-radius:12px;padding:9px 14px;font-weight:700;font-size:14px}
.opt[aria-pressed="true"]{border-color:var(--ink);background:var(--ink);color:var(--bg)}
.drop{border:2.5px dashed var(--line);border-radius:14px;padding:16px;text-align:center;color:var(--muted);font-weight:600;cursor:pointer;display:block}
.thumbs{display:flex;gap:8px;margin-top:8px;flex-wrap:wrap}
.thumbs div{position:relative;width:72px;height:90px;border-radius:10px;overflow:hidden;background:var(--surface2)}
.thumbs img{width:100%;height:100%;object-fit:cover}
.thumbs button{position:absolute;top:3px;right:3px;width:22px;height:22px;border-radius:50%;border:0;background:rgba(0,0,0,.6);color:#fff;font-size:13px;line-height:1}
.submit{width:100%;margin-top:20px;border:0;background:var(--cobalt);color:#fff;border-radius:14px;height:52px;font-weight:800;font-size:16px}
.submit:disabled{opacity:.6}
.err{color:var(--coral);font-weight:700;font-size:14px;margin-top:10px;min-height:1px}
.hint{color:var(--muted);font-size:13px}
.gallery{display:flex;gap:8px;overflow-x:auto;scroll-snap-type:x mandatory;margin:14px -4px 0;padding:0 4px}
.gallery img{height:300px;width:auto;max-width:85%;border-radius:14px;object-fit:cover;scroll-snap-align:start;flex:none}
.facts{display:grid;grid-template-columns:auto 1fr;gap:6px 14px;margin:16px 0;font-size:15px}
.facts dt{color:var(--muted)} .facts dd{margin:0;font-weight:700}
.callbar{display:flex;gap:10px;margin-top:16px}
.callbar a,.callbar button{flex:1;height:50px;border-radius:14px;display:flex;align-items:center;justify-content:center;font-weight:800;text-decoration:none;border:0}
.call{background:var(--mint);color:#fff}
.smsb{background:var(--surface2);color:var(--ink)}
.danger{background:transparent;border:2px solid var(--coral)!important;color:var(--coral)}
#qrbox{display:grid;place-items:center;background:#fff;padding:18px;border-radius:18px;margin:16px auto;width:max-content;border:3px solid var(--ink)}
#qrbox img,#qrbox canvas{width:220px;height:220px}
.toast{position:fixed;left:50%;bottom:calc(90px + env(safe-area-inset-bottom,0px));transform:translateX(-50%);background:var(--ink);color:var(--bg);padding:10px 18px;border-radius:12px;font-weight:700;z-index:50;opacity:0;transition:opacity .2s;pointer-events:none;max-width:90%}
.toast.show{opacity:1}
footer{padding:40px 0 120px;color:var(--muted);font-size:13px;text-align:center}
</style>
</head>
<body>
<header>
  <div class="wrap bar">
    <a class="logo" href="#top" aria-label="НомСолио нүүр">
      <i aria-hidden="true"><b style="height:16px;background:var(--coral)"></b><b style="height:24px;background:var(--cobalt)"></b><b style="height:20px;background:var(--sun)"></b><b style="height:26px;background:var(--mint)"></b></i>
      НомСолио
    </a>
    <button class="hbtn" id="qrBtn" aria-label="QR код">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="3" width="7" height="7" rx="1"/><rect x="14" y="3" width="7" height="7" rx="1"/><rect x="3" y="14" width="7" height="7" rx="1"/><path d="M14 14h3v3h-3zM20 14v.01M14 20h.01M17 20h4v-3"/></svg>QR
    </button>
    <button class="hbtn primary" id="authBtn">Нэвтрэх</button>
  </div>
</header>

<main id="top">
  <div class="hero">
    <div class="wrap">
      <h1>Өнгөрсөн жилийн номоо дараагийн сурагчид өг.</h1>
      <p>Дунд сургууль, их сургуулийн сурах бичгийг зарах, худалдаж авах, солилцох газар.</p>
      <form class="search" id="searchForm" role="search">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" aria-hidden="true"><circle cx="11" cy="11" r="7"/><path d="m20 20-4-4"/></svg>
        <input id="q" type="search" placeholder="Номын нэр эсвэл зохиогч" aria-label="Номын нэр эсвэл зохиогчоор хайх" autocomplete="off">
        <button type="submit">Хайх</button>
      </form>
      <div class="spines" id="spines" aria-hidden="true"></div>
    </div>
  </div>

  <section id="demandSec">
    <div class="wrap">
      <div class="shead"><div><h2>Энэ сард хамгийн их хайгдсан</h2><p class="sub">Сүүлийн 30 хоногт олон хүн хайсан номнууд</p></div></div>
      <div id="demand"></div>
    </div>
  </section>

  <section id="browse">
    <div class="wrap">
      <div class="levels" role="group" aria-label="Түвшин">
        <button class="level" data-level="school" aria-pressed="true"><span class="ic" style="background:#FFE7A8">🎒</span><span><strong>Дунд сургууль</strong><small>Ангиар нь</small></span></button>
        <button class="level" data-level="uni" aria-pressed="false"><span class="ic" style="background:#D9E0FF">🎓</span><span><strong>Их сургууль</strong><small>Мэргэжлээр нь</small></span></button>
      </div>
      <div class="chips" id="chips" role="group" aria-label="Анги эсвэл мэргэжил"></div>
      <div class="shead" style="margin-top:10px">
        <div><h2 id="listTitle">Зарууд</h2><p class="sub" id="listCount"></p></div>
        <div class="seg" role="group" aria-label="Төлөв">
          <button data-cond="all" aria-pressed="true">Бүгд</button>
          <button data-cond="new" aria-pressed="false">Шинэ</button>
          <button data-cond="used" aria-pressed="false">Хуучин</button>
        </div>
      </div>
      <div id="listings"></div>
    </div>
  </section>

  <section id="reqSec">
    <div class="wrap">
      <div class="shead">
        <div><h2>Ийм ном хайж байна</h2><p class="sub">Танд байгаа бол эзэнд нь залгаарай</p></div>
        <button class="hbtn" id="askBtn2">+ Ном асуух</button>
      </div>
      <div id="requests"></div>
    </div>
  </section>
</main>

<footer class="wrap">НомСолио · Сурах бичгээ дахин ашиглая</footer>

<div class="fab">
  <button class="alt" id="askBtn">🔍 Ном асуух</button>
  <button class="main" id="sellBtn">＋ Зар оруулах</button>
</div>

<dialog id="dlg"><div class="sheet" id="sheet"></div></dialog>
<div class="toast" id="toast" role="status" aria-live="polite"></div>

<script>
const SITE_URL_DEFAULT = "https://claude.ai/artifact/UDYZPxY7dAYXsiBcrxPwJh";
const GRADES = Array.from({length:12},(_,i)=>String(i+1));
const MAJORS = ["Мэдээлэл технологи","Инженерчлэл","Анагаах ухаан","Эдийн засаг","Бизнес удирдлага","Хууль зүй","Багшлах ухаан","Гадаад хэл","Байгалийн ухаан","Нийгмийн ухаан","Урлаг, дизайн","Бусад"];
const PALETTE = ["#FF5A6E","#3B5BFD","#16BF9E","#8E5CF7","#FF8A3D","#E0A800"];
const S = {db:null,user:null,assets:null,dl:null,uid:null,profile:null,listings:[],requests:[],level:"school",sub:"all",cond:"all",q:"",ready:false,canWrite:true};

const $ = s => document.querySelector(s);
const esc = s => String(s ?? "").replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));
const norm = s => String(s||"").toLowerCase().replace(/\s+/g," ").trim();
const img = id => "/_blob/" + encodeURIComponent(id);
const fmtPrice = n => Number(n).toLocaleString("mn-MN") + "₮";
const ago = t => { const d = Math.floor((Date.now()-t)/86400000); return d<=0?"Өнөөдөр":d===1?"Өчигдөр":d+" хоногийн өмнө"; };
function toast(m){const t=$("#toast");t.textContent=m;t.classList.add("show");clearTimeout(toast._t);toast._t=setTimeout(()=>t.classList.remove("show"),2600)}
const subLabel = (lvl,sub) => lvl==="school" ? sub+"-р анги" : sub;
const imgTag = (id,alt) => id ? <img src="${img(id)}" alt="${esc(alt)}" loading="lazy" onerror="this.replaceWith(Object.assign(document.createElement('div'),{className:'noimg',textContent:'📘'}))"> : <div class="noimg">📘</div>;

/* hero spines */
(function(){const el=$("#spines");const n=window.innerWidth<600?18:34;let h="";for(let i=0;i<n;i++){const c=PALETTE[i%PALETTE.length];h+=`<span style="height:${40+((i*37)%55)}%;background:${c};animation-delay:${i*25}ms"></span>`}el.innerHTML=h})();

/* chips */
function renderChips(){
  const items = S.level==="school"?GRADES:MAJORS;
  $("#chips").innerHTML = <button class="chip" data-sub="all" aria-pressed="${S.sub==="all"}">Бүгд</button> +
    items.map((v,i)=>`<button class="chip" data-sub="${esc(v)}" style="--c:${PALETTE[i%PALETTE.length]}" aria-pressed="${S.sub===v}">${esc(subLabel(S.level,v))}</button>`).join("");
}
document.querySelectorAll(".level").forEach(b=>b.onclick=()=>{S.level=b.dataset.level;S.sub="all";document.querySelectorAll(".level").forEach(x=>x.setAttribute("aria-pressed",x===b));renderChips();renderListings()});
$("#chips").onclick=e=>{const b=e.target.closest(".chip");if(!b)return;S.sub=b.dataset.sub;renderChips();renderListings()};
document.querySelectorAll(".seg button").forEach(b=>b.onclick=()=>{S.cond=b.dataset.cond;document.querySelectorAll(".seg button").forEach(x=>x.setAttribute("aria-pressed",x===b));renderListings()});
$("#searchForm").onsubmit=e=>{e.preventDefault();S.q=$("#q").value;renderListings();renderRequests();$("#browse").scrollIntoView({behavior:"smooth"})};
$("#q").oninput=()=>{S.q=$("#q").value;renderListings();renderRequests()};

function matchQ(o){const q=norm(S.q);if(!q)return true;return norm(o.title).includes(q)||norm(o.author).includes(q)}

/* listings */
function renderListings(){
  const el=$("#listings");
  if(!S.ready){el.innerHTML=`<div class="empty">Ачаалж байна…</div>`;return}
  const list=S.listings.filter(l=>l.level===S.level&&(S.sub==="all"||l.sub===S.sub)&&(S.cond==="all"||l.condition===S.cond)&&matchQ(l));
  $("#listTitle").textContent = S.q ? "${S.q}" хайлтын үр дүн : (S.sub==="all"?(S.level==="school"?"Дунд сургуулийн номнууд":"Их сургуулийн номнууд"):subLabel(S.level,S.sub));
  $("#listCount").textContent = list.length ? list.length+" зар" : "";
  if(!list.length){el.innerHTML=`<div class="empty">${S.q?"Энэ нэр, зохиогчтой ном одоогоор алга. Бусдаас асуугаад үзээрэй.":"Энд одоогоор зар алга. Эхний зарыг та оруулаарай."}<br><button class="hbtn primary" style="margin:12px auto 0" onclick="${S.q?"openAsk()":"openSell()"}">${S.q?"Ном асуух":"Зар оруулах"}</button></div>`;return}
  el.innerHTML=`<div class="grid">${list.map(l=>`
    <button class="card" data-id="${esc(l.id)}">
      <div class="img">${imgTag((l.images||[])[0],l.title)}<span class="badge ${l.condition==="new"?"new":"used"}">${l.condition==="new"?"Шинэ":"Хуучин"}</span>${l.sold?`<div class="sold">Зарагдсан</div>`:""}</div>
      <div class="t"><span class="title">${esc(l.title)}</span><span class="author">${esc(l.author||"Зохиогч тодорхойгүй")}</span>
      <div class="foot"><span class="price">${l.deal==="exchange"?"Солино":l.deal==="free"?"Үнэгүй":fmtPrice(l.price||0)}</span><span class="tag">${esc(subLabel(l.level,l.sub))}</span></div></div>
    </button>`).join("")}</div>`;
}
$("#listings").onclick=e=>{const c=e.target.closest(".card");if(c)openDetail(c.dataset.id)};

/* demand */
function renderDemand(){
  const el=$("#demand");
  if(!S.ready){el.innerHTML=`<div class="empty">Ачаалж байна…</div>`;return}
  const since=Date.now()-30*86400000, groups={};
  S.requests.filter(r=>r.createdAt>=since).forEach(r=>{
    const k=norm(r.title); if(!k)return;
    const g=groups[k]||(groups[k]={title:r.title,author:r.author,image:null,people:new Set(),reqId:r.id});
    g.people.add(r.ownerId);(r.wanters||[]).forEach(w=>g.people.add(w));
    if(!g.image&&r.image)g.image=r.image;
  });
  const top=Object.values(groups).sort((a,b)=>b.people.size-a.people.size).slice(0,10);
  if(!top.length){el.innerHTML=`<div class="empty">Энэ сард хайгдсан ном алга. Хэрэгтэй номоо асуувал энд гарч ирнэ.<br><button class="hbtn primary" style="margin:12px auto 0" onclick="openAsk()">Ном асуух</button></div>`;return}
  el.innerHTML=`<div class="demand">${top.map((g,i)=>`
    <button class="dcard" data-q="${esc(g.title)}" aria-label="${esc(g.title)}, ${g.people.size} хүн хайж байна">
      <div class="img">${imgTag(g.image,g.title)}</div>
      <span class="rank" style="background:${PALETTE[i%PALETTE.length]}">${i+1}</span>
      <div class="t"><b>${esc(g.title)}</b><span>${g.people.size} хүн хайж байна</span></div>
    </button>`).join("")}</div>`;
}
$("#demand").onclick=e=>{const c=e.target.closest(".dcard");if(!c)return;$("#q").value=c.dataset.q;S.q=c.dataset.q;renderListings();renderRequests();$("#browse").scrollIntoView({behavior:"smooth"})};

/* requests */
function renderRequests(){
  const el=$("#requests");
  if(!S.ready){el.innerHTML=`<div class="empty">Ачаалж байна…</div>`;return}
  const list=S.requests.filter(r=>!r.found&&matchQ(r));
  if(!list.length){el.innerHTML=`<div class="empty">Хайж буй ном одоогоор алга. Номынхоо зургийг оруулаад бүх хэрэглэгчдээс асуугаарай.</div>`;return}
  el.innerHTML=`<div class="reqs">${list.map(r=>{
    const mine=S.uid&&r.ownerId===S.uid, me2=S.uid&&(r.wanters||[]).includes(S.uid), n=1+(r.wanters||[]).length;
    return `<div class="req">
      <div class="img">${imgTag(r.image,r.title)}</div>
      <div class="body"><b>${esc(r.title)}</b>
        <span class="meta">${esc(r.author||"")}${r.author?" · ":""}${r.level?esc(subLabel(r.level,r.sub)):""}</span>
        ${r.note?`<span class="meta">${esc(r.note)}</span>`:""}
        <span class="meta" style="color:var(--coral);font-weight:800">${n} хүн хайж байна · ${ago(r.createdAt)}</span>
        <div class="acts">
          ${mine?`<button class="sbtn go" data-act="found" data-id="${esc(r.id)}">✓ Оллоо</button><button class="sbtn" data-act="delreq" data-id="${esc(r.id)}">Устгах</button>`
          :`<a class="sbtn go" href="tel:${esc(r.phone)}">📞 Надад байна</a><button class="sbtn ${me2?"on":""}" data-act="want" data-id="${esc(r.id)}">${me2?"✓ Надад бас хэрэгтэй":"Надад бас хэрэгтэй"}</button>`}
        </div></div></div>`}).join("")}</div>`;
}
$("#requests").onclick=async e=>{
  const b=e.target.closest("button[data-act]");if(!b)return;
  const r=S.requests.find(x=>x.id===b.dataset.id);if(!r)return;
  if(!(await requireLogin()))return;
  const ref=S.db.collection("requests").doc(r.id);
  try{
    if(b.dataset.act==="want"){const w=new Set(r.wanters||[]);w.has(S.uid)?w.delete(S.uid):w.add(S.uid);await ref.update({wanters:[...w]})}
    if(b.dataset.act==="found"){await ref.update({found:true});toast("Баяр хүргэе! Хайлтаас хасагдлаа.")}
    if(b.dataset.act==="delreq"){if(confirm("Энэ асуултыг устгах уу?")){await ref.delete();toast("Устгагдлаа")}}
  }catch(err){toast(writeErr(err))}
};

/* dialog helpers */
const dlg=$("#dlg");
function openSheet(html){$("#sheet").innerHTML=`<button class="x" aria-label="Хаах" onclick="closeSheet()">×</button>`+html;if(!dlg.open)dlg.showModal()}
function closeSheet(){dlg.close()}
dlg.addEventListener("click",e=>{if(e.target===dlg)closeSheet()});
function writeErr(e){return e&&e.code==="quota_exceeded"?"Хадгалах багтаамж дүүрсэн байна.":e&&e.code==="invalid_argument"?"Танд бичих эрх алга байна.":"Хадгалж чадсангүй. Дахин оролдоно уу."}

/* auth */
function normPhone(v){let d=String(v).replace(/\D/g,"");if(d.length===11&&d.startsWith("976"))d=d.slice(3);return d}
function renderAuthBtn(){const b=$("#authBtn");b.textContent=S.profile?("📱 "+S.profile.phone):"Нэвтрэх"}
$("#authBtn").onclick=()=>S.profile?openProfile():openLogin();
let afterLogin=null;
async function requireLogin(next){
  if(!S.db||!S.uid){toast("Нэвтрэх боломжгүй байна. Хуудсаа claude.ai дээр нэвтэрч нээнэ үү.");return false}
  if(S.profile)return true;
  afterLogin=next||null;openLogin();return false;
}
function openLogin(){
  if(!S.db||!S.uid){toast("Нэвтрэх боломжгүй байна. Хуудсаа claude.ai дээр нэвтэрч нээнэ үү.");return}
  openSheet(`<h3>Утасны дугаараар нэвтрэх</h3><p class="hint">Таны дугаарыг зар болон асуултан дээр харуулж, худалдан авагчид шууд залгана.</p>
    <form id="loginF">
      <div class="field"><label for="ph">Утасны дугаар</label><input id="ph" type="tel" inputmode="numeric" placeholder="9911 2233" autocomplete="tel" required></div>
      <div class="field"><label for="nm">Нэр</label><input id="nm" type="text" placeholder="Болд" autocomplete="given-name" required maxlength="40"></div>
      <div class="err" id="lerr"></div>
      <button class="submit" type="submit">Нэвтрэх</button></form>`);
  $("#ph").focus();
  $("#loginF").onsubmit=async e=>{
    e.preventDefault();const phone=normPhone($("#ph").value),name=$("#nm").value.trim();
    if(phone.length!==8){$("#lerr").textContent="8 оронтой утасны дугаар оруулна уу.";return}
    if(!name){$("#lerr").textContent="Нэрээ оруулна уу.";return}
    try{await S.db.doc(data/users/${S.uid}/profile).set({phone,name,updatedAt:Date.now()});S.profile={phone,name};renderAuthBtn();closeSheet();toast("Тавтай морил, "+name+"!");const f=afterLogin;afterLogin=null;if(f)f()}
    catch(err){$("#lerr").textContent=writeErr(err)}
  };
}
function openProfile(){
  const mine=S.listings.filter(l=>l.ownerId===S.uid);
  openSheet(`<h3>${esc(S.profile.name)}</h3><p class="hint">📱 ${esc(S.profile.phone)}</p>
    <h4 style="margin:18px 0 8px">Миний зарууд (${mine.length})</h4>
    ${mine.length?mine.map(l=>`<button class="sbtn" style="width:100%;justify-content:space-between;margin-bottom:6px;padding:10px 12px" onclick="openDetail('${esc(l.id)}')"><span>${esc(l.title)}</span><span class="hint">${l.sold?"Зарагдсан":"Идэвхтэй"}</span></button>`).join(""):`<p class="hint">Одоогоор зар алга.</p>`}
    <div class="callbar"><button class="smsb" onclick="closeSheet();openLogin()">Дугаар солих</button><button class="danger" onclick="logout()">Гарах</button></div>`);
}
async function logout(){try{await S.db.doc(data/users/${S.uid}/profile).delete()}catch(e){}S.profile=null;renderAuthBtn();closeSheet();toast("Гарлаа")}

/* image upload */
async function compress(file){
  try{const bm=await createImageBitmap(file);const r=Math.min(1,1280/Math.max(bm.width,bm.height));const c=document.createElement("canvas");c.width=Math.round(bm.width*r);c.height=Math.round(bm.height*r);c.getContext("2d").drawImage(bm,0,0,c.width,c.height);return await new Promise(res=>c.toBlob(b=>res(b||file),"image/jpeg",.82))}catch(e){return file}
}
function imagePicker(max,wrapId){
  const files=[];const wrap=$("#"+wrapId);
  const input=wrap.querySelector("input[type=file]"),thumbs=wrap.querySelector(".thumbs");
  const draw=()=>{thumbs.innerHTML=files.map((f,i)=>`<div><img src="${f.url}" alt=""><button type="button" data-i="${i}" aria-label="Зураг хасах">×</button></div>`).join("");wrap.querySelector(".drop").style.display=files.length>=max?"none":"block"};
  input.onchange=async()=>{for(const f of input.files){if(files.length>=max)break;if(!f.type.startsWith("image/"))continue;const b=await compress(f);files.push({blob:b,url:URL.createObjectURL(b)})}input.value="";draw()};
  thumbs.onclick=e=>{const b=e.target.closest("button");if(!b)return;files.splice(+b.dataset.i,1);draw()};
  return files;
}
async function uploadAll(files){
  if(!files.length)return[];
  if(!S.assets)throw{code:"no_assets"};
  const ids=[];for(const f of files){const r=await S.assets.upload(f.blob);ids.push(r.id)}return ids;
}
function uploadErr(e){return e&&e.code==="no_assets"?"Таны эрхээр зураг оруулах боломжгүй байна.":e&&e.code==="quota_exceeded"?"Зургийн багтаамж дүүрсэн байна.":e&&e.code==="too_large"?"Зураг хэт том байна.":null}
const levelFields=(prefix,lvl)=>`
  <div class="field"><label>Түвшин</label><div class="opts" id="${prefix}Lvl">
    <button type="button" class="opt" data-v="school" aria-pressed="${lvl==="school"}">🎒 Дунд сургууль</button>
    <button type="button" class="opt" data-v="uni" aria-pressed="${lvl==="uni"}">🎓 Их сургууль</button></div></div>
  <div class="field"><label for="${prefix}Sub" id="${prefix}SubL">${lvl==="school"?"Анги":"Мэргэжил"}</label><select id="${prefix}Sub"></select></div>`;
function wireLevel(prefix,state){
  const fill=()=>{$("#"+prefix+"SubL").textContent=state.level==="school"?"Анги":"Мэргэжил";$("#"+prefix+"Sub").innerHTML=(state.level==="school"?GRADES:MAJORS).map(v=>`<option value="${esc(v)}">${esc(subLabel(state.level,v))}</option>`).join("")};
  wireOpts(prefix+"Lvl",v=>{state.level=v;fill()});fill();
}
function wireOpts(id,cb){const g=$("#"+id);g.onclick=e=>{const b=e.target.closest(".opt");if(!b)return;g.querySelectorAll(".opt").forEach(x=>x.setAttribute("aria-pressed",x===b));cb(b.dataset.v)}}

/* sell */
async function openSell(){
  if(!(await requireLogin(openSell)))return;
  const st={level:S.level,condition:"used",deal:"sell"};
  openSheet(`<h3>Номын зар оруулах</h3>
    <form id="sellF">
      <div class="field" id="sellImgs"><label>Номын зураг (3 хүртэл)</label>
        <label class="drop">📷 Зураг сонгох<input type="file" accept="image/*" multiple hidden></label><div class="thumbs"></div></div>
      <div class="field"><label for="sT">Номын нэр</label><input id="sT" required maxlength="120" placeholder="Математик 10"></div>
      <div class="field"><label for="sA">Зохиогч</label><input id="sA" maxlength="80" placeholder="Б. Батбаяр"></div>
      ${levelFields("s",st.level)}
      <div class="field"><label>Төлөв</label><div class="opts" id="sCond">
        <button type="button" class="opt" data-v="new" aria-pressed="false">✨ Шинэ</button>
        <button type="button" class="opt" data-v="used" aria-pressed="true">📚 Хуучин</button></div></div>
      <div class="field"><label>Зарын төрөл</label><div class="opts" id="sDeal">
        <button type="button" class="opt" data-v="sell" aria-pressed="true">Зарна</button>
        <button type="button" class="opt" data-v="exchange" aria-pressed="false">Солино</button>
        <button type="button" class="opt" data-v="free" aria-pressed="false">Үнэгүй өгнө</button></div></div>
      <div class="field" id="priceF"><label for="sP">Үнэ (₮)</label><input id="sP" type="number" inputmode="numeric" min="0" step="500" placeholder="15000"></div>
      <div class="field"><label for="sD">Дэлгэрэнгүй</label><textarea id="sD" maxlength="1000" placeholder="Хэвлэлийн он, тэмдэглэл хийсэн эсэх, хаана уулзах гэх мэт"></textarea></div>
      <div class="err" id="serr"></div>
      <button class="submit" type="submit" id="sBtn">Зар нийтлэх</button>
    </form>`);
  const files=imagePicker(3,"sellImgs");
  wireLevel("s",st);
  wireOpts("sCond",v=>st.condition=v);
  wireOpts("sDeal",v=>{st.deal=v;$("#priceF").style.display=v==="sell"?"flex":"none"});
  $("#sellF").onsubmit=async e=>{
    e.preventDefault();const title=$("#sT").value.trim();
    if(!title){$("#serr").textContent="Номын нэрээ оруулна уу.";return}
    if(!files.length){$("#serr").textContent="Дор хаяж нэг зураг оруулна уу.";return}
    const price=Number($("#sP").value||0);
    if(st.deal==="sell"&&!(price>0)){$("#serr").textContent="Үнээ оруулна уу.";return}
    const btn=$("#sBtn");btn.disabled=true;btn.textContent="Хадгалж байна…";
    try{
      const images=await uploadAll(files);
      await S.db.collection("listings").add({title,author:$("#sA").value.trim(),level:st.level,sub:$("#sSub").value,condition:st.condition,deal:st.deal,price:st.deal==="sell"?price:0,description:$("#sD").value.trim(),images,phone:S.profile.phone,sellerName:S.profile.name,ownerId:S.uid,createdAt:Date.now(),sold:false});
      closeSheet();toast("Зар нийтлэгдлээ");
    }catch(err){$("#serr").textContent=uploadErr(err)||writeErr(err);btn.disabled=false;btn.textContent="Зар нийтлэх"}
  };
}

/* ask */
async function openAsk(){
  if(!(await requireLogin(openAsk)))return;
  const st={level:S.level};
  openSheet(`<h3>Хайж буй номоо асуух</h3><p class="hint">Зургийг нь оруулбал бусад хүмүүс хурдан таньж, танд залгана.</p>
    <form id="askF">
      <div class="field" id="askImg"><label>Номын зураг</label>
        <label class="drop">📷 Зураг сонгох<input type="file" accept="image/*" hidden></label><div class="thumbs"></div></div>
      <div class="field"><label for="aT">Номын нэр</label><input id="aT" required maxlength="120" value="${esc(S.q)}"></div>
      <div class="field"><label for="aA">Зохиогч</label><input id="aA" maxlength="80"></div>
      ${levelFields("a",st.level)}
      <div class="field"><label for="aN">Нэмэлт</label><input id="aN" maxlength="200" placeholder="Хуучин байсан ч болно"></div>
      <div class="err" id="aerr"></div>
      <button class="submit" type="submit" id="aBtn">Бүх хэрэглэгчээс асуух</button>
    </form>`);
  const files=imagePicker(1,"askImg");
  wireLevel("a",st);
  $("#askF").onsubmit=async e=>{
    e.preventDefault();const title=$("#aT").value.trim();
    if(!title){$("#aerr").textContent="Номын нэрээ оруулна уу.";return}
    if(!files.length){$("#aerr").textContent="Номын зургаа оруулна уу.";return}
    const btn=$("#aBtn");btn.disabled=true;btn.textContent="Илгээж байна…";
    try{
      const [image]=await uploadAll(files);
      await S.db.collection("requests").add({title,author:$("#aA").value.trim(),level:st.level,sub:$("#aSub").value,note:$("#aN").value.trim(),image,phone:S.profile.phone,name:S.profile.name,ownerId:S.uid,wanters:[],found:false,createdAt:Date.now()});
      closeSheet();toast("Асуулт нийтлэгдлээ");$("#reqSec").scrollIntoView({behavior:"smooth"});
    }catch(err){$("#aerr").textContent=uploadErr(err)||writeErr(err);btn.disabled=false;btn.textContent="Бүх хэрэглэгчээс асуух"}
  };
}
$("#sellBtn").onclick=()=>openSell();
$("#askBtn").onclick=()=>openAsk();
$("#askBtn2").onclick=()=>openAsk();

/* detail */
function openDetail(id){
  const l=S.listings.find(x=>x.id===id);if(!l)return;
  const mine=S.uid&&l.ownerId===S.uid;
  openSheet(`<h3>${esc(l.title)}</h3><p class="hint">${esc(l.author||"Зохиогч тодорхойгүй")}</p>
    <div class="gallery">${(l.images||[]).map(i=>`<img src="${img(i)}" alt="${esc(l.title)}">`).join("")||`<div class="noimg" style="height:200px">📘</div>`}</div>
    <dl class="facts">
      <dt>Үнэ</dt><dd>${l.deal==="exchange"?"Солилцоно":l.deal==="free"?"Үнэгүй өгнө":fmtPrice(l.price||0)}</dd>
      <dt>Төлөв</dt><dd>${l.condition==="new"?"✨ Шинэ":"📚 Хуучин"}</dd>
      <dt>${l.level==="school"?"Анги":"Мэргэжил"}</dt><dd>${esc(subLabel(l.level,l.sub))}</dd>
      <dt>Зарласан</dt><dd>${esc(l.sellerName||"")} · ${ago(l.createdAt)}</dd>
    </dl>
    ${l.description?`<p style="white-space:pre-wrap;margin:0">${esc(l.description)}</p>`:""}
    ${mine?`<div class="callbar"><button class="smsb" id="soldT">${l.sold?"Дахин идэвхжүүлэх":"Зарагдсан гэж тэмдэглэх"}</button><button class="danger" id="delL">Устгах</button></div>`
    :l.sold?`<p class="hint" style="margin-top:16px">Энэ ном зарагдсан байна.</p>`
    :`<div class="callbar"><a class="call" href="tel:${esc(l.phone)}">📞 ${esc(l.phone)}</a><a class="smsb" href="sms:${esc(l.phone)}">💬 Мессеж</a></div>`}`);
  if(mine){
    $("#soldT").onclick=async()=>{try{await S.db.collection("listings").doc(l.id).update({sold:!l.sold});closeSheet();toast(l.sold?"Зар идэвхжлээ":"Зарагдсан гэж тэмдэглэлээ")}catch(e){toast(writeErr(e))}};
    $("#delL").onclick=async()=>{if(!confirm("Энэ зарыг устгах уу?"))return;try{await S.db.collection("listings").doc(l.id).delete();closeSheet();toast("Зар устгагдлаа")}catch(e){toast(writeErr(e))}};
  }
}

/* QR */
$("#qrBtn").onclick=()=>{
  const url=SITE_URL_DEFAULT||location.href;
  openSheet(`<h3>Сайт руу орох QR код</h3><p class="hint">Хэвлээд сургуулийнхаа самбарт наагаарай. Утасны камераар уншуулахад шууд нээгдэнэ.</p>
    <div id="qrbox"></div>
    <div class="field"><label for="qrU">Холбоос</label><input id="qrU" value="${esc(url)}"></div>
    <div class="callbar"><button class="smsb" id="qrRe">Шинэчлэх</button><button class="call" id="qrDl">⬇ Татах</button></div>`);
  const draw=()=>{const b=$("#qrbox");b.innerHTML="";if(typeof QRCode==="undefined"){b.textContent="QR сан ачаалагдсангүй";return}new QRCode(b,{text:$("#qrU").value.trim()||url,width:440,height:440,colorDark:"#1F1D3D",colorLight:"#ffffff",correctLevel:QRCode.CorrectLevel.M})};
  draw();$("#qrRe").onclick=draw;
  $("#qrDl").style.display=S.dl?"flex":"none";
  $("#qrDl").onclick=async()=>{const c=$("#qrbox canvas");if(!c||!S.dl)return;const blob=await new Promise(r=>c.toBlob(r,"image/png"));try{await S.dl.save({filename:"nomsolio-qr.png",data:blob});}catch(e){}};
};

/* boot */
renderChips();renderListings();renderDemand();renderRequests();renderAuthBtn();
(async function boot(){
  const use=n=>window.claude&&window.claude.use?window.claude.use(n).catch(()=>null):Promise.resolve(null);
  const [db,user,assets,dl]=await Promise.all([use("db"),use("user"),use("assets"),use("downloads")]);
  Object.assign(S,{db,user,assets,dl});
  if(user){try{S.uid=await user.id()}catch(e){}}
  if(!db){S.ready=true;$("#listings").innerHTML=`<div class="empty">Зарууд харахын тулд claude.ai дээр нэвтэрч нээнэ үү.</div>`;$("#demand").innerHTML="";$("#requests").innerHTML="";return}
  if(S.uid){try{const p=await db.doc(data/users/${S.uid}/profile).get();if(p.exists)S.profile=p.data()}catch(e){}renderAuthBtn()}
  let gotL=false,gotR=false;const done=()=>{if(gotL&&gotR&&!S.ready){S.ready=true;renderListings();renderDemand();renderRequests()}};
  db.collection("listings").orderBy("createdAt","desc").limit(500).onSnapshot(s=>{S.listings=s.docs.map(d=>({id:d.id,...d.data()}));gotL=true;done();if(S.ready)renderListings()},()=>{gotL=true;done()});
  db.collection("requests").orderBy("createdAt","desc").limit(500).onSnapshot(s=>{S.requests=s.docs.map(d=>({id:d.id,...d.data()}));gotR=true;done();if(S.ready){renderDemand();renderRequests()}},()=>{gotR=true;done()});
})();
</script>
</body>
</html>
