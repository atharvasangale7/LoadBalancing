# LoadBalancing
Manage And Balance The Traffic through LoadBalancer

```bash
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculator</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(135deg, #6a11cb, #2575fc);
    }

    .calculator {
      width: 320px;
      background: #1e1e2f;
      border-radius: 20px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.5);
      padding: 20px;
    }

    .display input {
      width: 100%;
      height: 60px;
      border: none;
      border-radius: 12px;
      margin-bottom: 20px;
      font-size: 24px;
      text-align: right;
      padding: 10px;
      background: #2d2d44;
      color: #fff;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 12px;
    }

    .btn {
      height: 60px;
      font-size: 20px;
      border: none;
      border-radius: 12px;
      background: #2d2d44;
      color: #fff;
      cursor: pointer;
      transition: all 0.2s;
    }

    .btn:hover {
      background: #3c3c5c;
      transform: scale(1.05);
    }

    .clear {
      background: #ff4d4d;
    }

    .clear:hover {
      background: #ff1a1a;
    }

    .equal {
      grid-row: span 2;
      background: #4caf50;
      height: 132px;
    }

    .equal:hover {
      background: #45a049;
    }

    .zero {
      grid-column: span 2;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <div class="display">
      <input type="text" id="result" disabled>
    </div>
    <div class="buttons">
      <button class="btn clear" onclick="clearResult()">C</button>
      <button class="btn" onclick="appendValue('/')">÷</button>
      <button class="btn" onclick="appendValue('*')">×</button>
      <button class="btn" onclick="deleteLast()">⌫</button>

      <button class="btn" onclick="appendValue('7')">7</button>
      <button class="btn" onclick="appendValue('8')">8</button>
      <button class="btn" onclick="appendValue('9')">9</button>
      <button class="btn" onclick="appendValue('-')">−</button>

      <button class="btn" onclick="appendValue('4')">4</button>
      <button class="btn" onclick="appendValue('5')">5</button>
      <button class="btn" onclick="appendValue('6')">6</button>
      <button class="btn" onclick="appendValue('+')">+</button>

      <button class="btn" onclick="appendValue('1')">1</button>
      <button class="btn" onclick="appendValue('2')">2</button>
      <button class="btn" onclick="appendValue('3')">3</button>
      <button class="btn equal" onclick="calculate()">=</button>

      <button class="btn zero" onclick="appendValue('0')">0</button>
      <button class="btn" onclick="appendValue('.')">.</button>
    </div>
  </div>

  <script>
    function appendValue(value) {
      document.getElementById("result").value += value;
    }

    function clearResult() {
      document.getElementById("result").value = "";
    }

    function deleteLast() {
      let current = document.getElementById("result").value;
      document.getElementById("result").value = current.slice(0, -1);
    }

    function calculate() {
      try {
        let result = eval(document.getElementById("result").value);
        document.getElementById("result").value = result;
      } catch (e) {
        document.getElementById("result").value = "Error";
      }
    }
  </script>
</body>
</html>

```

```bash
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Atharva Sangale — Portfolio & Info</title>
  <meta name="description" content="Personal information page for Atharva Sangale — Cloud/DevOps & Linux enthusiast from Nashik, India." />
  <meta name="author" content="Atharva Sangale" />
  <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='0.9em' font-size='90'>🛠️</text></svg>">
  <style>
    :root{
      --bg: #0b0f17;
      --card: #121826;
      --muted: #8a94a7;
      --text: #e6e9ef;
      --accent: #5b8cff;
      --accent-2: #7ef0ff;
      --ring: rgba(91,140,255,.45);
      --shadow: 0 10px 30px rgba(0,0,0,.35);
      --radius: 18px;
    }
    *{box-sizing:border-box}
    html,body{margin:0;height:100%;background:radial-gradient(1200px 600px at 80% -10%, rgba(126,240,255,.15), transparent 60%), radial-gradient(800px 400px at 10% -20%, rgba(91,140,255,.18), transparent 60%), var(--bg); color:var(--text); font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";}
    a{color:var(--accent); text-decoration:none}
    a:hover{opacity:.9}
    .container{max-width:1100px; margin:0 auto; padding:24px}
    header{position:sticky; top:0; backdrop-filter:saturate(1.2) blur(10px); background:linear-gradient(to bottom, rgba(11,15,23,.9), rgba(11,15,23,.6)); border-bottom:1px solid rgba(255,255,255,.06); z-index:50}
    .nav{display:flex; align-items:center; justify-content:space-between; gap:16px}
    .brand{display:flex; align-items:center; gap:12px; font-weight:700; letter-spacing:.3px}
    .brand-logo{width:38px; height:38px; border-radius:12px; display:grid; place-content:center; background:linear-gradient(135deg, var(--accent), var(--accent-2)); box-shadow:inset 0 0 0 2px rgba(255,255,255,.2)}
    nav ul{display:flex; list-style:none; gap:18px; padding:0; margin:0}
    nav a{padding:10px 12px; border-radius:10px}
    nav a:hover{background:rgba(255,255,255,.05)}
    .btn{display:inline-flex; align-items:center; gap:8px; padding:10px 14px; border-radius:12px; background:linear-gradient(135deg, var(--accent), var(--accent-2)); color:#0b0f17; font-weight:700; box-shadow:var(--shadow)}
    .btn.secondary{background:#1a2236; color:var(--text); border:1px solid rgba(255,255,255,.08)}
    .grid{display:grid; gap:20px}
    .hero{padding:56px 0 24px}
    .hero-grid{grid-template-columns: 1.2fr .8fr}
    .card{background:linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,.02)); border:1px solid rgba(255,255,255,.08); border-radius:var(--radius); box-shadow:var(--shadow)}
    .card-inner{padding:26px}
    h1{font-size:40px; line-height:1.15; margin:0 0 8px}
    h2{font-size:26px; margin:0 0 8px}
    h3{font-size:20px; margin:0 0 8px}
    p{color:var(--muted); line-height:1.65}
    .kpis{display:grid; grid-template-columns: repeat(3, 1fr); gap:12px; margin-top:18px}
    .kpi{padding:14px; border-radius:14px; background:#121826; border:1px dashed rgba(255,255,255,.08); text-align:center}
    .kpi .num{font-size:22px; font-weight:800}
    .tag{padding:8px 12px; border-radius:999px; background:rgba(126,240,255,.08); border:1px solid rgba(126,240,255,.25); color:#ccf9ff; font-weight:600; font-size:13px}
    .tags{display:flex; flex-wrap:wrap; gap:10px}
    .section{margin:32px 0}
    .two-col{grid-template-columns:1fr 1fr}
    .list{display:grid; gap:12px; padding-left:0; margin:0; list-style:none}
    .item{padding:16px; border-radius:14px; background:#0f1422; border:1px solid rgba(255,255,255,.06)}
    .footer{padding:26px 0; color:var(--muted); border-top:1px solid rgba(255,255,255,.06); margin-top:28px}
    .chips{display:flex; flex-wrap:wrap; gap:8px}
    .chip{padding:8px 10px; border-radius:999px; border:1px solid rgba(255,255,255,.1); background:#0f1422; font-size:12px}
    .contact{display:grid; gap:12px}
    .socials{display:flex; gap:10px}
    .socials a{padding:10px 12px; border-radius:12px; border:1px solid rgba(255,255,255,.08); background:#121826}
    .notice{font-size:12px; color:#9aa5b8}
    @media (max-width: 900px){
      .hero-grid, .two-col{grid-template-columns:1fr}
      .kpis{grid-template-columns:1fr 1fr}
    }
    @media (max-width: 540px){
      h1{font-size:32px}
      .kpis{grid-template-columns:1fr}
    }
  </style>
  <script>
    // Smooth scroll for internal links
    addEventListener('DOMContentLoaded', () => {
      document.querySelectorAll('a[href^="#"]').forEach(a => {
        a.addEventListener('click', e => {
          const id = a.getAttribute('href');
          const el = document.querySelector(id);
          if(el){ e.preventDefault(); el.scrollIntoView({behavior:'smooth', block:'start'}); }
        })
      })
    });
  </script>
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Person",
    "name": "Atharva Sangale",
    "description": "Cloud/DevOps & Linux enthusiast. Security-focused. Job seeker.",
    "address": {
      "@type": "PostalAddress",
      "addressLocality": "Dodi Bk, Sinnar, Nashik",
      "addressRegion": "Maharashtra",
      "postalCode": "422606",
      "addressCountry": "IN"
    },
    "alumniOf": [
      {"@type":"EducationalOrganization", "name":"Shree Bramhanand New English School & Jr College, Dodi Bk"},
      {"@type":"CollegeOrUniversity", "name":"Shah & Anchor Kutchhi College of Engineering"}
    ],
    "knowsAbout": ["Linux","Docker","Jenkins","GitLab","Kubernetes","DNS","Cloud","Security Engineering"],
    "url": ""
  }
  </script>
</head>
<body>
  <header>
    <div class="container nav">
      <div class="brand">
        <div class="brand-logo">AS</div>
        <div>Atharva Sangale</div>
      </div>
      <nav>
        <ul>
          <li><a href="#about">About</a></li>
          <li><a href="#skills">Skills</a></li>
          <li><a href="#education">Education</a></li>
          <li><a href="#vlog">Vlog</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main class="container">
    <!-- HERO -->
    <section class="hero">
      <div class="grid hero-grid">
        <div class="card">
          <div class="card-inner">
            <span class="tag">Cloud · DevOps · Security</span>
            <h1>Hi, I’m Atharva —
              <br />Linux & DevOps enthusiast from Nashik, India.</h1>
            <p>
              I’m currently a <strong>job seeker</strong> looking for roles in <strong>Cloud/DevOps, Linux Administration, or Security Engineering</strong>.
              I enjoy building reliable infrastructure, securing deployments, and simplifying developer workflows.
            </p>
            <div class="chips" aria-label="key highlights">
              <span class="chip">Docker & Kubernetes</span>
              <span class="chip">CI/CD (Jenkins, GitLab)</span>
              <span class="chip">DNS & Networking</span>
              <span class="chip">AWS & EC2</span>
              <span class="chip">AdGuard Home + TLS</span>
            </div>
            <div style="margin-top:18px; display:flex; gap:12px; flex-wrap:wrap">
              <a class="btn" href="#contact">Hire Me</a>
              <a class="btn secondary" href="#projects">View Projects</a>
            </div>
            <div class="kpis">
              <div class="kpi"><div class="num">10+ </div><div class="txt">Mini Projects</div></div>
              <div class="kpi"><div class="num">7+</div><div class="txt">Core Skills</div></div>
              <div class="kpi"><div class="num">∞</div><div class="txt">Curiosity</div></div>
            </div>
          </div>
        </div>
        <aside class="card">
          <div class="card-inner">
            <h3>Quick Info</h3>
            <ul class="list">
              <li class="item"><strong>Location:</strong> Dodi Bk, Tal Sinnar, Dist Nashik, Maharashtra (422606), India</li>
              <li class="item"><strong>Interests:</strong> Cloud, DevOps, Security, Linux, Networking</li>
              <li class="item"><strong>Open to:</strong> Full‑time · Internship · Remote/On‑site</li>
              <li class="item"><strong>Status:</strong> Actively interviewing</li>
            </ul>
          </div>
        </aside>
      </div>
    </section>

    <!-- ABOUT -->
    <section id="about" class="section card">
      <div class="card-inner">
        <h2>About Me</h2>
        <p>
          I grew up in <strong>Dodi Bk village</strong> (Sinnar, Nashik) and studied at
          <strong>Shree Bramhanand New English School & Junior College</strong> (Dodi Bk) and
          <strong>Shah & Anchor Kutchhi College of Engineering</strong>.
          I love learning by doing — building homelabs on EC2, configuring DNS, and automating deployments.
        </p>
        <div class="tags">
          <span class="tag">Problem Solver</span>
          <span class="tag">Team Player</span>
          <span class="tag">Security Mindset</span>
          <span class="tag">Self‑Learner</span>
        </div>
      </div>
    </section>

    <!-- SKILLS -->
    <section id="skills" class="section">
      <div class="grid two-col">
        <div class="card">
          <div class="card-inner">
            <h2>Technical Skills</h2>
            <ul class="list">
              <li class="item"><strong>Linux & Shell</strong>: system administration, services, permissions, users/groups</li>
              <li class="item"><strong>Containers</strong>: Docker, images, volumes, networks; basics of Kubernetes</li>
              <li class="item"><strong>CI/CD</strong>: Jenkins pipelines, GitLab CI, GitHub Actions</li>
              <li class="item"><strong>Cloud</strong>: AWS EC2, security groups, key pairs, S3 static hosting</li>
              <li class="item"><strong>Networking & DNS</strong>: Route 53, DNS records, AdGuard Home; DoH/DoT</li>
              <li class="item"><strong>Security</strong>: least privilege, Secrets management, HTTPS/TLS basics</li>
              <li class="item"><strong>Languages</strong>: Bash, Python basics, Java (OOP), Dart/Flutter (apps)</li>
            </ul>
          </div>
        </div>
        <div class="card">
          <div class="card-inner">
            <h2>Highlights</h2>
            <ul class="list">
              <li class="item">Hosted AdGuard Home on EC2 with <em>HTTPS (DoH)</em> and <em>DNS‑over‑TLS</em>.</li>
              <li class="item">Built a Flutter app with <em>Firebase Auth</em>, role‑based navigation, and product comments/images.</li>
              <li class="item">Set up <em>MySQL replication</em> on Ubuntu EC2 (primary/replica).</li>
              <li class="item">Created CI/CD pipelines in <em>Jenkins</em> and <em>GitLab</em> for containerized apps.</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- EDUCATION -->
    <section id="education" class="section card">
      <div class="card-inner">
        <h2>Education</h2>
        <ul class="list">
          <li class="item"><strong>Shah & Anchor Kutchhi College of Engineering</strong> — Engineering graduate (Details/Year TBD)</li>
          <li class="item"><strong>Shree Bramhanand New English School & Jr College, Dodi Bk</strong> — Higher Secondary</li>
        </ul>
        <p class="notice">(You can update degree details and years later.)</p>
      </div>
    </section>

    <!-- PROJECTS (Optional Showcase) -->
    <section id="projects" class="section">
      <div class="grid two-col">
        <article class="card">
          <div class="card-inner">
            <h3>AdGuard Home on EC2 with DoH/DoT</h3>
            <p>Deployed AdGuard Home behind HTTPS using Let’s Encrypt, enabled DNS‑over‑HTTPS and DNS‑over‑TLS, and verified with curl/dig.</p>
            <div class="chips">
              <span class="chip">EC2</span><span class="chip">Route 53</span><span class="chip">TLS</span><span class="chip">Linux</span>
            </div>
          </div>
        </article>
        <article class="card">
          <div class="card-inner">
            <h3>Flutter App: Product Reviews + Images</h3>
            <p>Built ChemicalDetailPage showing ratings, comments, and user‑uploaded images; stored in Firestore under <code>userC&I</code>.</p>
            <div class="chips">
              <span class="chip">Flutter</span><span class="chip">Firebase</span><span class="chip">UI/UX</span>
            </div>
          </div>
        </article>
      </div>
    </section>

    <!-- VLOG -->
    <section id="vlog" class="section card">
      <div class="card-inner">
        <h2>Vlog</h2>
        <p>An emotional story about my background and journey is coming soon. I’ll share lessons from Dodi Bk to engineering college and beyond.</p>
        <p class="notice">(You can embed a YouTube video or write posts here later.)</p>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" class="section card">
      <div class="card-inner">
        <h2>Contact</h2>
        <div class="contact">
          <p>Interested in working together or have an opportunity? Reach out:</p>
          <ul class="list">
            <li class="item"><strong>Email:</strong> <a href="mailto:youremail@example.com">youremail@example.com</a> (replace with your real email)</li>
            <li class="item"><strong>Resume/CV:</strong> <a href="#" onclick="alert('Replace this link with your Google Drive or PDF resume URL.')">Download PDF</a></li>
            <li class="item"><strong>Location:</strong> Nashik, Maharashtra, India (Open to relocate)</li>
          </ul>
          <div class="socials">
            <a href="#" title="GitHub">GitHub</a>
            <a href="#" title="LinkedIn">LinkedIn</a>
            <a href="#" title="Twitter/X">Twitter</a>
          </div>
          <p class="notice">Tip: Update the email and social links above before publishing.</p>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="container" style="padding:0">
        © <span id="y"></span> Atharva Sangale • Built with HTML/CSS
      </div>
    </footer>
  </main>

  <script>document.getElementById('y').textContent = new Date().getFullYear()</script>
</body>
</html>

```

![image alt](https://github.com/atharvasangale7/LoadBalancing/blob/256e2eb2f176d8bf991984fe48d134e9b7080b2e/Screenshot%202025-08-27%20103943.png)
![image alt](https://github.com/atharvasangale7/LoadBalancing/blob/256e2eb2f176d8bf991984fe48d134e9b7080b2e/Screenshot%202025-08-27%20103957.png)
![image alt](https://github.com/atharvasangale7/LoadBalancing/blob/256e2eb2f176d8bf991984fe48d134e9b7080b2e/Screenshot%202025-08-27%20104015.png)
![image alt](https://github.com/atharvasangale7/LoadBalancing/blob/256e2eb2f176d8bf991984fe48d134e9b7080b2e/Screenshot%202025-08-27%20104039.png)

