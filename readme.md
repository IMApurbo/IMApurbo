<div align="center">

<!-- Animated banner — pure CSS/SVG, no JS required, works in GitHub -->
<svg viewBox="0 0 900 220" xmlns="http://www.w3.org/2000/svg" width="100%">
  <defs>
    <style>
      .bg { fill: #0a0e0a; }
      .grid-line { stroke: #1a2e1a; stroke-width: 0.5; }
      .node { fill: #599200; }
      .node-glow { fill: #599200; opacity: 0.15; }
      .edge { stroke: #599200; stroke-width: 0.8; fill: none; opacity: 0.3; }
      .particle { fill: #7ab800; }
      .title { font-family: 'Courier New', monospace; fill: #599200; font-weight: 700; }
      .subtitle { font-family: 'Courier New', monospace; fill: #3d6600; }
      .orbit { fill: none; stroke: #599200; stroke-width: 0.5; opacity: 0.2; }
      @keyframes pulse { 0%,100%{opacity:.15;r:3} 50%{opacity:.8;r:5} }
      @keyframes pulse2 { 0%,100%{opacity:.3;r:2} 50%{opacity:1;r:4} }
      @keyframes float { 0%{transform:translateY(0)} 50%{transform:translateY(-6px)} 100%{transform:translateY(0)} }
      @keyframes blink { 0%,49%{opacity:1} 50%,100%{opacity:0} }
      @keyframes scan { 0%{transform:translateY(0);opacity:0} 5%{opacity:.5} 95%{opacity:.3} 100%{transform:translateY(220px);opacity:0} }
      @keyframes glow-text { 0%,100%{filter:drop-shadow(0 0 4px #599200)} 50%{filter:drop-shadow(0 0 14px #7ab800)} }
      @keyframes orbit1 { from{transform:rotate(0deg) translateX(38px) rotate(0deg)} to{transform:rotate(360deg) translateX(38px) rotate(-360deg)} }
      @keyframes orbit2 { from{transform:rotate(120deg) translateX(52px) rotate(-120deg)} to{transform:rotate(480deg) translateX(52px) rotate(-480deg)} }
      @keyframes orbit3 { from{transform:rotate(240deg) translateX(28px) rotate(-240deg)} to{transform:rotate(600deg) translateX(28px) rotate(-600deg)} }
      @keyframes draw-edge { from{stroke-dashoffset:200;opacity:0} to{stroke-dashoffset:0;opacity:.25} }
      @keyframes dash-flow { from{stroke-dashoffset:40} to{stroke-dashoffset:0} }
      @keyframes core-pulse { 0%,100%{r:4;opacity:.8} 50%{r:5.5;opacity:1} }
      @keyframes bar-fill { from{width:0} to{width:170px} }
      @keyframes flicker { 0%,94%,96%,100%{opacity:1} 95%{opacity:.3} }
      .p1{animation:pulse 2.1s ease-in-out infinite}
      .p2{animation:pulse 3.3s ease-in-out infinite .7s}
      .p3{animation:pulse2 2.7s ease-in-out infinite 1.2s}
      .p4{animation:pulse 1.9s ease-in-out infinite .4s}
      .p5{animation:pulse2 2.5s ease-in-out infinite 1.8s}
      .p6{animation:pulse 3.1s ease-in-out infinite .9s}
      .p7{animation:pulse2 2.3s ease-in-out infinite .2s}
      .p8{animation:pulse 2.8s ease-in-out infinite 1.5s}
      .p9{animation:pulse2 3.5s ease-in-out infinite .6s}
      .p10{animation:pulse 2.0s ease-in-out infinite 2.1s}
      .scan-a{animation:scan 4s linear infinite}
      .scan-b{animation:scan 4s linear infinite 2s}
      .title-glow{animation:glow-text 3s ease-in-out infinite,flicker 8s step-end infinite 2s}
      .sub-glow{animation:glow-text 4s ease-in-out infinite 1s}
      .op1{transform-origin:770px 70px;animation:orbit1 6s linear infinite}
      .op2{transform-origin:770px 70px;animation:orbit2 9s linear infinite}
      .op3{transform-origin:770px 70px;animation:orbit3 4.5s linear infinite}
      .e1{stroke-dasharray:200;animation:draw-edge 2s ease-out forwards,dash-flow 3s linear infinite 2s}
      .e2{stroke-dasharray:200;animation:draw-edge 2s ease-out .3s forwards,dash-flow 3s linear infinite 2.3s}
      .e3{stroke-dasharray:200;animation:draw-edge 2s ease-out .6s forwards,dash-flow 3s linear infinite 2.6s}
      .e4{stroke-dasharray:200;animation:draw-edge 2s ease-out .9s forwards,dash-flow 3s linear infinite 2.9s}
      .e5{stroke-dasharray:200;animation:draw-edge 2s ease-out 1.2s forwards,dash-flow 3s linear infinite 3.2s}
      .e6{stroke-dasharray:200;animation:draw-edge 2s ease-out .15s forwards,dash-flow 3s linear infinite 2.15s}
      .e7{stroke-dasharray:200;animation:draw-edge 2s ease-out .45s forwards,dash-flow 3s linear infinite 2.45s}
      .cursor-blink{animation:blink 1s step-end infinite}
      .float-a{animation:float 4s ease-in-out infinite}
      .float-b{animation:float 5.5s ease-in-out infinite 1.5s}
    </style>
    <linearGradient id="bgGrad" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0%" stop-color="#070b07"/>
      <stop offset="100%" stop-color="#0d150d"/>
    </linearGradient>
    <linearGradient id="gridFade" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0%" stop-color="#0a0e0a" stop-opacity="0"/>
      <stop offset="60%" stop-color="#0a0e0a" stop-opacity="0"/>
      <stop offset="100%" stop-color="#0a0e0a" stop-opacity="1"/>
    </linearGradient>
    <linearGradient id="glowH" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0%" stop-color="#599200" stop-opacity="0.15"/>
      <stop offset="100%" stop-color="#599200" stop-opacity="0"/>
    </linearGradient>
  </defs>
  <!-- Background -->
  <rect width="900" height="220" fill="url(#bgGrad)"/>
  <!-- Perspective grid horizontal lines -->
  <line class="grid-line" x1="0" y1="130" x2="900" y2="130" opacity=".8"/>
  <line class="grid-line" x1="0" y1="148" x2="900" y2="148" opacity=".6"/>
  <line class="grid-line" x1="0" y1="163" x2="900" y2="163" opacity=".45"/>
  <line class="grid-line" x1="0" y1="175" x2="900" y2="175" opacity=".35"/>
  <line class="grid-line" x1="0" y1="185" x2="900" y2="185" opacity=".25"/>
  <line class="grid-line" x1="0" y1="193" x2="900" y2="193" opacity=".18"/>
  <line class="grid-line" x1="0" y1="200" x2="900" y2="200" opacity=".12"/>
  <line class="grid-line" x1="0" y1="206" x2="900" y2="206" opacity=".08"/>
  <line class="grid-line" x1="0" y1="211" x2="900" y2="211" opacity=".05"/>
  <!-- Vertical lines converging to vanishing point 450,80 -->
  <line class="grid-line" x1="450" y1="80" x2="0"   y2="220" opacity=".5"/>
  <line class="grid-line" x1="450" y1="80" x2="112"  y2="220" opacity=".5"/>
  <line class="grid-line" x1="450" y1="80" x2="225"  y2="220" opacity=".5"/>
  <line class="grid-line" x1="450" y1="80" x2="337"  y2="220" opacity=".5"/>
  <line class="grid-line" x1="450" y1="80" x2="450"  y2="220" opacity=".5"/>
  <line class="grid-line" x1="450" y1="80" x2="562"  y2="220" opacity=".5"/>
  <line class="grid-line" x1="450" y1="80" x2="675"  y2="220" opacity=".5"/>
  <line class="grid-line" x1="450" y1="80" x2="787"  y2="220" opacity=".5"/>
  <line class="grid-line" x1="450" y1="80" x2="900"  y2="220" opacity=".5"/>
  <!-- Horizon glow -->
  <rect x="0" y="120" width="900" height="20" fill="url(#glowH)"/>
  <!-- Scan lines -->
  <rect class="scan-a" x="0" y="0" width="900" height="2" fill="#599200" opacity=".04"/>
  <rect class="scan-b" x="0" y="0" width="900" height="1.5" fill="#599200" opacity=".03"/>
  <!-- LEFT: Particle network -->
  <g class="float-b">
    <line class="edge e1" x1="80"  y1="45"  x2="145" y2="80"/>
    <line class="edge e2" x1="145" y1="80"  x2="110" y2="105"/>
    <line class="edge e3" x1="145" y1="80"  x2="185" y2="55"/>
    <line class="edge e4" x1="185" y1="55"  x2="210" y2="88"/>
    <line class="edge e5" x1="110" y1="105" x2="160" y2="112"/>
    <line class="edge e6" x1="160" y1="112" x2="210" y2="88"/>
    <line class="edge e7" x1="60"  y1="85"  x2="110" y2="105"/>
    <circle class="node-glow" cx="80"  cy="45"  r="10"/>
    <circle class="node-glow" cx="145" cy="80"  r="14"/>
    <circle class="node-glow" cx="110" cy="105" r="10"/>
    <circle class="node-glow" cx="185" cy="55"  r="10"/>
    <circle class="node-glow" cx="210" cy="88"  r="12"/>
    <circle class="node-glow" cx="160" cy="112" r="9"/>
    <circle class="node-glow" cx="60"  cy="85"  r="9"/>
    <circle class="node p1" cx="80"  cy="45"  r="3"/>
    <circle class="node p2" cx="145" cy="80"  r="5"/>
    <circle class="node p3" cx="110" cy="105" r="3"/>
    <circle class="node p4" cx="185" cy="55"  r="3"/>
    <circle class="node p5" cx="210" cy="88"  r="4"/>
    <circle class="node p6" cx="160" cy="112" r="2.5"/>
    <circle class="node p7" cx="60"  cy="85"  r="2.5"/>
  </g>
  <!-- CENTER: Title -->
  <g class="title-glow">
    <text x="450" y="52" font-size="32" font-weight="700" text-anchor="middle"
      font-family="'Courier New',Courier,monospace" fill="#599200">IMApurbo</text>
  </g>
  <rect class="cursor-blink" x="548" y="28" width="3" height="20" rx="1" fill="#599200"/>
  <text x="450" y="74" font-size="11" text-anchor="middle"
    font-family="'Courier New',Courier,monospace" fill="#3a6000" class="sub-glow">
    Python Developer · Automation Master · Security Researcher
  </text>
  <text x="450" y="96" font-size="9.5" text-anchor="middle"
    font-family="'Courier New',Courier,monospace" fill="#2a4800" opacity=".9">
    $ python exploit.py --target=world --mode=ethical --verbose
  </text>
  <rect x="280" y="104" width="340" height="14" rx="3" fill="#0f1a0f" stroke="#1a2e1a" stroke-width=".5"/>
  <rect x="282" y="106" rx="2" fill="#1a3300" opacity=".85" height="10">
    <animate attributeName="width" values="0;170;170" dur="2.5s" fill="freeze"/>
  </rect>
  <text x="450" y="116" font-size="7.5" text-anchor="middle"
    font-family="'Courier New',Courier,monospace" fill="#599200" opacity=".7">
    SYSTEM ONLINE · ALL MODULES LOADED · READY
  </text>
  <!-- RIGHT: Orbital sphere -->
  <g class="float-a">
    <ellipse class="orbit" cx="770" cy="70" rx="52" ry="18"/>
    <ellipse class="orbit" cx="770" cy="70" rx="38" ry="42" opacity=".15"/>
    <ellipse class="orbit" cx="770" cy="70" rx="28" ry="12" opacity=".12" transform="rotate(-30,770,70)"/>
    <circle cx="770" cy="70" r="14" fill="#0f1a0f" stroke="#599200" stroke-width="1.2" opacity=".9"/>
    <circle cx="770" cy="70" r="8" fill="#1a3300" opacity=".6"/>
    <circle cx="770" cy="70" r="4" fill="#599200" opacity=".8">
      <animate attributeName="r" values="4;5.5;4" dur="2s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values=".8;1;.8" dur="2s" repeatCount="indefinite"/>
    </circle>
    <circle class="particle op1" cx="770" cy="70" r="2.5" fill="#7ab800"/>
    <circle class="particle op2" cx="770" cy="70" r="2" fill="#599200"/>
    <circle class="particle op3" cx="770" cy="70" r="1.8" fill="#3d6600"/>
    <circle class="node p8"  cx="820" cy="40" r="2" fill="#599200"/>
    <circle class="node p9"  cx="835" cy="90" r="1.8" fill="#599200"/>
    <circle class="node p10" cx="730" cy="30" r="2" fill="#599200"/>
    <line x1="820" y1="40" x2="784" y2="56" stroke="#599200" stroke-width=".8" fill="none" opacity=".2"/>
    <line x1="730" y1="30" x2="756" y2="56" stroke="#599200" stroke-width=".8" fill="none" opacity=".2"/>
  </g>
  <!-- Binary rain bottom -->
  <g font-family="'Courier New',Courier,monospace" font-size="7" fill="#1a2e1a" text-anchor="middle">
    <text x="30"  y="140" opacity=".6">01</text><text x="60"  y="145" opacity=".5">10</text>
    <text x="90"  y="141" opacity=".7">11</text><text x="120" y="143" opacity=".4">01</text>
    <text x="150" y="140" opacity=".6">10</text><text x="180" y="144" opacity=".5">00</text>
    <text x="750" y="140" opacity=".6">10</text><text x="780" y="143" opacity=".5">01</text>
    <text x="810" y="140" opacity=".7">11</text><text x="840" y="142" opacity=".4">00</text>
    <text x="870" y="141" opacity=".6">10</text>
  </g>
  <!-- Grid fade overlay -->
  <rect x="0" y="130" width="900" height="90" fill="url(#gridFade)"/>
  <!-- Bottom accent line -->
  <line x1="0" y1="219" x2="900" y2="219" stroke="#599200" stroke-width=".5" opacity=".2"/>
  <line x1="200" y1="219" x2="700" y2="219" stroke="#599200" stroke-width="1" opacity=".4"/>
</svg>

<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=22&pause=1000&color=599200&center=true&vCenter=true&width=700&lines=Python+Developer+%7C+Automation+Master;Security+Tools+%26+AI+Enthusiast;Pushing+boundaries+with+code+%F0%9F%94%A5" alt="Typing SVG" />
</div>

</div>

---

## About Me 🔥

I'm a passionate **Python developer** obsessed with automation, web tools, AI, and ethical security research. I love crafting powerful scripts that solve real problems and exploring the darker (but legal) corners of tech.

- 🔭 Currently building advanced automation & pentesting tools  
- 🌱 Mastering advanced NLP, machine learning & ethical hacking  
- 👯 Open to collaborate on Python automation, web scraping, or security projects  
- 💬 Ask me about **Python, Automation, Web Scraping, AI Chatbots, Brute-Forcers**  
- 📫 Reach me: **[imapurbo@proton.me](mailto:imapurbo@proton.me)**  
- ⚡ **Fun fact**: My scripts run faster than I can finish my coffee ☕🚀

---

## 🛠️ Tech Stack & Tools

<p align="center">
  <img src="https://img.shields.io/badge/-Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/-JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
  <img src="https://img.shields.io/badge/-React-61DAFB?style=for-the-badge&logo=react&logoColor=black" />
  <img src="https://img.shields.io/badge/-Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" />
  <img src="https://img.shields.io/badge/-Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" />
  <img src="https://img.shields.io/badge/-Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/-Git-F05032?style=for-the-badge&logo=git&logoColor=white" />
  <img src="https://img.shields.io/badge/-VS%20Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white" />
</p>

---

## 📊 GitHub Stats

<p align="center">
  <img src="https://github-readme-stats-trinibs-projects.vercel.app/api?username=IMApurbo&show_icons=true&theme=merko&border_color=599200" alt="IMApurbo's GitHub Stats" />
</p>

<p align="center">
  <img src="https://github-readme-stats-trinibs-projects.vercel.app/api/top-langs/?username=IMApurbo&layout=compact&theme=merko&border_color=599200" alt="Top Languages" />
  <img src="https://github-readme-streak-stats-trinibs-projects.vercel.app/?user=IMApurbo&theme=merko&border=599200" alt="GitHub Streak" />
</p>

---

## 🔥 Featured Projects

| Project | Description | Link |
|---------|-------------|------|
| **fckr** | High-performance brute-force tool for security research | [![PyPI](https://img.shields.io/pypi/v/fckr?color=599200&style=for-the-badge)](https://pypi.org/project/fckr) |
| **crawlerx** | Advanced web crawling framework for data extraction | [![PyPI](https://img.shields.io/pypi/v/crawlerx?color=599200&style=for-the-badge)](https://pypi.org/project/crawlerx) |
| **nlpchat** | Easy-to-use AI chatbot builder with NLP | [![PyPI](https://img.shields.io/pypi/v/nlpchat?color=599200&style=for-the-badge)](https://pypi.org/project/nlpchat) |

> **Pro Tip**: Always use these tools **responsibly** and **ethically** — only on systems you own or have explicit permission to test! 🛡️

---

## 🤝 Connect With Me

<p align="center">
  <a href="https://www.linkedin.com/in/your-profile">
    <img src="https://img.shields.io/badge/-LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="https://twitter.com/your-handle">
    <img src="https://img.shields.io/badge/-Twitter/X-1DA1F2?style=for-the-badge&logo=x&logoColor=white" />
  </a>
  <a href="https://your-portfolio.com">
    <img src="https://img.shields.io/badge/-Portfolio-000000?style=for-the-badge&logo=react&logoColor=white" />
  </a>
  <a href="mailto:imapurbo@proton.me">
    <img src="https://img.shields.io/badge/-Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=IMApurbo&label=Profile%20Views&color=599200&style=for-the-badge" alt="Profile views" />
</p>

---

<div align="center">
  ⭐️ From <strong>IMApurbo</strong> — Code with passion, hack with responsibility 🚀
</div>
