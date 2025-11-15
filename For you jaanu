<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>For You — I'm Sorry</title>
  <style>
    :root{--bg:#0f1022;--card:#121226;--accent:#ff6b9a;--muted:#bdbbdc}
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:Inter,system-ui,Segoe UI,Roboto,'Helvetica Neue',Arial}
    body{background:linear-gradient(180deg,#0b1020 0%, #121226 60%);color:#fff;display:flex;align-items:center;justify-content:center;padding:20px}.container{width:980px;max-width:100%;background:linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.015));border-radius:18px;padding:26px;box-shadow:0 10px 30px rgba(2,6,23,0.6);position:relative;overflow:hidden}

header{display:flex;gap:18px;align-items:center}
.logo{width:64px;height:64px;border-radius:12px;overflow:hidden;flex:0 0 64px;background:linear-gradient(135deg,var(--accent),#ffb3d1);display:flex;align-items:center;justify-content:center;font-weight:700;color:#2b0020}
h1{margin:0;font-size:22px}
p.lead{margin:4px 0 0;color:var(--muted)}

.main{display:grid;grid-template-columns:360px 1fr;gap:22px;margin-top:22px}

.left{background:rgba(255,255,255,0.02);padding:16px;border-radius:12px;min-height:360px;display:flex;flex-direction:column;gap:12px}
.photo-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.photo{background:#111214;height:160px;border-radius:10px;border:2px solid rgba(255,255,255,0.03);display:flex;align-items:center;justify-content:center;overflow:hidden;position:relative}
.photo img{width:100%;height:100%;object-fit:cover}
.upload-btn{display:flex;gap:8px;align-items:center}
.btn{background:linear-gradient(90deg,var(--accent),#ff9ec0);border:none;padding:10px 14px;border-radius:10px;color:#2b0020;font-weight:600;cursor:pointer}
input[type=file]{display:none}
.small{font-size:13px;color:var(--muted)}

.right{padding:18px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.03));min-height:360px;display:flex;flex-direction:column;justify-content:space-between}

.message{font-size:18px;line-height:1.45}
.message strong{color:var(--accent);font-size:20px}

.controls{display:flex;gap:12px;align-items:center}
.heart{font-size:28px;cursor:pointer}

.action-row{display:flex;gap:12px;align-items:center}
.sorry{background:transparent;border:2px solid var(--accent);padding:12px 16px;border-radius:12px;color:var(--accent);font-weight:700;cursor:pointer}
.save{background:#fff;padding:10px 14px;border-radius:12px;color:#2b0020;font-weight:700;border:none;cursor:pointer}

footer{margin-top:14px;color:var(--muted);font-size:13px;display:flex;justify-content:space-between;align-items:center}

/* confetti canvas */
#confetti{position:absolute;left:0;top:0;width:100%;height:100%;pointer-events:none}

/* hearts animation */
.floating-heart{position:absolute;width:48px;height:48px;display:flex;align-items:center;justify-content:center;opacity:0;transform:translateY(20px) scale(.8);transition:all .8s cubic-bezier(.2,.9,.22,1)}
.floating-heart.show{opacity:1;transform:translateY(-30px) scale(1)}

/* responsive */
@media (max-width:880px){.main{grid-template-columns:1fr;}.left{order:2}.right{order:1}}

  </style>
</head>
<body>
  <div class="container" id="app">
    <canvas id="confetti"></canvas>
    <div class="floating-heart" id="floatingHeart" style="right:28px;top:18px">❤️</div><header>
  <div class="logo">U</div>
  <div>
    <h1>For You — I miss your smile</h1>
    <p class="lead">A little page I made to say sorry. Add your pictures below.</p>
  </div>
</header>

<div class="main">
  <div class="left">
    <div class="photo-grid">
      <div class="photo" id="photo1"> <span class="small">Drop or upload photo</span></div>
      <div class="photo" id="photo2"> <span class="small">Drop or upload photo</span></div>
      <div class="photo" id="photo3"> <span class="small">Drop or upload photo</span></div>
      <div class="photo" id="photo4"> <span class="small">Drop or upload photo</span></div>
    </div>

    <div class="upload-btn">
      <label class="btn">Upload photos<input id="uploader" type="file" accept="image/*" multiple></label>
      <div class="small">Or drag & drop images onto any box</div>
    </div>

    <div class="small">Tip: Use pictures that make her laugh or remind her of good times. They’ll appear here instantly.</div>
  </div>

  <div class="right">
    <div>
      <div class="message" id="messageArea">
        <p>Hey <strong>Beautiful</strong>,</p>
        <p>I'm sorry for making you upset. I miss your laugh and your warmth. I made this little page to remind you how special you are to me. Please forgive me — I promise to be better.</p>
        <p style="margin-top:10px">Love, <strong>Your Name</strong></p>
      </div>
    </div>

    <div>
      <div class="action-row">
        <button class="sorry" id="apologyBtn">Say Sorry ❤️</button>
        <button class="save" id="downloadBtn">Download Page</button>
        <button class="btn" id="playMusicBtn">Play a Song</button>
        <input id="musicInput" type="file" accept="audio/*" style="display:none">
      </div>

      <div style="margin-top:12px" class="small">You can personalize the message by clicking the text. Double-click any photo to view full size.</div>
    </div>
  </div>
</div>

<footer>
  <div>Made with ❤️ to make her smile</div>
  <div class="small">Tip: When all looks good, download and open the HTML file in a browser to show her.</div>
</footer>

  </div>  <script>
    // Helpers: drag & drop, uploads
    const photoEls = [1,2,3,4].map(i => document.getElementById('photo'+i));
    const uploader = document.getElementById('uploader');
    const musicInput = document.getElementById('musicInput');
    const playMusicBtn = document.getElementById('playMusicBtn');
    const apologyBtn = document.getElementById('apologyBtn');
    const floatingHeart = document.getElementById('floatingHeart');

    function setImage(el, src){
      el.innerHTML = '';
      const img = document.createElement('img');
      img.src = src;
      el.appendChild(img);
      img.addEventListener('dblclick', ()=>{
        const w = window.open(''); w.document.write(`<img src="${src}" style="max-width:100%;height:auto">`);
      });
    }

    function handleFiles(files){
      const arr = Array.from(files).slice(0,4);
      arr.forEach((file, i)=>{
        const reader = new FileReader();
        reader.onload = e => setImage(photoEls[i], e.target.result);
        reader.readAsDataURL(file);
      });
    }

    uploader.addEventListener('change', e=> handleFiles(e.target.files));

    photoEls.forEach(el=>{
      el.addEventListener('dragover', e=>{e.preventDefault(); el.style.outline='2px dashed rgba(255,255,255,0.06)'});
      el.addEventListener('dragleave', e=>{e.preventDefault(); el.style.outline='none'});
      el.addEventListener('drop', e=>{e.preventDefault(); el.style.outline='none'; if(e.dataTransfer.files) handleFiles(e.dataTransfer.files)});
    });

    // Make message editable
    const messageArea = document.getElementById('messageArea');
    messageArea.contentEditable = true;
    messageArea.addEventListener('input', ()=> localStorage.setItem('messageHTML', messageArea.innerHTML));
    if(localStorage.getItem('messageHTML')) messageArea.innerHTML = localStorage.getItem('messageHTML');

    // Download the page as single HTML
    document.getElementById('downloadBtn').addEventListener('click', ()=>{
      const doc = document.documentElement.outerHTML;
      const blob = new Blob([doc], {type:'text/html'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a'); a.href=url; a.download='for-her.html'; a.click(); URL.revokeObjectURL(url);
    });

    // Play uploaded music
    let audio;
    playMusicBtn.addEventListener('click', ()=> musicInput.click());
    musicInput.addEventListener('change', (e)=>{
      const file = e.target.files[0]; if(!file) return;
      const url = URL.createObjectURL(file);
      if(audio){audio.pause(); URL.revokeObjectURL(audio.src)}
      audio = new Audio(url); audio.loop = true; audio.volume = 0.6; audio.play();
    });

    // Apology button: animate heart and confetti
    apologyBtn.addEventListener('click', ()=>{
      floatingHeart.classList.add('show');
      setTimeout(()=>floatingHeart.classList.remove('show'), 1800);
      launchConfetti();
    });

    // Simple confetti implementation
    const confettiCanvas = document.getElementById('confetti');
    const ctx = confettiCanvas.getContext('2d');
    function resize(){confettiCanvas.width = confettiCanvas.offsetWidth; confettiCanvas.height = confettiCanvas.offsetHeight}
    new ResizeObserver(resize).observe(confettiCanvas); resize();

    function launchConfetti(){
      const pieces = [];
      for(let i=0;i<60;i++) pieces.push({x: Math.random()*confettiCanvas.width, y: -10, vy: 2+Math.random()*5, size:6+Math.random()*8, rot:Math.random()*360, vr: (Math.random()-0.5)*6});
      let t = 0;
      function frame(){
        ctx.clearRect(0,0,confettiCanvas.width,confettiCanvas.height);
        pieces.forEach(p=>{ p.y += p.vy; p.vy += 0.03; p.rot += p.vr; ctx.save(); ctx.translate(p.x,p.y); ctx.rotate(p.rot*Math.PI/180); ctx.fillStyle = ['#ff6b9a','#ffd9e6','#ffd1a9'][Math.floor(Math.random()*3)]; ctx.fillRect(-p.size/2,-p.size/2,p.size,p.size*1.6); ctx.restore(); });
        t++; if(t<160) requestAnimationFrame(frame); else ctx.clearRect(0,0,confettiCanvas.width,confettiCanvas.height);
      }
      frame();
    }

    // Allow user to click any photo to replace from local files
    photoEls.forEach((el, idx)=>{
      el.addEventListener('click', ()=>{
        const f = document.createElement('input'); f.type='file'; f.accept='image/*'; f.onchange = ev => handleFiles(ev.target.files);
        f.click();
      });
    });

    // Allow saving images to localStorage (small images only) — optional
    function saveDisplayedImages(){
      photoEls.forEach((el,i)=>{
        const img = el.querySelector('img'); if(!img) return; localStorage.setItem('photo'+i, img.src);
      });
    }
    setInterval(saveDisplayedImages, 3000);
    // restore images
    [0,1,2,3].forEach(i=>{ const s = localStorage.getItem('photo'+i); if(s) setImage(photoEls[i], s)});

    // Small accessibility: keyboard trigger apology with Enter
    document.addEventListener('keydown', e=>{ if(e.key==='Enter' && (document.activeElement === apologyBtn || document.activeElement === playMusicBtn)) { e.preventDefault(); apologyBtn.click(); } });

  </script></body>
</html>
