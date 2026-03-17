<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>README — Akisa Vujel Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&family=DM+Sans:wght@300;400;500&family=DM+Mono&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #0e0c0a;
      --surface: #161310;
      --card: #1c1915;
      --border: #2e2923;
      --accent: #c9954a;
      --accent-light: #e8b97a;
      --accent-dim: rgba(201,149,74,0.12);
      --text: #e8e0d4;
      --text-muted: #8a7f72;
      --text-dim: #5a5248;
      --heading-font: 'Playfair Display', Georgia, serif;
      --body-font: 'DM Sans', sans-serif;
      --mono-font: 'DM Mono', monospace;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--body-font);
      font-weight: 300;
      line-height: 1.75;
      min-height: 100vh;
      padding: 60px 24px 100px;
    }

    /* Subtle grain overlay */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 0;
      opacity: 0.4;
    }

    .page {
      max-width: 780px;
      margin: 0 auto;
      position: relative;
      z-index: 1;
    }

    /* ── Header ── */
    .readme-header {
      border: 1px solid var(--border);
      border-radius: 2px;
      padding: 48px 52px;
      background: var(--surface);
      margin-bottom: 4px;
      position: relative;
      overflow: hidden;
      animation: fadeUp 0.6s ease both;
    }

    .readme-header::after {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 2px;
      background: linear-gradient(90deg, transparent, var(--accent), transparent);
    }

    .file-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-family: var(--mono-font);
      font-size: 0.7rem;
      color: var(--text-dim);
      letter-spacing: 0.1em;
      text-transform: uppercase;
      margin-bottom: 20px;
    }

    .file-badge::before {
      content: '';
      width: 6px; height: 6px;
      border-radius: 50%;
      background: var(--accent);
      box-shadow: 0 0 8px var(--accent);
    }

    .readme-header h1 {
      font-family: var(--heading-font);
      font-size: clamp(1.8rem, 4vw, 2.6rem);
      font-weight: 700;
      color: var(--text);
      line-height: 1.2;
      margin-bottom: 10px;
    }

    .readme-header h1 span {
      color: var(--accent);
    }

    .tagline {
      font-size: 0.95rem;
      color: var(--text-muted);
      font-weight: 300;
    }

    .live-link {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      margin-top: 24px;
      padding: 9px 20px;
      background: var(--accent-dim);
      border: 1px solid var(--accent);
      border-radius: 2px;
      color: var(--accent-light);
      text-decoration: none;
      font-size: 0.85rem;
      font-family: var(--mono-font);
      transition: background 0.2s, color 0.2s;
    }

    .live-link:hover {
      background: rgba(201,149,74,0.22);
      color: #fff;
    }

    .live-link svg { width: 14px; height: 14px; fill: currentColor; }

    /* ── Sections ── */
    .section {
      border: 1px solid var(--border);
      border-radius: 2px;
      background: var(--surface);
      margin-bottom: 4px;
      overflow: hidden;
      animation: fadeUp 0.6s ease both;
    }

    .section:nth-child(2) { animation-delay: 0.1s; }
    .section:nth-child(3) { animation-delay: 0.18s; }
    .section:nth-child(4) { animation-delay: 0.26s; }
    .section:nth-child(5) { animation-delay: 0.34s; }

    .section-header {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 18px 52px;
      border-bottom: 1px solid var(--border);
      background: var(--card);
    }

    .section-icon {
      font-size: 1rem;
      width: 28px;
      text-align: center;
    }

    .section-header h2 {
      font-family: var(--heading-font);
      font-size: 1rem;
      font-weight: 600;
      color: var(--accent-light);
      letter-spacing: 0.02em;
    }

    .section-body {
      padding: 32px 52px;
    }

    .section-body p {
      font-size: 0.95rem;
      color: var(--text-muted);
      max-width: 600px;
    }

    /* ── Skills ── */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 3px;
    }

    .skill-group {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 2px;
      padding: 20px 22px;
    }

    .skill-group-title {
      font-size: 0.72rem;
      font-family: var(--mono-font);
      color: var(--accent);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 12px;
    }

    .skill-tag {
      display: inline-block;
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--border);
      color: var(--text-muted);
      font-size: 0.78rem;
      padding: 3px 10px;
      border-radius: 2px;
      margin: 3px 3px 3px 0;
      font-family: var(--mono-font);
      transition: border-color 0.2s, color 0.2s;
    }

    .skill-tag:hover {
      border-color: var(--accent);
      color: var(--accent-light);
    }

    /* ── Built With ── */
    .built-list {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .built-item {
      display: flex;
      align-items: center;
      gap: 8px;
      padding: 8px 16px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 2px;
      font-size: 0.85rem;
      color: var(--text-muted);
    }

    .built-item::before {
      content: '▸';
      color: var(--accent);
      font-size: 0.7rem;
    }

    /* ── Contact ── */
    .contact-grid {
      display: grid;
      gap: 3px;
    }

    .contact-row {
      display: flex;
      align-items: center;
      gap: 0;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 2px;
      overflow: hidden;
      transition: border-color 0.2s;
      text-decoration: none;
    }

    .contact-row:hover {
      border-color: var(--accent);
    }

    .contact-platform {
      font-family: var(--mono-font);
      font-size: 0.72rem;
      color: var(--accent);
      letter-spacing: 0.1em;
      text-transform: uppercase;
      padding: 14px 20px;
      width: 120px;
      flex-shrink: 0;
      border-right: 1px solid var(--border);
    }

    .contact-value {
      padding: 14px 20px;
      font-size: 0.88rem;
      color: var(--text-muted);
      transition: color 0.2s;
    }

    .contact-row:hover .contact-value {
      color: var(--accent-light);
    }

    /* ── Footer ── */
    .readme-footer {
      text-align: center;
      padding: 40px 0 0;
      font-size: 0.8rem;
      color: var(--text-dim);
      font-family: var(--mono-font);
      animation: fadeUp 0.6s 0.4s ease both;
    }

    .readme-footer span {
      color: var(--accent);
    }

    /* ── Animation ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(18px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ── Responsive ── */
    @media (max-width: 600px) {
      .readme-header, .section-header, .section-body { padding-left: 24px; padding-right: 24px; }
      .skills-grid { grid-template-columns: 1fr 1fr; }
      .contact-platform { width: 90px; font-size: 0.65rem; }
    }
  </style>
</head>
<body>
<div class="page">

  <!-- Header -->
  <div class="readme-header">
    <div class="file-badge">README.md</div>
    <h1>Akisa Vujel — <span>Data Analyst</span> Portfolio</h1>
    <p class="tagline">Welcome to my personal portfolio repository.</p>
    <a href="https://akisavujel.github.io/Portfolio/" target="_blank" class="live-link">
      <svg viewBox="0 0 24 24"><path d="M14 3h7v7l-2-2-8 8-3-3 8-8-2-2zm-4 2H5a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2v-5l-2 2v3H5V7h3l2-2z"/></svg>
      akisavujel.github.io/Portfolio
    </a>
  </div>

  <!-- About -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">👩‍💻</span>
      <h2>About Me</h2>
    </div>
    <div class="section-body">
      <p>I'm a second-year Bachelor of Information Technology (BIT) student with a strong passion for data analysis and problem-solving. I work with structured datasets using Python, SQL, Excel, and Tableau to extract meaningful insights and support data-driven decisions. I enjoy turning raw data into clear visualizations, interactive dashboards, and analytical reports.</p>
    </div>
  </div>

  <!-- Skills -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">🛠</span>
      <h2>Technical Skills</h2>
    </div>
    <div class="section-body">
      <div class="skills-grid">
        <div class="skill-group">
          <div class="skill-group-title">Programming</div>
          <span class="skill-tag">Python</span>
          <span class="skill-tag">SQL</span>
          <span class="skill-tag">MySQL</span>
        </div>
        <div class="skill-group">
          <div class="skill-group-title">Analysis</div>
          <span class="skill-tag">Pandas</span>
          <span class="skill-tag">Matplotlib</span>
          <span class="skill-tag">Seaborn</span>
          <span class="skill-tag">EDA</span>
        </div>
        <div class="skill-group">
          <div class="skill-group-title">Visualization</div>
          <span class="skill-tag">Tableau</span>
          <span class="skill-tag">Excel</span>
          <span class="skill-tag">Pivot Tables</span>
        </div>
        <div class="skill-group">
          <div class="skill-group-title">Web</div>
          <span class="skill-tag">HTML</span>
          <span class="skill-tag">CSS</span>
        </div>
        <div class="skill-group">
          <div class="skill-group-title">Tools</div>
          <span class="skill-tag">Jupyter</span>
          <span class="skill-tag">Git</span>
          <span class="skill-tag">GitHub</span>
          <span class="skill-tag">Kaggle</span>
          <span class="skill-tag">Google Sheets</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Built With -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">🏗</span>
      <h2>Built With</h2>
    </div>
    <div class="section-body">
      <div class="built-list">
        <div class="built-item">HTML5 & CSS3</div>
        <div class="built-item">Responsive Design</div>
        <div class="built-item">GitHub Pages</div>
      </div>
    </div>
  </div>

  <!-- Contact -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">📬</span>
      <h2>Contact</h2>
    </div>
    <div class="section-body">
      <div class="contact-grid">
        <a href="mailto:akishabhujel@gmail.com" class="contact-row">
          <span class="contact-platform">📧 Email</span>
          <span class="contact-value">akishabhujel@gmail.com</span>
        </a>
        <a href="https://www.linkedin.com/in/akisa-vujel-5437843a2/" target="_blank" class="contact-row">
          <span class="contact-platform">💼 LinkedIn</span>
          <span class="contact-value">linkedin.com/in/akisa-vujel</span>
        </a>
        <a href="https://www.kaggle.com/akisavujel" target="_blank" class="contact-row">
          <span class="contact-platform">📊 Kaggle</span>
          <span class="contact-value">kaggle.com/akisavujel</span>
        </a>
        <a href="https://github.com/akisavujel" target="_blank" class="contact-row">
          <span class="contact-platform">🐙 GitHub</span>
          <span class="contact-value">github.com/akisavujel</span>
        </a>
        <a href="https://hashnode.com/@akisavujel" target="_blank" class="contact-row">
          <span class="contact-platform">✍️ Hashnode</span>
          <span class="contact-value">hashnode.com/@akisavujel</span>
        </a>
      </div>
    </div>
  </div>

  <div class="readme-footer">
    <span>⭐</span> Thanks for visiting — feel free to explore or reach out.
  </div>

</div>
</body>
</html>
