<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Naragam Manikanta Raghava — VLSI Design Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Chakra+Petch:wght@400;500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #0a0d13;
    --surface: #11141d;
    --surface-2: #161a26;
    --border: #232838;
    --trace: #3ddbd9;
    --trace-dim: #3ddbd94d;
    --gold: #e8b454;
    --text: #e9edf3;
    --text-muted: #8a92a6;
    --text-faint: #565d70;
  }

  *{ box-sizing:border-box; margin:0; padding:0; }

  html{ scroll-behavior:smooth; }

  body{
    background:var(--bg);
    color:var(--text);
    font-family:'Inter', sans-serif;
    line-height:1.6;
    overflow-x:hidden;
  }

  @media (prefers-reduced-motion: reduce){
    html{ scroll-behavior:auto; }
  }

  #bg-canvas{
    position:fixed;
    top:0; left:0;
    width:100%; height:100%;
    z-index:0;
    pointer-events:none;
  }

  .vignette{
    position:fixed;
    inset:0;
    z-index:1;
    pointer-events:none;
    background:
      radial-gradient(ellipse at 50% 0%, transparent 0%, transparent 35%, var(--bg) 92%),
      linear-gradient(180deg, transparent 0%, transparent 70%, var(--bg) 100%);
  }

  main{
    position:relative;
    z-index:2;
    max-width:840px;
    margin:0 auto;
    padding:0 24px 120px;
  }

  /* ---------- Hero ---------- */
  .hero{
    min-height:92vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    padding-top:40px;
  }

  .eyebrow{
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    letter-spacing:0.12em;
    color:var(--trace);
    text-transform:uppercase;
    margin-bottom:20px;
    display:flex;
    align-items:center;
    gap:10px;
  }

  .eyebrow::before{
    content:"";
    width:8px; height:8px;
    background:var(--trace);
    border-radius:50%;
    box-shadow:0 0 12px 2px var(--trace);
    animation:pulse 2.4s ease-in-out infinite;
  }

  @keyframes pulse{
    0%,100%{ opacity:1; }
    50%{ opacity:0.35; }
  }

  h1.name{
    font-family:'Chakra Petch', sans-serif;
    font-weight:700;
    font-size:clamp(38px, 6.4vw, 68px);
    line-height:1.04;
    letter-spacing:-0.01em;
    max-width:11ch;
  }

  .role{
    font-family:'Chakra Petch', sans-serif;
    font-weight:500;
    font-size:clamp(18px, 2.4vw, 24px);
    color:var(--trace);
    margin-top:14px;
  }

  .hero-meta{
    display:flex;
    flex-wrap:wrap;
    gap:10px 28px;
    margin-top:32px;
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    color:var(--text-muted);
  }

  .hero-meta span b{ color:var(--text); font-weight:500; }

  .scroll-cue{
    margin-top:56px;
    font-family:'JetBrains Mono', monospace;
    font-size:12px;
    color:var(--text-faint);
    letter-spacing:0.08em;
    display:flex;
    align-items:center;
    gap:10px;
  }

  .scroll-cue .line{
    width:28px; height:1px;
    background:var(--text-faint);
    animation:extend 2s ease-in-out infinite;
    transform-origin:left;
  }

  @keyframes extend{
    0%,100%{ transform:scaleX(1); }
    50%{ transform:scaleX(1.6); }
  }

  /* ---------- Section shell ---------- */
  section{
    padding-top:96px;
  }

  .sec-head{
    display:flex;
    align-items:baseline;
    gap:14px;
    margin-bottom:28px;
  }

  .sec-num{
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    color:var(--trace-dim);
    color:var(--trace);
    opacity:0.55;
  }

  .sec-title{
    font-family:'Chakra Petch', sans-serif;
    font-weight:600;
    font-size:26px;
    letter-spacing:-0.01em;
  }

  /* ---------- About / yaml card ---------- */
  .yaml-card{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:10px;
    overflow:hidden;
  }

  .yaml-card .titlebar{
    display:flex;
    align-items:center;
    gap:8px;
    padding:12px 16px;
    border-bottom:1px solid var(--border);
    background:var(--surface-2);
  }

  .titlebar .dot{ width:9px; height:9px; border-radius:50%; }
  .titlebar .dot:nth-child(1){ background:#ff5f56; }
  .titlebar .dot:nth-child(2){ background:#ffbd2e; }
  .titlebar .dot:nth-child(3){ background:#27c93f; }
  .titlebar .fname{
    margin-left:8px;
    font-family:'JetBrains Mono', monospace;
    font-size:12px;
    color:var(--text-faint);
  }

  .yaml-body{
    padding:22px 24px;
    font-family:'JetBrains Mono', monospace;
    font-size:13.5px;
    overflow-x:auto;
  }

  .yaml-body .row{ white-space:pre; }
  .yaml-key{ color:var(--trace); }
  .yaml-str{ color:var(--gold); }
  .yaml-punct{ color:var(--text-faint); }

  /* ---------- Currently Building ---------- */
  .build-card{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:10px;
    padding:28px 26px;
  }

  .build-card h3{
    font-family:'Chakra Petch', sans-serif;
    font-size:18px;
    font-weight:600;
    margin-bottom:6px;
  }

  .build-card p{
    color:var(--text-muted);
    font-size:14.5px;
    margin-bottom:20px;
  }

  .flow{
    display:flex;
    flex-wrap:wrap;
    align-items:center;
    gap:0;
    margin-bottom:22px;
    font-family:'JetBrains Mono', monospace;
    font-size:12.5px;
  }

  .flow .step{
    padding:7px 12px;
    border:1px solid var(--border);
    border-radius:6px;
    color:var(--text-muted);
    background:var(--surface-2);
  }

  .flow .step.done{
    color:var(--trace);
    border-color:var(--trace-dim);
  }

  .flow .step.active{
    color:var(--gold);
    border-color:#e8b45466;
    box-shadow:0 0 0 1px #e8b45422;
  }

  .flow .arrow{
    color:var(--text-faint);
    padding:0 6px;
  }

  .checklist{
    display:flex;
    flex-direction:column;
    gap:10px;
  }

  .checklist .item{
    display:flex;
    align-items:center;
    gap:10px;
    font-size:14px;
  }

  .checklist .mark{
    font-family:'JetBrains Mono', monospace;
    font-size:12px;
    width:16px;
  }

  .checklist .item.done .mark{ color:var(--trace); }
  .checklist .item.progress .mark{ color:var(--gold); }
  .checklist .item.progress span{ color:var(--text); }
  .checklist .item span{ color:var(--text-muted); }

  /* ---------- Highlight ---------- */
  .highlight{
    position:relative;
    background:linear-gradient(135deg, #1a1610 0%, var(--surface) 55%);
    border:1px solid #e8b45440;
    border-radius:10px;
    padding:32px 30px;
  }

  .highlight .medal{
    font-size:26px;
    margin-bottom:14px;
    display:block;
  }

  .highlight p{
    font-family:'Chakra Petch', sans-serif;
    font-size:19px;
    font-weight:500;
    line-height:1.5;
    color:var(--text);
  }

  .highlight .num{
    color:var(--gold);
  }

  .highlight .proj{
    display:block;
    margin-top:10px;
    font-size:16px;
    font-weight:400;
    color:var(--text-muted);
    font-family:'Inter', sans-serif;
  }

  /* ---------- Projects ---------- */
  .projects{
    display:flex;
    flex-direction:column;
    gap:16px;
  }

  .proj-card{
    display:block;
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:10px;
    padding:24px 26px;
    text-decoration:none;
    color:inherit;
    transition:border-color 0.25s ease, transform 0.25s ease, background 0.25s ease;
  }

  .proj-card:hover{
    border-color:var(--trace-dim);
    background:var(--surface-2);
    transform:translateY(-2px);
  }

  .proj-card:focus-visible{
    outline:2px solid var(--trace);
    outline-offset:3px;
  }

  .proj-top{
    display:flex;
    align-items:flex-start;
    justify-content:space-between;
    gap:16px;
    margin-bottom:10px;
  }

  .proj-title{
    font-family:'Chakra Petch', sans-serif;
    font-size:18px;
    font-weight:600;
  }

  .proj-arrow{
    color:var(--text-faint);
    font-size:18px;
    flex-shrink:0;
    transition:transform 0.25s ease, color 0.25s ease;
  }

  .proj-card:hover .proj-arrow{
    transform:translate(3px,-3px);
    color:var(--trace);
  }

  .proj-desc{
    color:var(--text-muted);
    font-size:14.5px;
    margin-bottom:16px;
    max-width:56ch;
  }

  .tags{
    display:flex;
    flex-wrap:wrap;
    gap:8px;
  }

  .tag{
    font-family:'JetBrains Mono', monospace;
    font-size:11.5px;
    color:var(--trace);
    background:#3ddbd914;
    border:1px solid #3ddbd930;
    padding:4px 10px;
    border-radius:5px;
  }

  /* ---------- Stack ---------- */
  .stack-grid{
    display:flex;
    flex-wrap:wrap;
    gap:10px;
  }

  .stack-chip{
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    color:var(--text-muted);
    border:1px solid var(--border);
    background:var(--surface);
    padding:9px 16px;
    border-radius:20px;
  }

  /* ---------- Connect ---------- */
  .connect-card{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:10px;
    padding:30px 28px;
  }

  .ask{
    font-size:15px;
    margin-bottom:18px;
  }

  .ask b{ color:var(--trace); font-weight:600; }

  .fun-fact{
    font-family:'Chakra Petch', sans-serif;
    font-size:16px;
    color:var(--gold);
    font-style:italic;
    border-left:2px solid #e8b45450;
    padding-left:14px;
    margin-bottom:24px;
  }

  .links{
    display:flex;
    gap:12px;
    flex-wrap:wrap;
  }

  .links a{
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    color:var(--bg);
    background:var(--trace);
    padding:11px 20px;
    border-radius:6px;
    text-decoration:none;
    font-weight:500;
    transition:opacity 0.2s ease;
  }

  .links a:hover{ opacity:0.85; }

  footer{
    margin-top:100px;
    padding-top:24px;
    border-top:1px solid var(--border);
    font-family:'JetBrains Mono', monospace;
    font-size:12px;
    color:var(--text-faint);
    display:flex;
    justify-content:space-between;
    flex-wrap:wrap;
    gap:10px;
  }

  @media (max-width:600px){
    section{ padding-top:72px; }
    .hero{ min-height:82vh; }
  }
</style>
</head>
<body>

<canvas id="bg-canvas"></canvas>
<div class="vignette"></div>

<main>

  <section class="hero">
    <div class="eyebrow">Netlist → GDSII, one block at a time</div>
    <h1 class="name">Naragam Manikanta<br>Raghava</h1>
    <div class="role">Aspiring VLSI Design Engineer</div>
    <div class="hero-meta">
      <span>B.Tech ECE, <b>2026</b></span>
      <span>Seshadri Rao Gudlavalleru Engineering College</span>
      <span>CGPA <b>8.80&nbsp;/&nbsp;10</b></span>
    </div>
    <div class="scroll-cue"><span class="line"></span>scroll</div>
  </section>

  <section id="about">
    <div class="sec-head"><span class="sec-num">01</span><span class="sec-title">About Me</span></div>
    <div class="yaml-card">
      <div class="titlebar">
        <div class="dot"></div><div class="dot"></div><div class="dot"></div>
        <span class="fname">about.yaml</span>
      </div>
      <div class="yaml-body">
<div class="row"><span class="yaml-key">name:</span>          <span class="yaml-str">"Naragam Manikanta Raghava"</span></div>
<div class="row"><span class="yaml-key">role:</span>          <span class="yaml-str">"Aspiring VLSI Design Engineer"</span></div>
<div class="row"><span class="yaml-key">degree:</span>        <span class="yaml-str">"B.Tech, Electronics & Communication Engineering (2026)"</span></div>
<div class="row"><span class="yaml-key">college:</span>       <span class="yaml-str">"Seshadri Rao Gudlavalleru Engineering College"</span></div>
<div class="row"><span class="yaml-key">cgpa:</span>          <span class="yaml-str">"8.80 / 10"</span></div>
<div class="row"><span class="yaml-key">currently:</span>     <span class="yaml-str">"Physical Design Training (8 Months) @ VLSI Guru Institute"</span></div>
<div class="row"><span class="yaml-key">focus:</span>         <span class="yaml-punct">[</span><span class="yaml-str">"RTL Design"</span><span class="yaml-punct">, </span><span class="yaml-str">"Verilog HDL"</span><span class="yaml-punct">, </span><span class="yaml-str">"CMOS"</span><span class="yaml-punct">, </span><span class="yaml-str">"STA"</span><span class="yaml-punct">, </span><span class="yaml-str">"ASIC Backend Flow"</span><span class="yaml-punct">]</span></div>
<div class="row"><span class="yaml-key">fun_fact:</span>      <span class="yaml-str">"Slow to start, but once I begin — I'm haunted till I finish it"</span></div>
      </div>
    </div>
  </section>

  <section id="building">
    <div class="sec-head"><span class="sec-num">02</span><span class="sec-title">Currently Building</span></div>
    <div class="build-card">
      <h3>🔭 Physical Design Training — VLSI Guru Institute</h3>
      <p>8-month program covering the full ASIC Netlist → GDSII flow.</p>

      <div class="flow">
        <span class="step done">RTL</span><span class="arrow">→</span>
        <span class="step done">Synthesis</span><span class="arrow">→</span>
        <span class="step active">Floorplan</span><span class="arrow">→</span>
        <span class="step">Placement</span><span class="arrow">→</span>
        <span class="step">CTS</span><span class="arrow">→</span>
        <span class="step">Routing</span><span class="arrow">→</span>
        <span class="step">STA</span><span class="arrow">→</span>
        <span class="step">Sign-off</span><span class="arrow">→</span>
        <span class="step">GDSII</span>
      </div>

      <div class="checklist">
        <div class="item done"><span class="mark">✔</span><span>Digital Design &amp; CMOS Fundamentals</span></div>
        <div class="item done"><span class="mark">✔</span><span>Linux/UNIX &amp; TCL Scripting</span></div>
        <div class="item progress"><span class="mark">◐</span><span>Floorplanning · CTS · Routing · STA · Sign-off — in progress</span></div>
      </div>
    </div>
  </section>

  <section id="highlight">
    <div class="sec-head"><span class="sec-num">03</span><span class="sec-title">Highlight</span></div>
    <div class="highlight">
      <span class="medal">🥇</span>
      <p>Best Project Award — awarded among <span class="num">271</span> ECE students
        <span class="proj">for the final-year project "Braille-Based IoT Home Automation for Multi-Disability Empowerment"</span>
      </p>
    </div>
  </section>

  <section id="projects">
    <div class="sec-head"><span class="sec-num">04</span><span class="sec-title">Featured Projects</span></div>
    <div class="projects">

      <a class="proj-card" href="https://github.com/NMRL24/Braille-Based-IoT-Home-Automation-for-Multi-Disability-Empowerment" target="_blank" rel="noopener">
        <div class="proj-top">
          <span class="proj-title">♿ Braille-Based IoT Home Automation</span>
          <span class="proj-arrow">↗</span>
        </div>
        <div class="proj-desc">Led a 4-member team building a dual-ESP32 assistive system enabling home automation for visually and speech-impaired users.</div>
        <div class="tags"><span class="tag">ESP32</span><span class="tag">IoT</span><span class="tag">Embedded C</span><span class="tag">Accessibility</span></div>
      </a>

      <a class="proj-card" href="https://github.com/NMRL24/Vehicle-Speed-Monitoring-Overspeed-Alert-System" target="_blank" rel="noopener">
        <div class="proj-top">
          <span class="proj-title">🚗 Vehicle Speed Monitoring &amp; Overspeed Alert</span>
          <span class="proj-arrow">↗</span>
        </div>
        <div class="proj-desc">Real-time vehicle speed monitoring and overspeed alert system built on ESP32, integrated with the Blynk IoT platform.</div>
        <div class="tags"><span class="tag">ESP32</span><span class="tag">Blynk</span><span class="tag">Real-Time Systems</span></div>
      </a>

      <a class="proj-card" href="https://github.com/NMRL24/Verilog-HDL-Projects" target="_blank" rel="noopener">
        <div class="proj-top">
          <span class="proj-title">🖥️ Verilog HDL Projects Collection</span>
          <span class="proj-arrow">↗</span>
        </div>
        <div class="proj-desc">RTL designs simulated in Xilinx Vivado — 128-bit ALU, FSM-based Elevator Controller, Vending Machine Controller, Digital Clock, and 101 Sequence Detector.</div>
        <div class="tags"><span class="tag">Verilog HDL</span><span class="tag">RTL Design</span><span class="tag">Xilinx Vivado</span><span class="tag">FSM</span></div>
      </a>

    </div>
  </section>

  <section id="stack">
    <div class="sec-head"><span class="sec-num">05</span><span class="sec-title">Tech Stack</span></div>
    <div class="stack-grid">
      <span class="stack-chip">Verilog HDL</span>
      <span class="stack-chip">Xilinx Vivado</span>
      <span class="stack-chip">TCL</span>
      <span class="stack-chip">Linux / UNIX</span>
      <span class="stack-chip">C</span>
      <span class="stack-chip">Embedded C</span>
      <span class="stack-chip">Python</span>
      <span class="stack-chip">ESP32</span>
    </div>
  </section>

  <section id="connect">
    <div class="sec-head"><span class="sec-num">06</span><span class="sec-title">Connect With Me</span></div>
    <div class="connect-card">
      <div class="ask">💬 <b>Ask me about:</b> Verilog HDL · RTL Design · Digital Electronics · C · Embedded C · Python</div>
      <div class="fun-fact">⚡ I'm a little slow to start, but once I begin something, I'm haunted till I finish it.</div>
      <div class="links">
        <a href="https://github.com/NMRL24" target="_blank" rel="noopener">GitHub ↗</a>
      </div>
    </div>
  </section>

  <footer>
    <span>© 2026 Naragam Manikanta Raghava</span>
    <span>Built for the fab</span>
  </footer>

</main>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
(function(){
  var canvas = document.getElementById('bg-canvas');
  var reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

  var scene = new THREE.Scene();
  var camera = new THREE.PerspectiveCamera(55, window.innerWidth/window.innerHeight, 0.1, 1000);
  camera.position.z = 60;

  var renderer = new THREE.WebGLRenderer({ canvas: canvas, antialias:true, alpha:true });
  renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
  renderer.setSize(window.innerWidth, window.innerHeight);

  // --- Node field: like die interconnects / bond pads drifting in space ---
  var NODE_COUNT = window.innerWidth < 700 ? 55 : 110;
  var SPREAD = 90;
  var nodes = [];
  var nodeGeo = new THREE.BufferGeometry();
  var positions = new Float32Array(NODE_COUNT * 3);
  var velocities = [];

  for (var i = 0; i < NODE_COUNT; i++){
    var x = (Math.random()-0.5) * SPREAD * 2;
    var y = (Math.random()-0.5) * SPREAD * 1.4;
    var z = (Math.random()-0.5) * 60 - 10;
    positions[i*3] = x;
    positions[i*3+1] = y;
    positions[i*3+2] = z;
    velocities.push({
      x: (Math.random()-0.5) * 0.012,
      y: (Math.random()-0.5) * 0.012,
      z: (Math.random()-0.5) * 0.008
    });
  }
  nodeGeo.setAttribute('position', new THREE.BufferAttribute(positions, 3));

  var nodeMat = new THREE.PointsMaterial({
    color: 0x3ddbd9,
    size: 1.6,
    transparent: true,
    opacity: 0.75,
    sizeAttenuation: true
  });
  var points = new THREE.Points(nodeGeo, nodeMat);
  scene.add(points);

  // --- Trace lines: connect nearby nodes, like RDL routing ---
  var lineGeo = new THREE.BufferGeometry();
  var maxLines = NODE_COUNT * 4;
  var linePositions = new Float32Array(maxLines * 2 * 3);
  lineGeo.setAttribute('position', new THREE.BufferAttribute(linePositions, 3));
  var lineMat = new THREE.LineBasicMaterial({
    color: 0x3ddbd9,
    transparent: true,
    opacity: 0.14
  });
  var lines = new THREE.LineSegments(lineGeo, lineMat);
  scene.add(lines);

  var LINK_DIST = 17;

  function updateLinks(){
    var arr = nodeGeo.attributes.position.array;
    var lp = lineGeo.attributes.position.array;
    var idx = 0;
    for (var i = 0; i < NODE_COUNT && idx < linePositions.length - 6; i++){
      var ax = arr[i*3], ay = arr[i*3+1], az = arr[i*3+2];
      for (var j = i+1; j < NODE_COUNT && idx < linePositions.length - 6; j++){
        var bx = arr[j*3], by = arr[j*3+1], bz = arr[j*3+2];
        var dx = ax-bx, dy = ay-by, dz = az-bz;
        var d = Math.sqrt(dx*dx + dy*dy + dz*dz);
        if (d < LINK_DIST){
          lp[idx++] = ax; lp[idx++] = ay; lp[idx++] = az;
          lp[idx++] = bx; lp[idx++] = by; lp[idx++] = bz;
        }
      }
    }
    for (; idx < linePositions.length; idx++){ lp[idx] = 0; }
    lineGeo.attributes.position.needsUpdate = true;
  }

  updateLinks();

  var mouseX = 0, mouseY = 0;
  window.addEventListener('mousemove', function(e){
    mouseX = (e.clientX / window.innerWidth - 0.5);
    mouseY = (e.clientY / window.innerHeight - 0.5);
  });

  window.addEventListener('resize', function(){
    camera.aspect = window.innerWidth / window.innerHeight;
    camera.updateProjectionMatrix();
    renderer.setSize(window.innerWidth, window.innerHeight);
  });

  var frame = 0;

  function animate(){
    requestAnimationFrame(animate);
    frame++;

    if (!reduceMotion){
      var arr = nodeGeo.attributes.position.array;
      for (var i = 0; i < NODE_COUNT; i++){
        arr[i*3]   += velocities[i].x;
        arr[i*3+1] += velocities[i].y;
        arr[i*3+2] += velocities[i].z;

        if (arr[i*3] > SPREAD || arr[i*3] < -SPREAD) velocities[i].x *= -1;
        if (arr[i*3+1] > SPREAD*0.7 || arr[i*3+1] < -SPREAD*0.7) velocities[i].y *= -1;
        if (arr[i*3+2] > 30 || arr[i*3+2] < -50) velocities[i].z *= -1;
      }
      nodeGeo.attributes.position.needsUpdate = true;

      if (frame % 4 === 0) updateLinks();

      camera.position.x += (mouseX * 12 - camera.position.x) * 0.02;
      camera.position.y += (-mouseY * 8 - camera.position.y) * 0.02;
      camera.lookAt(0,0,0);
    }

    renderer.render(scene, camera);
  }
  animate();
})();
</script>

</body>
</html>
