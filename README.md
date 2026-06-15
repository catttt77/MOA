[moa_landing.html](https://github.com/user-attachments/files/28952933/moa_landing.html)
# MOA<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MOA — Korean Wellness Lifestyle Brand</title>
<style>
  :root{
    --bg-dark: #14202b;
    --bg-darker: #0e161e;
    --accent: #aebfd6;
    --accent-warm: #cdb8a0;
    --text-light: #f4f1ec;
    --text-muted: #b9c2cd;
    --serif: 'Playfair Display', Georgia, serif;
    --sans: 'Poppins', 'Segoe UI', sans-serif;
  }

  *{margin:0;padding:0;box-sizing:border-box;}

  body{
    font-family: var(--sans);
    background: var(--bg-darker);
    color: var(--text-light);
    line-height: 1.7;
    overflow-x: hidden;
  }

  a{color:inherit; text-decoration:none;}

  .container{
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 24px;
  }

  /* ===== NAV ===== */
  header{
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 18px 0;
    background: rgba(14,22,30,0.0);
    transition: background 0.4s ease, padding 0.4s ease, box-shadow 0.4s ease;
  }
  header.scrolled{
    background: rgba(14,22,30,0.85);
    backdrop-filter: blur(10px);
    padding: 12px 0;
    box-shadow: 0 4px 20px rgba(0,0,0,0.25);
  }
  nav{
    display:flex;
    align-items:center;
    justify-content: space-between;
  }
  .logo{
    font-family: var(--serif);
    font-size: 26px;
    font-weight: 700;
    letter-spacing: 2px;
    display:flex;
    align-items:center;
    gap: 10px;
  }
  .logo span{
    font-size: 14px;
    font-weight: 400;
    letter-spacing: 1px;
    color: var(--accent);
    font-family: var(--sans);
  }
  .nav-links{
    display:flex;
    gap: 32px;
    font-size: 14px;
    letter-spacing: 0.5px;
  }
  .nav-links a{
    opacity: 0.8;
    transition: opacity 0.3s, color 0.3s;
    position: relative;
  }
  .nav-links a:hover{ opacity: 1; color: var(--accent); }
  .nav-cta{
    border: 1px solid var(--accent);
    padding: 9px 22px;
    border-radius: 30px;
    font-size: 13px;
    letter-spacing: 1px;
    transition: all 0.3s ease;
    white-space: nowrap;
  }
  .nav-cta:hover{
    background: var(--accent);
    color: var(--bg-darker);
  }
  .burger{
    display:none;
    flex-direction:column;
    gap:5px;
    cursor:pointer;
    z-index: 200;
  }
  .burger span{
    width: 26px; height: 2px;
    background: var(--text-light);
    transition: all 0.3s ease;
  }

  /* ===== HERO ===== */
  .hero{
    min-height: 100vh;
    display:flex;
    align-items:center;
    position: relative;
    background:
      radial-gradient(ellipse at 75% 30%, rgba(174,191,214,0.12), transparent 55%),
      radial-gradient(ellipse at 20% 80%, rgba(205,184,160,0.10), transparent 50%),
      linear-gradient(160deg, #16232f 0%, #0c1117 100%);
    overflow: hidden;
  }
  .hero::before{
    content:"모아";
    position:absolute;
    font-family: var(--serif);
    font-size: min(45vw, 520px);
    font-weight: 700;
    color: rgba(255,255,255,0.025);
    top: 50%; left: 50%;
    transform: translate(-50%,-50%);
    white-space: nowrap;
    user-select: none;
    pointer-events: none;
  }
  .hero-grid{
    display:grid;
    grid-template-columns: 1.1fr 0.9fr;
    gap: 60px;
    align-items:center;
    width:100%;
    position: relative;
    z-index: 2;
  }
  .hero-eyebrow{
    font-size: 13px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 22px;
    opacity:0;
    animation: fadeUp 1s ease forwards 0.2s;
  }
  .hero h1{
    font-family: var(--serif);
    font-size: clamp(40px, 6.5vw, 76px);
    font-weight: 700;
    line-height: 1.15;
    margin-bottom: 24px;
    opacity:0;
    animation: fadeUp 1s ease forwards 0.4s;
  }
  .hero h1 em{
    font-style: italic;
    color: var(--accent-warm);
  }
  .hero p{
    font-size: 17px;
    color: var(--text-muted);
    max-width: 460px;
    margin-bottom: 38px;
    opacity:0;
    animation: fadeUp 1s ease forwards 0.6s;
  }
  .hero-actions{
    display:flex;
    gap:18px;
    flex-wrap: wrap;
    opacity:0;
    animation: fadeUp 1s ease forwards 0.8s;
  }
  .btn-primary{
    background: var(--accent-warm);
    color: #1c130a;
    padding: 16px 36px;
    border-radius: 40px;
    font-size: 14px;
    letter-spacing: 1px;
    font-weight: 600;
    border:none;
    cursor:pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    box-shadow: 0 10px 30px -10px rgba(205,184,160,0.4);
  }
  .btn-primary:hover{
    transform: translateY(-3px);
    box-shadow: 0 16px 36px -8px rgba(205,184,160,0.55);
  }
  .btn-secondary{
    border: 1px solid rgba(244,241,236,0.3);
    padding: 16px 36px;
    border-radius: 40px;
    font-size: 14px;
    letter-spacing: 1px;
    background: transparent;
    color: var(--text-light);
    cursor:pointer;
    transition: all 0.3s ease;
  }
  .btn-secondary:hover{
    border-color: var(--accent);
    background: rgba(174,191,214,0.08);
  }

  .hero-visual{
    position: relative;
    display:flex;
    justify-content:center;
    align-items:center;
    opacity:0;
    animation: fadeIn 1.4s ease forwards 0.5s;
  }
  .product-card{
    width: 100%;
    max-width: 380px;
    aspect-ratio: 3/4;
    border-radius: 24px;
    overflow:hidden;
    position: relative;
    box-shadow: 0 40px 80px -30px rgba(0,0,0,0.6);
    animation: float 6s ease-in-out infinite;
  }
  .product-card img{
    width:100%; height:100%;
    object-fit: cover;
    display:block;
  }
  .product-tag{
    position:absolute;
    bottom: 24px; left: 24px;
    background: rgba(20,32,43,0.7);
    backdrop-filter: blur(8px);
    padding: 14px 22px;
    border-radius: 14px;
    border: 1px solid rgba(255,255,255,0.08);
  }
  .product-tag p{ font-size:11px; letter-spacing:2px; color: var(--accent); margin-bottom:4px;}
  .product-tag h4{ font-family: var(--serif); font-size: 18px; }

  @keyframes float{
    0%,100%{ transform: translateY(0); }
    50%{ transform: translateY(-16px); }
  }
  @keyframes fadeUp{
    from{ opacity:0; transform: translateY(24px); }
    to{ opacity:1; transform: translateY(0); }
  }
  @keyframes fadeIn{
    from{ opacity:0; transform: scale(0.96); }
    to{ opacity:1; transform: scale(1); }
  }

  .scroll-cue{
    position:absolute;
    bottom: 32px; left: 50%;
    transform: translateX(-50%);
    font-size: 11px;
    letter-spacing: 3px;
    color: var(--text-muted);
    display:flex;
    flex-direction:column;
    align-items:center;
    gap:10px;
    z-index: 3;
  }
  .scroll-cue::after{
    content:"";
    width:1px; height: 40px;
    background: linear-gradient(to bottom, var(--accent), transparent);
    animation: scrollLine 2s ease-in-out infinite;
  }
  @keyframes scrollLine{
    0%{ transform: scaleY(0.4); opacity: 0.4; }
    50%{ transform: scaleY(1); opacity: 1; }
    100%{ transform: scaleY(0.4); opacity: 0.4; }
  }

  /* ===== SECTION GENERAL ===== */
  section{ padding: 120px 0; position: relative; }
  .section-tag{
    font-size: 12px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 18px;
    display:flex;
    align-items:center;
    gap: 14px;
  }
  .section-tag::before{
    content:"";
    width: 36px; height:1px;
    background: var(--accent);
  }
  h2{
    font-family: var(--serif);
    font-size: clamp(32px, 5vw, 52px);
    font-weight: 700;
    margin-bottom: 24px;
    line-height: 1.2;
  }
  .lead{
    color: var(--text-muted);
    font-size: 17px;
    max-width: 640px;
  }

  .reveal{
    opacity:0;
    transform: translateY(40px);
    transition: opacity 0.9s ease, transform 0.9s ease;
  }
  .reveal.visible{
    opacity:1;
    transform: translateY(0);
  }

  /* ===== ABOUT ===== */
  .about{
    background: linear-gradient(180deg, #0e161e 0%, #131e29 100%);
  }
  .about-grid{
    display:grid;
    grid-template-columns: 1fr 1fr;
    gap: 70px;
    align-items:center;
    margin-top: 60px;
  }
  .about-quote{
    font-family: var(--serif);
    font-size: 26px;
    line-height: 1.6;
    font-style: italic;
    color: var(--text-light);
    border-left: 2px solid var(--accent-warm);
    padding-left: 28px;
  }
  .about-text p{ color: var(--text-muted); margin-bottom: 18px; font-size: 16px; }
  .about-text strong{ color: var(--text-light); font-weight: 600; }

  /* ===== INGREDIENTS ===== */
  .ingredients{ background: var(--bg-darker); }
  .ingredients-grid{
    display:grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 24px;
    margin-top: 60px;
  }
  .ingredient-card{
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 18px;
    padding: 32px 26px;
    transition: transform 0.4s ease, border-color 0.4s ease, background 0.4s ease;
  }
  .ingredient-card:hover{
    transform: translateY(-8px);
    border-color: rgba(174,191,214,0.4);
    background: rgba(174,191,214,0.04);
  }
  .ingredient-icon{
    width: 48px; height: 48px;
    border-radius: 50%;
    background: rgba(174,191,214,0.1);
    display:flex; align-items:center; justify-content:center;
    margin-bottom: 22px;
    font-size: 20px;
  }
  .ingredient-card h4{
    font-family: var(--serif);
    font-size: 19px;
    margin-bottom: 10px;
  }
  .ingredient-card p{
    font-size: 14px;
    color: var(--text-muted);
  }

  .price-bar{
    margin-top: 70px;
    display:flex;
    justify-content: space-between;
    align-items:center;
    flex-wrap: wrap;
    gap: 30px;
    padding: 34px 40px;
    border-radius: 20px;
    background: linear-gradient(120deg, rgba(174,191,214,0.08), rgba(205,184,160,0.06));
    border: 1px solid rgba(255,255,255,0.06);
  }
  .price-item p{ font-size: 13px; letter-spacing: 2px; color: var(--text-muted); margin-bottom: 6px; text-transform: uppercase;}
  .price-item h3{ font-family: var(--serif); font-size: 30px; }

  /* ===== RITUAL / QUIZ ===== */
  .ritual{
    background: linear-gradient(180deg, #131e29 0%, #16232f 100%);
    text-align:center;
  }
  .ritual h2{ margin: 0 auto 18px; }
  .ritual .lead{ margin: 0 auto 50px; }
  .steps{
    display:grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
    text-align:left;
  }
  .step-card{
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 18px;
    padding: 36px 30px;
    position: relative;
  }
  .step-number{
    font-family: var(--serif);
    font-size: 46px;
    color: rgba(174,191,214,0.3);
    margin-bottom: 14px;
  }
  .step-card h4{ font-family: var(--serif); font-size: 20px; margin-bottom: 10px; }
  .step-card p{ font-size: 14px; color: var(--text-muted); }

  .quiz-cta{
    margin-top: 64px;
    display:inline-flex;
    flex-direction: column;
    align-items: center;
    gap: 22px;
  }

  /* ===== WHY MOA ===== */
  .why{ background: var(--bg-darker); }
  .why-grid{
    display:grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 18px;
    margin-top: 56px;
  }
  .why-item{
    display:flex;
    gap: 18px;
    align-items:flex-start;
    padding: 22px 26px;
    border-radius: 14px;
    border: 1px solid rgba(255,255,255,0.05);
    transition: background 0.3s ease, border-color 0.3s ease;
  }
  .why-item:hover{
    background: rgba(255,255,255,0.03);
    border-color: rgba(174,191,214,0.3);
  }
  .why-check{
    flex-shrink:0;
    width: 30px; height:30px;
    border-radius: 50%;
    background: rgba(205,184,160,0.15);
    color: var(--accent-warm);
    display:flex; align-items:center; justify-content:center;
    font-size: 14px;
    font-weight: 700;
  }
  .why-item p{ font-size: 15px; color: var(--text-muted); }
  .why-item strong{ color: var(--text-light); }

  /* ===== STATS ===== */
  .stats{
    background: linear-gradient(120deg, #1a2734 0%, #0e161e 100%);
  }
  .stats-grid{
    display:grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 24px;
    text-align:center;
    margin-top: 50px;
  }
  .stat-card h3{
    font-family: var(--serif);
    font-size: clamp(34px, 5vw, 48px);
    color: var(--accent-warm);
    margin-bottom: 8px;
  }
  .stat-card p{
    font-size: 13px;
    letter-spacing: 1px;
    color: var(--text-muted);
    text-transform: uppercase;
  }

  /* ===== FORM ===== */
  .signup{
    background: radial-gradient(ellipse at 50% 0%, rgba(174,191,214,0.1), transparent 60%), #0e161e;
    text-align:center;
  }
  .signup h2{ margin: 0 auto 16px; }
  .signup .lead{ margin: 0 auto 46px; }
  form.kit-form{
    max-width: 540px;
    margin: 0 auto;
    display:flex;
    flex-direction:column;
    gap: 18px;
  }
  .kit-form input,
  .kit-form select{
    width: 100%;
    padding: 16px 22px;
    border-radius: 40px;
    border: 1px solid rgba(255,255,255,0.12);
    background: rgba(255,255,255,0.03);
    color: var(--text-light);
    font-size: 15px;
    font-family: var(--sans);
    transition: border-color 0.3s ease, background 0.3s ease;
    outline:none;
    appearance: none;
  }
  .kit-form input::placeholder{ color: var(--text-muted); }
  .kit-form input:focus,
  .kit-form select:focus{
    border-color: var(--accent);
    background: rgba(174,191,214,0.06);
  }
  .kit-form select{ color: var(--text-muted); cursor:pointer; }
  .kit-form select:valid{ color: var(--text-light); }

  .form-success{
    display:none;
    margin-top: 26px;
    padding: 18px 26px;
    border-radius: 14px;
    background: rgba(99, 153, 34, 0.12);
    border: 1px solid rgba(99,153,34,0.3);
    color: #c0dd97;
    font-size: 14px;
  }
  .form-success.visible{ display:block; animation: fadeUp 0.6s ease; }

  /* ===== FOOTER ===== */
  footer{
    background: var(--bg-darker);
    padding: 70px 0 30px;
    border-top: 1px solid rgba(255,255,255,0.05);
  }
  .footer-grid{
    display:flex;
    justify-content: space-between;
    align-items:flex-start;
    flex-wrap: wrap;
    gap: 40px;
    margin-bottom: 50px;
  }
  .footer-logo{
    font-family: var(--serif);
    font-size: 28px;
    margin-bottom: 14px;
  }
  .footer-logo span{ color: var(--accent); font-size:14px; font-family: var(--sans); }
  footer p{ color: var(--text-muted); font-size: 14px; max-width: 320px; }
  .footer-links{ display:flex; gap: 60px; flex-wrap: wrap; }
  .footer-col h5{
    font-size: 12px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 18px;
  }
  .footer-col a{
    display:block;
    color: var(--text-muted);
    font-size: 14px;
    margin-bottom: 10px;
    transition: color 0.3s ease;
  }
  .footer-col a:hover{ color: var(--text-light); }
  .footer-bottom{
    border-top: 1px solid rgba(255,255,255,0.05);
    padding-top: 26px;
    display:flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 14px;
    font-size: 13px;
    color: var(--text-muted);
  }

  /* ===== RESPONSIVE ===== */
  @media (max-width: 900px){
    .hero-grid{ grid-template-columns: 1fr; text-align:center; }
    .hero p{ margin: 0 auto 38px; }
    .hero-actions{ justify-content:center; }
    .hero-visual{ order:-1; margin-bottom: 20px; }
    .about-grid{ grid-template-columns: 1fr; gap: 40px; }
    .ingredients-grid{ grid-template-columns: repeat(2, 1fr); }
    .steps{ grid-template-columns: 1fr; }
    .why-grid{ grid-template-columns: 1fr; }
    .stats-grid{ grid-template-columns: repeat(2, 1fr); gap: 30px; }
    .price-bar{ flex-direction: column; align-items: flex-start; }

    .nav-links{
      position: fixed;
      top:0; right:0;
      height: 100vh;
      width: min(75vw, 320px);
      background: rgba(14,22,30,0.97);
      backdrop-filter: blur(10px);
      flex-direction: column;
      justify-content:center;
      align-items:flex-start;
      gap: 30px;
      padding: 0 50px;
      transform: translateX(100%);
      transition: transform 0.4s ease;
      font-size: 18px;
      z-index: 150;
    }
    .nav-links.open{ transform: translateX(0); }
    .nav-cta{ margin-top: 10px; }
    .burger{ display:flex; }
    .burger.open span:nth-child(1){ transform: translateY(7px) rotate(45deg); }
    .burger.open span:nth-child(2){ opacity:0; }
    .burger.open span:nth-child(3){ transform: translateY(-7px) rotate(-45deg); }
  }

  @media (max-width: 600px){
    section{ padding: 80px 0; }
    .ingredients-grid{ grid-template-columns: 1fr; }
    .stats-grid{ grid-template-columns: 1fr 1fr; }
    .hero h1{ font-size: 42px; }
  }
</style>
</head>
<body>

<header id="header">
  <div class="container">
    <nav>
      <div class="logo">MOA <span>모아</span></div>
      <div class="nav-links" id="navLinks">
        <a href="#about" class="nav-link">Бренд</a>
        <a href="#product" class="nav-link">Продукт</a>
        <a href="#ritual" class="nav-link">Ритуал</a>
        <a href="#why" class="nav-link">Почему MOA</a>
        <a href="#signup" class="nav-cta">Получить kit</a>
      </div>
      <div class="burger" id="burger">
        <span></span><span></span><span></span>
      </div>
    </nav>
  </div>
</header>

<section class="hero">
  <div class="container hero-grid">
    <div>
      <p class="hero-eyebrow">Korean Wellness Lifestyle Brand</p>
      <h1>Твой сон <em>заслуживает</em> ритуала</h1>
      <p>Один жест перед сном. Всё остальное сделает ночь. MOA Sleep Balm — корейская практика заботы, объединяющая науку и спокойствие в одной баночке.</p>
      <div class="hero-actions">
        <button class="btn-primary" onclick="document.getElementById('signup').scrollIntoView({behavior:'smooth'})">Собери свой первый ritual kit</button>
        <button class="btn-secondary" onclick="document.getElementById('product').scrollIntoView({behavior:'smooth'})">Узнать о продукте</button>
      </div>
    </div>
    <div class="hero-visual">
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1601049541289-9b1b7bbbfe19?w=800&q=80" alt="MOA Sleep Balm" loading="lazy">
        <div class="product-tag">
          <p>MOA SLEEP BALM</p>
          <h4>3,800 ₽</h4>
        </div>
      </div>
    </div>
  </div>
  <div class="scroll-cue">SCROLL</div>
</section>

<section class="about" id="about">
  <div class="container">
    <p class="section-tag reveal">Концепция бренда</p>
    <h2 class="reveal">собирать. объединять. восстанавливать.</h2>
    <div class="about-grid">
      <p class="about-quote reveal">«MOA (모아) — корейский wellness-бренд, сфокусированный на качестве сна как основе физического и психологического восстановления.»</p>
      <div class="about-text reveal">
        <p>Название переводится как «собирать», «объединять» — бренд объединяет <strong>научный подход</strong>, корейские практики заботы о теле и современный <strong>lifestyle</strong>.</p>
        <p>Это не «ещё одна баночка» — это <strong>формат ритуала</strong>, который превращает вечер в осознанную паузу перед сном.</p>
        <p>Korean wellness + aesthetic packaging + physical product + digital content — всё в одной системе заботы о себе.</p>
      </div>
    </div>
  </div>
</section>

<section class="ingredients" id="product">
  <div class="container">
    <p class="section-tag reveal">Продукт</p>
    <h2 class="reveal">MOA Sleep Balm</h2>
    <p class="lead reveal">Бальзам для вечернего ритуала — не про уход, а про комфорт и заземление перед сном.</p>

    <div class="ingredients-grid">
      <div class="ingredient-card reveal">
        <div class="ingredient-icon">🌿</div>
        <h4>Лаванда</h4>
        <p>Снижает уровень возбуждения нервной системы, помогая телу перейти в режим покоя.</p>
      </div>
      <div class="ingredient-card reveal">
        <div class="ingredient-icon">🍃</div>
        <h4>Полынь (mugwort)</h4>
        <p>Традиционный корейский компонент, веками используемый в вечерних ритуалах заботы.</p>
      </div>
      <div class="ingredient-card reveal">
        <div class="ingredient-icon">🪵</div>
        <h4>Сандаловое дерево</h4>
        <p>Тёплый древесный аромат, ассоциирующийся с «заземлением» и ощущением дома.</p>
      </div>
      <div class="ingredient-card reveal">
        <div class="ingredient-icon">🤍</div>
        <h4>Масло ши</h4>
        <p>Носитель текстуры — мягкое, плотное ощущение на коже, созданное для комфорта.</p>
      </div>
    </div>

    <div class="price-bar reveal">
      <div class="price-item">
        <p>Цена</p>
        <h3>3,800 ₽ <span style="font-size:16px; color:var(--text-muted); font-family: var(--sans);">(~$42)</span></h3>
      </div>
      <div class="price-item">
        <p>Аудитория</p>
        <h3 style="font-size:22px;">18–35 лет, K-lifestyle enthusiasts</h3>
      </div>
      <button class="btn-primary" onclick="document.getElementById('signup').scrollIntoView({behavior:'smooth'})">Заказать сейчас</button>
    </div>
  </div>
</section>

<section class="ritual" id="ritual">
  <div class="container">
    <p class="section-tag reveal" style="margin:0 auto 18px; justify-content:center;">Ритуал & Quiz</p>
    <h2 class="reveal">Какой kit подходит твоему сну?</h2>
    <p class="lead reveal">Пройди короткий quiz — и получи персональные рекомендации, основанные на твоих привычках сна.</p>

    <div class="steps">
      <div class="step-card reveal">
        <div class="step-number">01</div>
        <h4>Quiz о сне</h4>
        <p>Ответь на несколько вопросов о своих привычках, тревогах и вечерней рутине.</p>
      </div>
      <div class="step-card reveal">
        <div class="step-number">02</div>
        <h4>Персональный kit</h4>
        <p>Получи рекомендацию ritual kit, подобранного под твой тип сна.</p>
      </div>
      <div class="step-card reveal">
        <div class="step-number">03</div>
        <h4>30-Day Sleep Glow</h4>
        <p>Присоединяйся к челленджу — отслеживай прогресс и делись опытом.</p>
      </div>
    </div>

    <div class="quiz-cta reveal">
      <button class="btn-primary" onclick="document.getElementById('signup').scrollIntoView({behavior:'smooth'})">Пройти Quiz: какой kit подходит твоему сну?</button>
    </div>
  </div>
</section>

<section class="why" id="why">
  <div class="container">
    <p class="section-tag reveal">Почему MOA</p>
    <h2 class="reveal">Это не «ещё одна баночка»</h2>

    <div class="why-grid">
      <div class="why-item reveal">
        <div class="why-check">✓</div>
        <p><strong>Уникальность продукта</strong> — не набор и не косметика, а фокусный продукт для ночного состояния.</p>
      </div>
      <div class="why-item reveal">
        <div class="why-check">✓</div>
        <p><strong>Формат ритуала</strong> — осознанная пауза перед сном, а не рутинный уход.</p>
      </div>
      <div class="why-item reveal">
        <div class="why-check">✓</div>
        <p><strong>Идеальный тайминг</strong> — K-wellness boom встречается с глобальным трендом на сон.</p>
      </div>
      <div class="why-item reveal">
        <div class="why-check">✓</div>
        <p><strong>TikTok-ready</strong> — визуальный, эстетичный, shareable unboxing-опыт.</p>
      </div>
      <div class="why-item reveal">
        <div class="why-check">✓</div>
        <p><strong>Сильные метрики</strong> — ROI 259%, окупаемость в течение первого месяца.</p>
      </div>
      <div class="why-item reveal">
        <div class="why-check">✓</div>
        <p><strong>Масштабируемость</strong> — seasonal collections и subscription-модель.</p>
      </div>
    </div>
  </div>
</section>

<section class="stats">
  <div class="container">
    <p class="section-tag reveal">Прогноз эффективности</p>
    <h2 class="reveal">Один вложенный рубль приносит 2,59 ₽ прибыли</h2>
    <p class="lead reveal">Прогноз на первый месяц при бюджете 380,000 ₽ и трафике 50,000 визитов.</p>

    <div class="stats-grid">
      <div class="stat-card reveal">
        <h3 id="cpl">0</h3>
        <p>CPL, ₽</p>
      </div>
      <div class="stat-card reveal">
        <h3 id="sales">0</h3>
        <p>Продаж за месяц</p>
      </div>
      <div class="stat-card reveal">
        <h3 id="romi">0%</h3>
        <p>ROMI</p>
      </div>
      <div class="stat-card reveal">
        <h3 id="repeat">0</h3>
        <p>Повторных покупок</p>
      </div>
    </div>
  </div>
</section>

<section class="signup" id="signup">
  <div class="container">
    <p class="section-tag reveal" style="margin:0 auto 18px; justify-content:center;">Начни свой ритуал</p>
    <h2 class="reveal">Собери свой первый ritual kit</h2>
    <p class="lead reveal">Оставь email и расскажи о своих привычках сна — мы подберём для тебя идеальный набор.</p>

    <form class="kit-form reveal" id="kitForm">
      <input type="email" id="email" placeholder="Твой email" required>
      <select id="sleepIssue" required>
        <option value="" disabled selected>Что мешает тебе спать?</option>
        <option value="stress">Стресс и тревожные мысли</option>
        <option value="screens">Слишком много экранов перед сном</option>
        <option value="routine">Нет вечернего ритуала</option>
        <option value="other">Другое</option>
      </select>
      <select id="frequency" required>
        <option value="" disabled selected>Как часто ты плохо спишь?</option>
        <option value="daily">Почти каждую ночь</option>
        <option value="weekly">Несколько раз в неделю</option>
        <option value="rarely">Редко, но бывает</option>
      </select>
      <button type="submit" class="btn-primary">Получить рекомендацию</button>
    </form>
    <div class="form-success" id="formSuccess">Спасибо! Мы отправили твою персональную рекомендацию на почту. Добро пожаловать в MOA 모아 ✓</div>
  </div>
</section>

<footer>
  <div class="container">
    <div class="footer-grid">
      <div>
        <div class="footer-logo">MOA <span>모아</span></div>
        <p>Korean Wellness Lifestyle Brand. Твой сон заслуживает ритуала.</p>
      </div>
      <div class="footer-links">
        <div class="footer-col">
          <h5>Бренд</h5>
          <a href="#about">О MOA</a>
          <a href="#product">Sleep Balm</a>
          <a href="#why">Почему MOA</a>
        </div>
        <div class="footer-col">
          <h5>Программа</h5>
          <a href="#ritual">Sleep Glow Challenge</a>
          <a href="#signup">Referral: Give 500₽ Get 500₽</a>
        </div>
        <div class="footer-col">
          <h5>Контакты</h5>
          <a href="#">moa.beauty</a>
          <a href="#">Instagram</a>
          <a href="#">TikTok</a>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2026 MOA 모아. Все права защищены.</p>
      <p>Pre-launch: март 2026 · Full launch: апрель 2026</p>
    </div>
  </div>
</footer>

<script>
  // Header scroll effect
  const header = document.getElementById('header');
  window.addEventListener('scroll', () => {
    header.classList.toggle('scrolled', window.scrollY > 40);
  });

  // Mobile menu
  const burger = document.getElementById('burger');
  const navLinks = document.getElementById('navLinks');
  burger.addEventListener('click', () => {
    burger.classList.toggle('open');
    navLinks.classList.toggle('open');
  });
  document.querySelectorAll('.nav-link, .nav-cta').forEach(link => {
    link.addEventListener('click', () => {
      burger.classList.remove('open');
      navLinks.classList.remove('open');
    });
  });

  // Reveal on scroll
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.15 });
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  // Animated counters for stats
  function animateCounter(el, target, suffix = '', duration = 1500) {
    let start = 0;
    const stepTime = 16;
    const steps = duration / stepTime;
    const increment = target / steps;
    const isFloat = target % 1 !== 0;
    const timer = setInterval(() => {
      start += increment;
      if (start >= target) {
        start = target;
        clearInterval(timer);
      }
      el.textContent = (isFloat ? start.toFixed(0) : Math.floor(start)).toLocaleString('ru-RU') + suffix;
    }, stepTime);
  }

  const statsSection = document.querySelector('.stats');
  let statsAnimated = false;
  const statsObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting && !statsAnimated) {
        statsAnimated = true;
        animateCounter(document.getElementById('cpl'), 152, ' ₽');
        animateCounter(document.getElementById('sales'), 525);
        animateCounter(document.getElementById('romi'), 259, '%');
        animateCounter(document.getElementById('repeat'), 158);
      }
    });
  }, { threshold: 0.3 });
  statsObserver.observe(statsSection);

  // Form submit
  document.getElementById('kitForm').addEventListener('submit', function(e) {
    e.preventDefault();
    document.getElementById('formSuccess').classList.add('visible');
    this.reset();
  });
</script>

</body>
</html>
