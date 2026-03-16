<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Jiawei – GitHub Profile Preview</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Sora:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg:          #0d1117;
    --surface:     #161b22;
    --border:      #30363d;
    --text:        #c9d1d9;
    --muted:       #8b949e;
    --blue:        #58a6ff;
    --green:       #3fb950;
    --orange:      #d29922;
    --purple:      #bc8cff;
    --font-mono:   'JetBrains Mono', monospace;
    --font-body:   'Sora', sans-serif;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-body);
    font-size: 15px;
    line-height: 1.7;
  }

  /* ── GitHub chrome wrapper ── */
  .chrome-bar {
    height: 48px;
    background: #161b22;
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    padding: 0 24px;
    gap: 12px;
  }
  .chrome-dot { width: 12px; height: 12px; border-radius: 50%; }
  .d1 { background: #ff5f57; }
  .d2 { background: #febc2e; }
  .d3 { background: #28c840; }
  .chrome-url {
    flex: 1;
    max-width: 420px;
    margin-left: 16px;
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 4px 12px;
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--muted);
  }

  /* ── Page layout ── */
  .page { max-width: 960px; margin: 0 auto; padding: 32px 24px 80px; }

  /* ── Banner ── */
  .banner {
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 32px;
    background: linear-gradient(135deg,
      #0d1117 0%,
      #0e2042 40%,
      #0d1117 100%);
    border: 1px solid var(--border);
    padding: 48px 32px 36px;
    text-align: center;
    position: relative;
  }
  .banner::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse at 20% 60%, rgba(88,166,255,0.12) 0%, transparent 55%),
      radial-gradient(ellipse at 80% 30%, rgba(63,185,80,0.08) 0%, transparent 55%);
    pointer-events: none;
  }
  .banner-wave-top {
    position: absolute; top: 0; left: 0; right: 0; height: 6px;
    background: linear-gradient(90deg, #58a6ff, #3fb950, #58a6ff);
    border-radius: 12px 12px 0 0;
  }
  .banner h1 {
    font-size: 2.8rem;
    font-weight: 700;
    color: #fff;
    letter-spacing: -1px;
    margin-bottom: 6px;
  }
  .banner h1 span { color: var(--blue); }
  .banner-sub {
    font-size: 1rem;
    color: var(--muted);
    margin-bottom: 20px;
  }
  .typing-line {
    display: inline-block;
    font-family: var(--font-mono);
    font-size: 0.95rem;
    color: var(--blue);
    border-right: 2px solid var(--blue);
    padding-right: 4px;
    white-space: nowrap;
    overflow: hidden;
    animation: typing 3s steps(42) infinite alternate, blink 0.7s step-end infinite;
    max-width: 44ch;
  }
  @keyframes typing {
    from { width: 0 }
    to   { width: 44ch }
  }
  @keyframes blink {
    50% { border-color: transparent }
  }
  .views-badge {
    display: inline-block;
    margin-top: 16px;
    background: rgba(88,166,255,0.1);
    border: 1px solid rgba(88,166,255,0.3);
    border-radius: 20px;
    padding: 4px 14px;
    font-size: 0.78rem;
    font-family: var(--font-mono);
    color: var(--blue);
  }

  /* ── Section ── */
  section {
    margin-bottom: 32px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 24px 28px;
  }
  section h2 {
    font-size: 1.1rem;
    font-weight: 600;
    color: #fff;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    padding-bottom: 12px;
    border-bottom: 1px solid var(--border);
  }
  section h2 .emoji { font-size: 1.2rem; }

  /* ── About code block ── */
  .code-block {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 20px;
    font-family: var(--font-mono);
    font-size: 0.82rem;
    line-height: 1.9;
    margin-top: 12px;
    overflow-x: auto;
  }
  .code-block .kw  { color: #ff7b72; }
  .code-block .str { color: #a5d6ff; }
  .code-block .var { color: var(--blue); }
  .code-block .num { color: #79c0ff; }
  .code-block .cm  { color: var(--muted); }
  .code-block .bra { color: #e6edf3; }
  .about-quote {
    font-style: italic;
    color: var(--muted);
    border-left: 3px solid var(--blue);
    padding-left: 16px;
    margin-bottom: 16px;
    line-height: 1.6;
  }

  /* ── Education table ── */
  .edu-table { width: 100%; border-collapse: collapse; }
  .edu-table tr { border-bottom: 1px solid var(--border); }
  .edu-table tr:last-child { border-bottom: none; }
  .edu-table td { padding: 12px 8px; vertical-align: top; }
  .edu-table td:first-child { font-size: 1.4rem; width: 40px; }
  .edu-table .deg { font-weight: 600; color: #fff; font-size: 0.9rem; }
  .edu-table .uni { color: var(--muted); font-size: 0.82rem; margin-top: 2px; }
  .edu-table .gpa {
    display: inline-block;
    background: rgba(63,185,80,0.12);
    border: 1px solid rgba(63,185,80,0.3);
    color: var(--green);
    border-radius: 4px;
    padding: 1px 7px;
    font-size: 0.75rem;
    font-family: var(--font-mono);
    margin-left: 6px;
  }
  .edu-table .period {
    font-size: 0.78rem;
    color: var(--muted);
    font-family: var(--font-mono);
    white-space: nowrap;
    text-align: right;
  }

  /* ── Experience ── */
  .exp-item { margin-bottom: 16px; }
  .exp-item:last-child { margin-bottom: 0; }
  .exp-header {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    gap: 12px;
    margin-bottom: 8px;
  }
  .exp-title {
    font-weight: 600;
    color: #fff;
    font-size: 0.92rem;
  }
  .exp-period {
    font-size: 0.75rem;
    font-family: var(--font-mono);
    color: var(--muted);
    white-space: nowrap;
  }
  .exp-bullets { list-style: none; padding-left: 0; }
  .exp-bullets li {
    padding: 2px 0 2px 16px;
    position: relative;
    font-size: 0.87rem;
    color: var(--muted);
  }
  .exp-bullets li::before {
    content: '▸';
    position: absolute; left: 0;
    color: var(--blue);
    font-size: 0.8rem;
  }
  .exp-bullets li strong { color: var(--text); }
  .exp-divider { border: none; border-top: 1px solid var(--border); margin: 16px 0; }

  /* ── Awards ── */
  .awards-table { width: 100%; border-collapse: collapse; }
  .awards-table th {
    text-align: left;
    font-size: 0.78rem;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    color: var(--muted);
    padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
  }
  .awards-table td { padding: 10px 0; border-bottom: 1px solid rgba(48,54,61,0.5); font-size: 0.87rem; }
  .awards-table tr:last-child td { border-bottom: none; }
  .awards-table .medal { font-size: 1.1rem; padding-right: 8px; }
  .awards-table .year {
    font-family: var(--font-mono);
    font-size: 0.78rem;
    color: var(--muted);
    text-align: right;
  }

  /* ── Badges ── */
  .badge-group { margin-bottom: 12px; }
  .badge-group-label {
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--muted);
    margin-bottom: 8px;
    font-family: var(--font-mono);
  }
  .badges { display: flex; flex-wrap: wrap; gap: 8px; }
  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 5px 12px;
    font-size: 0.78rem;
    font-family: var(--font-mono);
    font-weight: 500;
    transition: border-color 0.15s, background 0.15s;
  }
  .badge:hover { border-color: var(--blue); background: rgba(88,166,255,0.06); }
  .badge .dot { width: 8px; height: 8px; border-radius: 50%; }
  .b-c      { color: #a8b9cc; } .b-c .dot      { background: #a8b9cc; }
  .b-py     { color: #3572a5; } .b-py .dot     { background: #3572a5; }
  .b-js     { color: #f1e05a; } .b-js .dot     { background: #f1e05a; }
  .b-ts     { color: #2b7489; } .b-ts .dot     { background: #2b7489; }
  .b-sql    { color: #336791; } .b-sql .dot    { background: #336791; }
  .b-arm    { color: #0091bd; } .b-arm .dot    { background: #0091bd; }
  .b-react  { color: #61dafb; } .b-react .dot  { background: #61dafb; }
  .b-node   { color: #43853d; } .b-node .dot   { background: #43853d; }
  .b-git    { color: #f05032; } .b-git .dot    { background: #f05032; }
  .b-linux  { color: #fcc624; } .b-linux .dot  { background: #fcc624; }
  .b-alt    { color: #a5915f; } .b-alt .dot    { background: #a5915f; }
  .b-obs    { color: #7c3aed; } .b-obs .dot    { background: #7c3aed; }

  /* ── Currently Exploring ── */
  .explore-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  .explore-card {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 12px 14px;
  }
  .explore-card:hover { border-color: rgba(88,166,255,0.4); }
  .explore-card .ec-icon { font-size: 1.2rem; margin-bottom: 6px; }
  .explore-card .ec-title { font-size: 0.85rem; font-weight: 600; color: #fff; }
  .explore-card .ec-desc  { font-size: 0.78rem; color: var(--muted); margin-top: 2px; }

  /* ── Competencies tree ── */
  .tree-block {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 20px;
    font-family: var(--font-mono);
    font-size: 0.82rem;
    line-height: 2;
    color: var(--text);
  }
  .tree-block .leaf { color: var(--muted); }
  .tree-block .branch { color: var(--blue); }

  /* ── Stats ── */
  .stats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 12px; }
  .stats-card {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
  }
  .stats-card img { width: 100%; display: block; }
  .streak-card {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
    text-align: center;
  }
  .streak-card img { width: 100%; display: block; }

  /* ── Contact ── */
  .contact-row {
    display: flex;
    justify-content: center;
    gap: 12px;
    flex-wrap: wrap;
    padding-top: 8px;
  }
  .contact-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 8px 18px;
    font-size: 0.85rem;
    font-family: var(--font-mono);
    color: var(--text);
    text-decoration: none;
    transition: all 0.15s;
  }
  .contact-btn:hover { border-color: var(--blue); color: var(--blue); }
  .contact-btn .cb-icon { font-size: 1rem; }

  /* ── Footer wave ── */
  .footer-wave {
    height: 6px;
    background: linear-gradient(90deg, #3fb950, #58a6ff, #3fb950);
    border-radius: 0 0 12px 12px;
    margin-top: -8px;
  }

  /* ── Responsive ── */
  @media (max-width: 600px) {
    .stats-grid     { grid-template-columns: 1fr; }
    .explore-grid   { grid-template-columns: 1fr; }
    .banner h1      { font-size: 2rem; }
  }
</style>
</head>
<body>

<!-- Browser chrome -->
<div class="chrome-bar">
  <div class="chrome-dot d1"></div>
  <div class="chrome-dot d2"></div>
  <div class="chrome-dot d3"></div>
  <div class="chrome-url">github.com/Jack5336</div>
</div>

<div class="page">

  <!-- ── BANNER ── -->
  <div class="banner">
    <div class="banner-wave-top"></div>
    <h1>Hi, I'm <span>Jiawei</span> 👋</h1>
    <p class="banner-sub">CS @ UCL &nbsp;·&nbsp; PKM Enthusiast &nbsp;·&nbsp; Philosophy &amp; Tech</p>
    <div class="typing-line">Building Personal AI Infrastructure</div>
    <br>
    <span class="views-badge">👁 profile views · Jack5336</span>
  </div>

  <!-- ── ABOUT ── -->
  <section>
    <h2><span class="emoji">🧠</span> About Me</h2>
    <p class="about-quote">"Advanced technology in service of a meaningful life."</p>
    <p style="color:var(--muted); font-size:0.88rem; margin-bottom:14px;">
      I'm a CS graduate student at <strong style="color:var(--text)">UCL</strong> passionate about building systems that amplify human intelligence.
      As a <strong style="color:var(--text)">PKM enthusiast</strong>, I've explored Notion, Flomo, Obsidian, Logseq, and Tana — building my own
      <em style="color:var(--blue)">Personal AI Infrastructure</em> to compound knowledge over time.
      My intellectual diet spans <strong style="color:var(--text)">Philosophy</strong>, software architecture, and the hardware/software interface.
    </p>
    <div class="code-block">
<span class="var">jiawei</span> <span class="kw">=</span> <span class="bra">{</span><br>
&nbsp;&nbsp;<span class="str">"currently"</span><span class="kw">:</span> <span class="str">"MSc Computer Science @ UCL"</span>,<br>
&nbsp;&nbsp;<span class="str">"building"</span><span class="kw">:</span>  <span class="str">"Personal AI Infrastructure (PAI)"</span>,<br>
&nbsp;&nbsp;<span class="str">"reading"</span><span class="kw">:</span>   <span class="bra">[</span><span class="str">"Philosophy of Mind"</span>, <span class="str">"Systems Thinking"</span><span class="bra">]</span>,<br>
&nbsp;&nbsp;<span class="str">"tools"</span><span class="kw">:</span>     <span class="bra">[</span><span class="str">"Obsidian"</span>, <span class="str">"Claude Code"</span>, <span class="str">"Python"</span><span class="bra">]</span>,<br>
&nbsp;&nbsp;<span class="str">"languages"</span><span class="kw">:</span> <span class="bra">[</span><span class="str">"English"</span>, <span class="str">"Mandarin"</span><span class="bra">]</span>,<br>
&nbsp;&nbsp;<span class="str">"ask_me_about"</span><span class="kw">:</span> <span class="bra">[</span><span class="str">"PKM"</span>, <span class="str">"AI agents"</span>, <span class="str">"Hardware design"</span><span class="bra">]</span>,<br>
<span class="bra">}</span>
    </div>
  </section>

  <!-- ── EDUCATION ── -->
  <section>
    <h2><span class="emoji">🎓</span> Education</h2>
    <table class="edu-table">
      <tr>
        <td>🎓</td>
        <td>
          <div class="deg">MSc Computer Science</div>
          <div class="uni">University College London (UCL)</div>
        </td>
        <td class="period">Sept 2024 – Sept 2025</td>
      </tr>
      <tr>
        <td>🎓</td>
        <td>
          <div class="deg">BEng Electronic Science &amp; Technology <span class="gpa">GPA 3.7</span></div>
          <div class="uni">Xi'an Jiaotong-Liverpool University</div>
        </td>
        <td class="period">Sept 2020 – Aug 2024</td>
      </tr>
    </table>
  </section>

  <!-- ── EXPERIENCE ── -->
  <section>
    <h2><span class="emoji">💼</span> Professional Experience</h2>

    <div class="exp-item">
      <div class="exp-header">
        <span class="exp-title">🔧 Hardware Engineer</span>
        <span class="exp-period">Jun 2023 – Sept 2023</span>
      </div>
      <ul class="exp-bullets">
        <li>Selected electronic devices and components (<strong>MPU</strong>, PA, etc.)</li>
        <li>Designed circuit boards using <strong>Altium Designer</strong></li>
        <li>Conducted product modeling and simulation (CAD)</li>
        <li>Performed prototype verification and testing in laboratory settings</li>
      </ul>
    </div>

    <hr class="exp-divider">

    <div class="exp-item">
      <div class="exp-header">
        <span class="exp-title">🔬 Research Assistant</span>
        <span class="exp-period">Jun 2021 – Aug 2021</span>
      </div>
      <ul class="exp-bullets">
        <li>Surveyed state-of-art research on <strong>CMOS logic inverter</strong> transfer characteristics</li>
        <li>Conducted circuit design and simulation</li>
        <li>Constructed and tested circuits on breadboard</li>
        <li>Presented findings via posters and academic presentations · <em>Supervisor: Prof. Sang Lam</em></li>
      </ul>
    </div>
  </section>

  <!-- ── AWARDS ── -->
  <section>
    <h2><span class="emoji">🏆</span> Awards &amp; Achievements</h2>
    <table class="awards-table">
      <tr>
        <th>Award</th><th style="text-align:right">Year</th>
      </tr>
      <tr>
        <td><span class="medal">🥇</span> University Academic Excellence Award</td>
        <td class="year">2021/22</td>
      </tr>
      <tr>
        <td><span class="medal">🥇</span> University Academic Achievement Award</td>
        <td class="year">2022/23</td>
      </tr>
      <tr>
        <td><span class="medal">🏅</span> Mathematical Contest in Modeling — H Award</td>
        <td class="year">Mar 2022</td>
      </tr>
    </table>
  </section>

  <!-- ── TECHNICAL SKILLS ── -->
  <section>
    <h2><span class="emoji">🔧</span> Technical Skills</h2>

    <div class="badge-group">
      <div class="badge-group-label">Languages &amp; Code</div>
      <div class="badges">
        <span class="badge b-c"><span class="dot"></span> C</span>
        <span class="badge b-py"><span class="dot"></span> Python</span>
        <span class="badge b-js"><span class="dot"></span> JavaScript</span>
        <span class="badge b-ts"><span class="dot"></span> TypeScript</span>
        <span class="badge b-sql"><span class="dot"></span> SQL</span>
        <span class="badge b-arm"><span class="dot"></span> ARM Assembly</span>
      </div>
    </div>

    <div class="badge-group" style="margin-top:12px">
      <div class="badge-group-label">Frameworks &amp; Tools</div>
      <div class="badges">
        <span class="badge b-react"><span class="dot"></span> React</span>
        <span class="badge b-node"><span class="dot"></span> Node.js</span>
        <span class="badge b-git"><span class="dot"></span> Git</span>
        <span class="badge b-linux"><span class="dot"></span> Linux</span>
        <span class="badge b-alt"><span class="dot"></span> Altium Designer</span>
        <span class="badge b-obs"><span class="dot"></span> Obsidian</span>
      </div>
    </div>
  </section>

  <!-- ── CURRENTLY EXPLORING ── -->
  <section>
    <h2><span class="emoji">🌱</span> Currently Exploring</h2>
    <div class="explore-grid">
      <div class="explore-card">
        <div class="ec-icon">🤖</div>
        <div class="ec-title">AI Agents &amp; LLM Infrastructure</div>
        <div class="ec-desc">Building autonomous workflows with Claude &amp; DeepSeek</div>
      </div>
      <div class="explore-card">
        <div class="ec-icon">🧩</div>
        <div class="ec-title">Personal Knowledge Management</div>
        <div class="ec-desc">Obsidian-based second brain + spaced repetition systems</div>
      </div>
      <div class="explore-card">
        <div class="ec-icon">📖</div>
        <div class="ec-title">Philosophy of Mind</div>
        <div class="ec-desc">Consciousness, epistemology, personal identity</div>
      </div>
      <div class="explore-card">
        <div class="ec-icon">🔄</div>
        <div class="ec-title">Systems Thinking</div>
        <div class="ec-desc">Emergence, feedback loops, complex adaptive systems</div>
      </div>
    </div>
  </section>

  <!-- ── COMPETENCIES ── -->
  <section>
    <h2><span class="emoji">💡</span> Core Competencies</h2>
    <div class="tree-block">
<span class="branch">├──</span> Computer Science<br>
<span class="branch">│   ├──</span> <span class="leaf">Algorithms &amp; Data Structures</span><br>
<span class="branch">│   ├──</span> <span class="leaf">Computer Architecture</span><br>
<span class="branch">│   └──</span> <span class="leaf">Operating Systems</span><br>
<span class="branch">├──</span> Engineering<br>
<span class="branch">│   ├──</span> <span class="leaf">Hardware &amp; Circuit Design</span><br>
<span class="branch">│   ├──</span> <span class="leaf">Embedded Systems</span><br>
<span class="branch">│   └──</span> <span class="leaf">PCB Design (Altium Designer)</span><br>
<span class="branch">└──</span> Soft Skills<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="branch">├──</span> <span class="leaf">Project Management</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="branch">├──</span> <span class="leaf">Academic Research</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="branch">└──</span> <span class="leaf">English &amp; Mandarin (Fluent)</span>
    </div>
  </section>

  <!-- ── GITHUB STATS ── -->
  <section>
    <h2><span class="emoji">📊</span> GitHub Stats</h2>
    <div class="stats-grid">
      <div class="stats-card">
        <img src="https://github-readme-stats.vercel.app/api?username=Jack5336&show_icons=true&theme=github_dark&include_all_commits=true&count_private=true&border_color=30363d" alt="GitHub Stats">
      </div>
      <div class="stats-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Jack5336&layout=compact&langs_count=8&theme=github_dark&border_color=30363d" alt="Top Languages">
      </div>
    </div>
    <div class="streak-card">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=Jack5336&theme=github-dark-blue&border=30363d" alt="GitHub Streak">
    </div>
  </section>

  <!-- ── CONTACT ── -->
  <section style="text-align:center">
    <h2 style="justify-content:center"><span class="emoji">📫</span> Connect With Me</h2>
    <div class="contact-row">
      <a class="contact-btn" href="https://github.com/Jack5316">
        <span class="cb-icon">⚡</span> @Jack5336
      </a>
    </div>
    <div class="footer-wave" style="margin-top:24px"></div>
  </section>

</div>

</body>
</html>
