<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>داود | باحث أمن سيبراني</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&family=Orbitron:wght@400;700;900&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg: #050a0f;
      --bg2: #080e15;
      --surface: #0d1620;
      --surface2: #111c2a;
      --accent: #00d4ff;
      --accent2: #0ff;
      --green: #00ff88;
      --red: #ff3355;
      --text: #e2eaf5;
      --muted: #6b8299;
      --border: rgba(0,212,255,0.15);
      --glow: 0 0 20px rgba(0,212,255,0.3);
      --glow2: 0 0 40px rgba(0,212,255,0.15);
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Cairo', sans-serif;
      overflow-x: hidden;
      cursor: none;
    }

    /* Custom cursor */
    .cursor {
      position: fixed;
      width: 12px; height: 12px;
      background: var(--accent);
      border-radius: 50%;
      pointer-events: none;
      z-index: 9999;
      transition: transform 0.1s, opacity 0.2s;
      mix-blend-mode: screen;
    }
    .cursor-ring {
      position: fixed;
      width: 36px; height: 36px;
      border: 1px solid rgba(0,212,255,0.5);
      border-radius: 50%;
      pointer-events: none;
      z-index: 9998;
      transition: transform 0.15s ease, width 0.2s, height 0.2s;
    }

    /* Noise overlay */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 1;
      opacity: 0.4;
    }

    /* ─── NAVBAR ─── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 18px 40px;
      background: rgba(5,10,15,0.85);
      backdrop-filter: blur(20px);
      border-bottom: 1px solid var(--border);
    }
    .nav-logo {
      font-family: 'Orbitron', sans-serif;
      font-weight: 900;
      font-size: 1.2rem;
      color: var(--accent);
      text-shadow: var(--glow);
      letter-spacing: 2px;
    }
    .nav-links {
      display: flex;
      gap: 32px;
      list-style: none;
    }
    .nav-links a {
      color: var(--muted);
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 600;
      transition: color 0.2s;
      position: relative;
    }
    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -4px; right: 0;
      width: 0; height: 1px;
      background: var(--accent);
      transition: width 0.3s;
    }
    .nav-links a:hover { color: var(--accent); }
    .nav-links a:hover::after { width: 100%; }

    .nav-badge {
      display: flex;
      align-items: center;
      gap: 8px;
      background: rgba(0,212,255,0.08);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 6px 16px;
      font-size: 0.8rem;
      color: var(--accent);
    }
    .status-dot {
      width: 7px; height: 7px;
      background: var(--green);
      border-radius: 50%;
      animation: pulse-dot 2s ease infinite;
    }
    @keyframes pulse-dot {
      0%, 100% { opacity: 1; box-shadow: 0 0 0 0 rgba(0,255,136,0.4); }
      50% { opacity: 0.7; box-shadow: 0 0 0 6px rgba(0,255,136,0); }
    }

    /* ─── HERO ─── */
    #hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      overflow: hidden;
      padding: 120px 40px 60px;
    }

    .hero-bg-grid {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(0,212,255,0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,212,255,0.04) 1px, transparent 1px);
      background-size: 50px 50px;
      mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 30%, transparent 100%);
    }

    .hero-glow-1 {
      position: absolute;
      width: 600px; height: 600px;
      background: radial-gradient(circle, rgba(0,212,255,0.08) 0%, transparent 70%);
      top: -100px; right: -100px;
      animation: float1 8s ease-in-out infinite;
    }
    .hero-glow-2 {
      position: absolute;
      width: 400px; height: 400px;
      background: radial-gradient(circle, rgba(0,255,136,0.06) 0%, transparent 70%);
      bottom: 0; left: 100px;
      animation: float2 10s ease-in-out infinite;
    }
    @keyframes float1 { 0%, 100% { transform: translateY(0) scale(1); } 50% { transform: translateY(-30px) scale(1.05); } }
    @keyframes float2 { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(20px); } }

    .hero-content {
      position: relative;
      z-index: 2;
      max-width: 900px;
      text-align: center;
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: rgba(0,212,255,0.07);
      border: 1px solid rgba(0,212,255,0.2);
      border-radius: 30px;
      padding: 8px 20px;
      font-size: 0.8rem;
      color: var(--accent);
      letter-spacing: 2px;
      text-transform: uppercase;
      margin-bottom: 28px;
      animation: fadeUp 0.8s ease both;
    }
    .hero-tag-icon { font-size: 1rem; }

    .hero-name {
      font-family: 'Cairo', sans-serif;
      font-size: clamp(2.8rem, 7vw, 5.5rem);
      font-weight: 900;
      line-height: 1.1;
      margin-bottom: 12px;
      animation: fadeUp 0.8s 0.1s ease both;
    }
    .hero-name span {
      background: linear-gradient(135deg, #fff 30%, var(--accent) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .hero-handle {
      font-family: 'Orbitron', sans-serif;
      font-size: clamp(1rem, 2.5vw, 1.4rem);
      color: var(--accent);
      letter-spacing: 4px;
      margin-bottom: 24px;
      animation: fadeUp 0.8s 0.2s ease both;
      text-shadow: var(--glow);
    }

    .hero-bio {
      max-width: 600px;
      margin: 0 auto 40px;
      color: var(--muted);
      font-size: 1.05rem;
      line-height: 1.8;
      font-weight: 400;
      animation: fadeUp 0.8s 0.3s ease both;
    }

    .hero-ctas {
      display: flex;
      gap: 16px;
      justify-content: center;
      flex-wrap: wrap;
      animation: fadeUp 0.8s 0.4s ease both;
    }

    .btn-primary {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: var(--accent);
      color: #000;
      font-family: 'Cairo', sans-serif;
      font-weight: 700;
      font-size: 0.95rem;
      padding: 14px 32px;
      border-radius: 6px;
      text-decoration: none;
      border: none;
      cursor: none;
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(0,212,255,0.4); }

    .btn-ghost {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: transparent;
      color: var(--text);
      font-family: 'Cairo', sans-serif;
      font-weight: 600;
      font-size: 0.95rem;
      padding: 14px 32px;
      border-radius: 6px;
      text-decoration: none;
      border: 1px solid var(--border);
      cursor: none;
      transition: border-color 0.2s, color 0.2s, transform 0.2s;
    }
    .btn-ghost:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }

    .hero-scroll {
      position: absolute;
      bottom: 30px; left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
      color: var(--muted);
      font-size: 0.75rem;
      animation: fadeUp 1s 1s ease both;
    }
    .scroll-line {
      width: 1px; height: 40px;
      background: linear-gradient(to bottom, var(--accent), transparent);
      animation: scrollAnim 2s ease-in-out infinite;
    }
    @keyframes scrollAnim { 0%, 100% { opacity: 1; } 50% { opacity: 0.3; } }

    /* ─── STATS STRIP ─── */
    .stats-strip {
      background: var(--surface);
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
      padding: 32px 40px;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
      gap: 24px;
    }
    .stat-item {
      text-align: center;
      position: relative;
    }
    .stat-item + .stat-item::before {
      content: '';
      position: absolute;
      right: 0; top: 50%;
      transform: translateY(-50%);
      width: 1px; height: 40px;
      background: var(--border);
    }
    .stat-num {
      font-family: 'Orbitron', sans-serif;
      font-size: 2rem;
      font-weight: 900;
      color: var(--accent);
      text-shadow: var(--glow);
      display: block;
    }
    .stat-label { color: var(--muted); font-size: 0.8rem; margin-top: 4px; display: block; }

    /* ─── SECTION COMMON ─── */
    section {
      padding: 100px 40px;
      max-width: 1100px;
      margin: 0 auto;
    }
    .section-header {
      margin-bottom: 60px;
      display: flex;
      align-items: center;
      gap: 20px;
    }
    .section-tag {
      font-family: 'Orbitron', sans-serif;
      font-size: 0.65rem;
      letter-spacing: 3px;
      color: var(--accent);
      text-transform: uppercase;
      writing-mode: vertical-rl;
    }
    .section-title {
      font-size: clamp(1.8rem, 4vw, 2.8rem);
      font-weight: 900;
      line-height: 1.2;
    }
    .section-title em {
      font-style: normal;
      color: var(--accent);
    }
    .section-line {
      flex: 1;
      height: 1px;
      background: linear-gradient(to left, transparent, var(--border));
    }

    /* ─── ABOUT ─── */
    #about .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 60px;
      align-items: center;
    }
    .about-visual {
      position: relative;
    }
    .about-avatar-wrap {
      position: relative;
      width: 280px; height: 280px;
      margin: 0 auto;
    }
    .about-avatar {
      width: 100%; height: 100%;
      border-radius: 20px;
      background: var(--surface2);
      border: 1px solid var(--border);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 5rem;
      position: relative;
      overflow: hidden;
    }
    .about-avatar::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(0,212,255,0.1) 0%, transparent 60%);
    }
    .avatar-ring {
      position: absolute;
      inset: -15px;
      border: 1px solid rgba(0,212,255,0.2);
      border-radius: 28px;
      animation: ringRotate 8s linear infinite;
    }
    .avatar-ring-2 {
      position: absolute;
      inset: -30px;
      border: 1px dashed rgba(0,212,255,0.1);
      border-radius: 40px;
      animation: ringRotate 12s linear infinite reverse;
    }
    @keyframes ringRotate { to { transform: rotate(360deg); } }

    .about-badge {
      position: absolute;
      bottom: -15px; left: -20px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 12px 18px;
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 0.82rem;
      color: var(--text);
      box-shadow: 0 8px 30px rgba(0,0,0,0.5);
    }
    .badge-icon { font-size: 1.3rem; }

    .about-text p {
      color: var(--muted);
      line-height: 1.9;
      font-size: 1rem;
      margin-bottom: 20px;
    }
    .about-text p strong { color: var(--text); }

    .about-skills {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 28px;
    }
    .skill-chip {
      background: rgba(0,212,255,0.07);
      border: 1px solid rgba(0,212,255,0.15);
      color: var(--accent);
      border-radius: 4px;
      padding: 6px 14px;
      font-size: 0.82rem;
      font-weight: 600;
      transition: background 0.2s, transform 0.2s;
    }
    .skill-chip:hover { background: rgba(0,212,255,0.15); transform: translateY(-2px); }

    /* ─── PLATFORMS ─── */
    #platforms .platforms-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 20px;
    }
    .platform-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 28px;
      text-decoration: none;
      transition: border-color 0.2s, transform 0.2s, box-shadow 0.2s;
      display: block;
      position: relative;
      overflow: hidden;
    }
    .platform-card::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(0,212,255,0.05) 0%, transparent 60%);
      opacity: 0;
      transition: opacity 0.2s;
    }
    .platform-card:hover::before { opacity: 1; }
    .platform-card:hover {
      border-color: rgba(0,212,255,0.4);
      transform: translateY(-4px);
      box-shadow: var(--glow2);
    }
    .platform-icon { font-size: 2.2rem; margin-bottom: 16px; }
    .platform-name {
      font-size: 1.1rem;
      font-weight: 700;
      color: var(--text);
      margin-bottom: 8px;
    }
    .platform-handle {
      color: var(--accent);
      font-size: 0.85rem;
      font-family: 'Orbitron', sans-serif;
      margin-bottom: 10px;
    }
    .platform-desc { color: var(--muted); font-size: 0.88rem; line-height: 1.6; }
    .platform-arrow {
      position: absolute;
      top: 24px; left: 24px;
      color: var(--muted);
      font-size: 1.2rem;
      transition: color 0.2s, transform 0.2s;
    }
    .platform-card:hover .platform-arrow { color: var(--accent); transform: translate(-3px, -3px); }

    /* ─── ACHIEVEMENTS ─── */
    #achievements .achievements-list {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }
    .achievement-item {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 22px 28px;
      display: flex;
      align-items: center;
      gap: 20px;
      transition: border-color 0.2s, transform 0.2s;
    }
    .achievement-item:hover { border-color: rgba(0,212,255,0.35); transform: translateX(-6px); }
    .achievement-icon {
      font-size: 1.8rem;
      min-width: 48px;
      text-align: center;
    }
    .achievement-content h4 { font-size: 1rem; font-weight: 700; margin-bottom: 4px; }
    .achievement-content p { color: var(--muted); font-size: 0.88rem; }
    .achievement-badge {
      margin-right: auto;
      background: rgba(0,255,136,0.1);
      border: 1px solid rgba(0,255,136,0.2);
      color: var(--green);
      border-radius: 20px;
      padding: 4px 14px;
      font-size: 0.75rem;
      font-weight: 700;
      white-space: nowrap;
    }

    /* ─── CONTACT ─── */
    #contact {
      text-align: center;
    }
    .contact-box {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 60px 40px;
      position: relative;
      overflow: hidden;
    }
    .contact-box::before {
      content: '';
      position: absolute;
      top: -60px; right: -60px;
      width: 300px; height: 300px;
      background: radial-gradient(circle, rgba(0,212,255,0.08) 0%, transparent 70%);
    }
    .contact-title {
      font-size: clamp(1.6rem, 4vw, 2.5rem);
      font-weight: 900;
      margin-bottom: 16px;
    }
    .contact-sub { color: var(--muted); margin-bottom: 40px; font-size: 1rem; }
    .social-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      justify-content: center;
    }
    .social-btn {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: var(--surface2);
      border: 1px solid var(--border);
      color: var(--text);
      border-radius: 8px;
      padding: 12px 24px;
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 600;
      transition: border-color 0.2s, color 0.2s, transform 0.2s, background 0.2s;
    }
    .social-btn:hover {
      border-color: var(--accent);
      color: var(--accent);
      background: rgba(0,212,255,0.06);
      transform: translateY(-2px);
    }
    .social-btn-icon { font-size: 1.1rem; }

    /* ─── TERMINAL ─── */
    .terminal {
      background: #0a0f16;
      border: 1px solid rgba(0,212,255,0.2);
      border-radius: 12px;
      padding: 20px 24px;
      font-family: 'Courier New', monospace;
      font-size: 0.85rem;
      line-height: 2;
      margin-top: 40px;
      position: relative;
    }
    .terminal-bar {
      display: flex;
      gap: 7px;
      margin-bottom: 16px;
    }
    .terminal-dot { width: 11px; height: 11px; border-radius: 50%; }
    .terminal-dot:nth-child(1) { background: #ff5f57; }
    .terminal-dot:nth-child(2) { background: #ffbd2e; }
    .terminal-dot:nth-child(3) { background: #28c840; }
    .t-prompt { color: var(--green); }
    .t-cmd { color: var(--text); }
    .t-comment { color: var(--muted); }
    .t-val { color: var(--accent); }
    .t-str { color: #ff9e64; }
    .cursor-blink {
      display: inline-block;
      width: 8px; height: 1em;
      background: var(--accent);
      animation: blink 1s step-end infinite;
      vertical-align: text-bottom;
    }
    @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }

    /* ─── FOOTER ─── */
    footer {
      background: var(--surface);
      border-top: 1px solid var(--border);
      padding: 30px 40px;
      text-align: center;
      color: var(--muted);
      font-size: 0.85rem;
    }
    footer span { color: var(--accent); }

    /* ─── ANIMATIONS ─── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }
    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ─── MOBILE ─── */
    .hamburger {
      display: none;
      flex-direction: column;
      gap: 5px;
      cursor: pointer;
      padding: 4px;
    }
    .hamburger span {
      display: block;
      width: 24px; height: 2px;
      background: var(--text);
      border-radius: 2px;
      transition: 0.3s;
    }

    @media (max-width: 768px) {
      nav { padding: 16px 20px; }
      .nav-links { display: none; }
      .nav-badge { display: none; }
      .hamburger { display: flex; }

      #hero { padding: 100px 20px 60px; }
      section { padding: 70px 20px; }

      #about .about-grid { grid-template-columns: 1fr; gap: 40px; }
      .about-avatar-wrap { width: 200px; height: 200px; }

      .stats-strip { padding: 24px 20px; }
      .stat-item + .stat-item::before { display: none; }

      .section-header { flex-direction: column; align-items: flex-start; gap: 10px; }
      .section-tag { writing-mode: horizontal-tb; }
      .section-line { display: none; }

      .contact-box { padding: 40px 20px; }
    }

    /* ─── GLITCH on name ─── */
    .glitch {
      position: relative;
    }
    .glitch::before, .glitch::after {
      content: attr(data-text);
      position: absolute;
      top: 0; left: 0; right: 0;
      background: linear-gradient(135deg, #fff 30%, var(--accent) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .glitch::before {
      animation: glitch1 4s 2s infinite;
      clip-path: polygon(0 0, 100% 0, 100% 35%, 0 35%);
      transform: translateX(-2px);
      opacity: 0;
    }
    .glitch::after {
      animation: glitch2 4s 2s infinite;
      clip-path: polygon(0 65%, 100% 65%, 100% 100%, 0 100%);
      transform: translateX(2px);
      opacity: 0;
    }
    @keyframes glitch1 {
      0%, 90%, 100% { opacity: 0; }
      92% { opacity: 1; transform: translateX(-3px) skew(-1deg); }
      94% { opacity: 0; }
    }
    @keyframes glitch2 {
      0%, 90%, 100% { opacity: 0; }
      93% { opacity: 1; transform: translateX(3px) skew(1deg); }
      95% { opacity: 0; }
    }

    /* ─── MOBILE NAV OPEN ─── */
    .mobile-nav {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(5,10,15,0.97);
      z-index: 99;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 32px;
    }
    .mobile-nav.open { display: flex; }
    .mobile-nav a {
      color: var(--text);
      text-decoration: none;
      font-size: 1.5rem;
      font-weight: 700;
      transition: color 0.2s;
    }
    .mobile-nav a:hover { color: var(--accent); }
    .mobile-nav-close {
      position: absolute;
      top: 20px; right: 20px;
      background: none;
      border: none;
      color: var(--text);
      font-size: 1.5rem;
      cursor: pointer;
    }
  </style>
</head>
<body>

<!-- Cursor -->
<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- Mobile Nav -->
<div class="mobile-nav" id="mobileNav">
  <button class="mobile-nav-close" onclick="closeMobileNav()">✕</button>
  <a href="#about" onclick="closeMobileNav()">عني</a>
  <a href="#platforms" onclick="closeMobileNav()">حساباتي</a>

  <a href="#contact" onclick="closeMobileNav()">تواصل</a>
</div>

<!-- NAVBAR -->
<nav>
  <div class="nav-logo">DAWOOD</div>
  <ul class="nav-links">
    <li><a href="#about">عني</a></li>
    <li><a href="#platforms">حساباتي</a></li>

    <li><a href="#contact">تواصل</a></li>
  </ul>
  <div class="nav-badge">
    <span class="status-dot"></span>
    متاح للتعاون
  </div>
  <div class="hamburger" onclick="openMobileNav()">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg-grid"></div>
  <div class="hero-glow-1"></div>
  <div class="hero-glow-2"></div>
  <div class="hero-content">
    <div class="hero-tag">
      <span class="hero-tag-icon">🛡️</span>
      باحث أمن سيبراني · Bug Bounty Hunter
    </div>
    <h1 class="hero-name glitch" data-text="داوود الجريد">
      <span>داوود الجريد</span>
    </h1>
    <div class="hero-handle">@dawoodf96 · @rmaad</div>
    <p class="hero-bio">
      باحث في <strong>الأمن السيبراني</strong> واصطياد الثغرات على المنصات الوطنية والعالمية.
      أعمل على اكتشاف الثغرات الأمنية وحمايتها لصون البنية الرقمية للمملكة والمؤسسات حول العالم.
    </p>
    <div class="hero-ctas">
      <a href="#contact" class="btn-primary">🤝 تواصل معي</a>

    </div>
  </div>
  <div class="hero-scroll">
    <span>اسحب للأسفل</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- STATS STRIP -->
<div class="stats-strip">
  <div class="stat-item reveal">
    <span class="stat-num" data-target="50">0</span>
    <span class="stat-label">+ ثغرة مكتشفة</span>
  </div>
  <div class="stat-item reveal">
    <span class="stat-num" data-target="15">0</span>
    <span class="stat-label">+ برنامج Bug Bounty</span>
  </div>
  <div class="stat-item reveal">
    <span class="stat-num" data-target="3">0</span>
    <span class="stat-label">سنوات خبرة</span>
  </div>
  <div class="stat-item reveal">
    <span class="stat-num">🏅</span>
    <span class="stat-label">Hall of Fame</span>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="section-header">
    <div class="section-tag">ABOUT</div>
    <h2 class="section-title">من <em>أنا</em></h2>
    <div class="section-line"></div>
  </div>
  <div class="about-grid">
    <div class="about-visual reveal">
      <div class="about-avatar-wrap">
        <div class="about-avatar">🧑‍💻</div>
        <div class="avatar-ring"></div>
        <div class="avatar-ring-2"></div>
        <div class="about-badge">
          <span class="badge-icon">🇸🇦</span>
          <div>
            <div style="font-weight:700;font-size:0.8rem;">المملكة العربية السعودية</div>
            <div style="color:var(--muted);font-size:0.75rem;">Cybersecurity Researcher</div>
          </div>
        </div>
      </div>
      <div class="terminal" style="margin-top:50px;">
        <div class="terminal-bar">
          <div class="terminal-dot"></div>
          <div class="terminal-dot"></div>
          <div class="terminal-dot"></div>
        </div>
        <div><span class="t-prompt">~$ </span><span class="t-cmd">whoami</span></div>
        <div><span class="t-val">dawoodf96</span> <span class="t-comment">// @rmaad on bugbounty.sa</span></div>
        <div><span class="t-prompt">~$ </span><span class="t-cmd">cat role.txt</span></div>
        <div><span class="t-str">"Bug Bounty Hunter &amp; Security Researcher"</span></div>
        <div><span class="t-prompt">~$ </span><span class="t-cmd">ls skills/</span></div>
        <div><span class="t-val">web-pentesting</span> <span class="t-val">recon</span> <span class="t-val">xss</span> <span class="t-val">sqli</span></div>
        <div><span class="t-prompt">~$ </span><span class="cursor-blink"></span></div>
      </div>
    </div>
    <div class="about-text reveal">
      <p>
        مرحباً، أنا <strong>داوود الجريد</strong> — باحث متخصص في <strong>اختبار الاختراق</strong>
        واكتشاف الثغرات الأمنية في التطبيقات والمواقع الإلكترونية.
        أنشط على منصة <strong>bugbounty.sa</strong> الوطنية التابعة لاتحاد الفضاء والأمن السيبراني
        والبرمجة بالمملكة العربية السعودية.
      </p>
      <p>
        أسعى دائماً لتعزيز أمان الفضاء الرقمي من خلال الإبلاغ المسؤول عن الثغرات،
        والمساهمة في حماية مواقع الجهات الحكومية والخاصة.
        أؤمن بأن الأمن السيبراني مسؤولية وطنية قبل أن يكون مهنة.
      </p>
      <p>
        أيضاً أشارك محتواي وتجربتي على منصة <strong>Creators.sa</strong>
        للوصول للمهتمين بمجال الأمن السيبراني وتبادل المعرفة.
      </p>
      <div class="about-skills">
        <span class="skill-chip">Web Application Pentesting</span>
        <span class="skill-chip">Bug Bounty</span>
        <span class="skill-chip">XSS</span>
        <span class="skill-chip">SQL Injection</span>
        <span class="skill-chip">Recon & OSINT</span>
        <span class="skill-chip">IDOR</span>
        <span class="skill-chip">API Security</span>
        <span class="skill-chip">Burp Suite</span>
        <span class="skill-chip">Linux</span>
        <span class="skill-chip">Network Security</span>
      </div>
    </div>
  </div>
</section>

<!-- PLATFORMS -->
<section id="platforms" style="background:var(--surface);border-radius:0;max-width:100%;padding:100px 0;">
  <div style="max-width:1100px;margin:0 auto;padding:0 40px;">
    <div class="section-header">
      <div class="section-tag">LINKS</div>
      <h2 class="section-title">حساباتي <em>ومنصاتي</em></h2>
      <div class="section-line"></div>
    </div>
    <div class="platforms-grid">
      <a href="https://creators.sa/dawoodf96" target="_blank" class="platform-card reveal">
        <div class="platform-arrow">↗</div>
        <div class="platform-icon">🌐</div>
        <div class="platform-name">Creators.sa</div>
        <div class="platform-handle">@dawoodf96</div>
        <p class="platform-desc">منصتي على Creators — جميع حساباتي وروابطي في مكان واحد</p>
      </a>
      <a href="https://bugbounty.sa/profile/rmaad" target="_blank" class="platform-card reveal">
        <div class="platform-arrow">↗</div>
        <div class="platform-icon">🐛</div>
        <div class="platform-name">BugBounty.sa</div>
        <div class="platform-handle">@rmaad</div>
        <p class="platform-desc">بروفايلي على المنصة الوطنية لاصطياد الثغرات التابعة لاتحاد SAFCSP</p>
      </a>
      <a href="#" class="platform-card reveal">
        <div class="platform-arrow">↗</div>
        <div class="platform-icon">🐦</div>
        <div class="platform-name">تويتر / X</div>
        <div class="platform-handle">@dawoodf96</div>
        <p class="platform-desc">تغريداتي في الأمن السيبراني والثغرات والأخبار التقنية</p>
      </a>
      <a href="#" class="platform-card reveal">
        <div class="platform-arrow">↗</div>
        <div class="platform-icon">💻</div>
        <div class="platform-name">GitHub</div>
        <div class="platform-handle">dawoodf96</div>
        <p class="platform-desc">أدواتي وأكوادي وسكريبتات الأمن السيبراني المفتوحة المصدر</p>
      </a>
      <a href="#" class="platform-card reveal">
        <div class="platform-arrow">↗</div>
        <div class="platform-icon">📸</div>
        <div class="platform-name">Instagram</div>
        <div class="platform-handle">@dawoodf96</div>
        <p class="platform-desc">لحظات من عالم الأمن السيبراني والمؤتمرات التقنية</p>
      </a>
      <a href="#" class="platform-card reveal">
        <div class="platform-arrow">↗</div>
        <div class="platform-icon">💬</div>
        <div class="platform-name">Telegram</div>
        <div class="platform-handle">@dawoodf96</div>
        <p class="platform-desc">قناتي للتواصل المباشر ومشاركة نصائح الأمن السيبراني</p>
      </a>
    </div>
  </div>
</section>



<!-- CONTACT -->
<section id="contact" style="max-width:800px;">
  <div class="contact-box reveal">
    <h2 class="contact-title">هل لديك مشروع أو تعاون؟ 🤝</h2>
    <p class="contact-sub">
      سواء كنت تبحث عن باحث أمني موثوق، أو شريك في برنامج Bug Bounty،
      أو تحتاج استشارة تقنية — أنا هنا.
    </p>
    <div class="social-grid">
      <a href="https://creators.sa/dawoodf96" target="_blank" class="social-btn">
        <span class="social-btn-icon">🌐</span> Creators.sa
      </a>
      <a href="https://bugbounty.sa/profile/rmaad" target="_blank" class="social-btn">
        <span class="social-btn-icon">🐛</span> BugBounty.sa
      </a>
      <a href="#" class="social-btn">
        <span class="social-btn-icon">🐦</span> تويتر
      </a>
      <a href="#" class="social-btn">
        <span class="social-btn-icon">📸</span> انستغرام
      </a>
      <a href="#" class="social-btn">
        <span class="social-btn-icon">💬</span> تيليغرام
      </a>
      <a href="mailto:contact@dawoodf96.com" class="social-btn">
        <span class="social-btn-icon">📧</span> البريد الإلكتروني
      </a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>صُنع بـ ❤️ في <span>المملكة العربية السعودية</span> · <span>@dawoodf96</span> · 2025</p>
</footer>

<script>
  // ─── CURSOR ───
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;

  document.addEventListener('mousemove', e => {
    mx = e.clientX; my = e.clientY;
    cursor.style.left = mx - 6 + 'px';
    cursor.style.top = my - 6 + 'px';
  });

  function animRing() {
    rx += (mx - rx - 18) * 0.12;
    ry += (my - ry - 18) * 0.12;
    ring.style.left = rx + 'px';
    ring.style.top = ry + 'px';
    requestAnimationFrame(animRing);
  }
  animRing();

  document.querySelectorAll('a, button, .platform-card, .skill-chip').forEach(el => {
    el.addEventListener('mouseenter', () => {
      cursor.style.transform = 'scale(2)';
      ring.style.width = '50px'; ring.style.height = '50px';
    });
    el.addEventListener('mouseleave', () => {
      cursor.style.transform = 'scale(1)';
      ring.style.width = '36px'; ring.style.height = '36px';
    });
  });

  // ─── REVEAL ───
  const observer = new IntersectionObserver(entries => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), 100);
      }
    });
  }, { threshold: 0.15 });

  document.querySelectorAll('.reveal').forEach((el, i) => {
    el.style.transitionDelay = (i % 4) * 0.08 + 's';
    observer.observe(el);
  });

  // ─── COUNTER ───
  const counters = document.querySelectorAll('[data-target]');
  const cObserver = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        const el = e.target;
        const target = +el.dataset.target;
        let count = 0;
        const step = target / 50;
        const timer = setInterval(() => {
          count += step;
          if (count >= target) { count = target; clearInterval(timer); }
          el.textContent = Math.floor(count) + '+';
        }, 30);
        cObserver.unobserve(el);
      }
    });
  }, { threshold: 0.5 });
  counters.forEach(c => cObserver.observe(c));

  // ─── MOBILE NAV ───
  function openMobileNav() {
    document.getElementById('mobileNav').classList.add('open');
  }
  function closeMobileNav() {
    document.getElementById('mobileNav').classList.remove('open');
  }

  // ─── ACTIVE NAV ───
  const sections = document.querySelectorAll('section[id], .stats-strip');
  const navLinks = document.querySelectorAll('.nav-links a');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(s => {
      if (window.scrollY >= s.offsetTop - 100) current = s.id;
    });
    navLinks.forEach(a => {
      a.style.color = a.getAttribute('href') === '#' + current ? 'var(--accent)' : '';
    });
  });
</script>
</body>
</html>
