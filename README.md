# sister-hinabe
火鍋シスター公式サイト
<!doctype html>
<html lang="ja">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>火鍋シスター（姐妹）｜花巻の本格火鍋</title>
  <meta name="description" content="岩手県花巻市の本格火鍋。香り立つスープと豊富な具材で、身体が喜ぶ“あったか火鍋”。ご予約はお電話で。" />

  <!-- 任意：公開URLが確定したら canonical を入れると良い
  <link rel="canonical" href="https://<あなたのID>.github.io/sister-hinabe/" />
  -->

  <!-- OGP（SNS表示用）※og:imageは本来「絶対URL」推奨。公開後に差し替えると強い -->
  <meta property="og:title" content="火鍋シスター（姐妹）｜花巻の本格火鍋" />
  <meta property="og:description" content="香り立つスープと具材で、身体が喜ぶ“あったか火鍋”。ご予約はお電話で。" />
  <meta property="og:type" content="website" />
  <meta property="og:image" content="images/ogp.jpg" />

  <!-- 任意：X(Twitter)用 -->
  <meta name="twitter:card" content="summary_large_image" />

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg: #0b0c10;
      --surface: #121420;
      --surface2: #0f1118;
      --text: #f5f7ff;
      --muted: rgba(245,247,255,.75);
      --line: rgba(255,255,255,.10);

      --primary: #c00015;   /* 赤 */
      --primary2:#ff3b30;   /* 明るい赤 */
      --accent:  #d7b46a;   /* 金 */

      --radius: 18px;
      --shadow: 0 14px 30px rgba(0,0,0,.35);
      --max: 1080px;
    }

    *{ box-sizing: border-box; }
    html{ scroll-behavior: smooth; }
    body{
      margin:0;
      font-family: "Noto Sans JP", system-ui, -apple-system, "Segoe UI", Roboto, "Hiragino Kaku Gothic ProN", "Yu Gothic", sans-serif;
      color: var(--text);
      background: radial-gradient(1200px 600px at 20% -10%, rgba(192,0,21,.35), transparent 60%),
                  radial-gradient(900px 500px at 90% 0%, rgba(215,180,106,.18), transparent 55%),
                  linear-gradient(180deg, #07080c 0%, #0b0c10 40%, #07080c 100%);
      line-height: 1.7;
    }

    a{ color: inherit; text-decoration: none; }
    img{ max-width: 100%; display:block; }
    .container{ width: min(var(--max), calc(100% - 40px)); margin: 0 auto; }
    .sr-only{ position:absolute; width:1px; height:1px; padding:0; margin:-1px; overflow:hidden; clip:rect(0,0,0,0); white-space:nowrap; border:0; }

    .skip{
      position:absolute; left:16px; top:-60px;
      background: var(--text); color:#000;
      padding:10px 12px; border-radius:12px;
      transition: .2s;
      z-index: 9999;
    }
    .skip:focus{ top:16px; }

    header{
      position: sticky; top:0; z-index: 50;
      backdrop-filter: blur(10px);
      background: rgba(11,12,16,.72);
      border-bottom: 1px solid var(--line);
    }
    .nav{
      display:flex; align-items:center; justify-content:space-between;
      padding: 14px 0;
      gap: 16px;
    }
    .brand{
      display:flex; align-items:center; gap:10px;
      min-width: 180px;
    }
    .logo{
      width: 38px; height: 38px; border-radius: 12px;
      background: linear-gradient(135deg, var(--primary), #52000a);
      box-shadow: 0 10px 20px rgba(192,0,21,.25);
      display:grid; place-items:center;
      border: 1px solid rgba(255,255,255,.12);
      font-weight: 800;
    }
    .brand .name{
      display:flex; flex-direction:column; line-height:1.2;
    }
    .brand .name strong{ font-size: 14px; letter-spacing:.02em; }
    .brand .name span{ font-size: 12px; color: var(--muted); }

    nav ul{
      list-style:none; margin:0; padding:0;
      display:flex; gap: 14px; align-items:center;
    }
    nav a{
      font-size: 13px;
      color: rgba(245,247,255,.85);
      padding: 10px 10px;
      border-radius: 12px;
      transition: .15s;
    }
    nav a:hover{ background: rgba(255,255,255,.06); }

    .nav-cta{
      display:flex; align-items:center; gap:10px;
      min-width: 220px;
      justify-content:flex-end;
    }

    .btn{
      display:inline-flex; align-items:center; justify-content:center;
      gap:8px;
      border-radius: 999px;
      padding: 12px 16px;
      border: 1px solid rgba(255,255,255,.16);
      background: rgba(255,255,255,.06);
      color: var(--text);
      font-weight: 700;
      letter-spacing:.02em;
      transition: .15s;
      box-shadow: 0 10px 22px rgba(0,0,0,.25);
    }
    .btn:hover{ transform: translateY(-1px); background: rgba(255,255,255,.09); }
    .btn-primary{
      border: 1px solid rgba(255,255,255,.12);
      background: linear-gradient(135deg, var(--primary), #7a0010);
      box-shadow: 0 14px 26px rgba(192,0,21,.28);
    }
    .btn-primary:hover{ background: linear-gradient(135deg, var(--primary2), var(--primary)); }
    .btn-ghost{
      box-shadow:none;
      background: transparent;
    }

    .hamburger{
      display:none;
      width:44px; height:44px;
      border-radius: 14px;
      border: 1px solid rgba(255,255,255,.16);
      background: rgba(255,255,255,.06);
      color: var(--text);
      cursor:pointer;
    }

    .hero{ padding: 56px 0 24px; }
    .hero-grid{
      display:grid;
      grid-template-columns: 1.1fr .9fr;
      gap: 22px;
      align-items: stretch;
    }
    .hero-card{
      border-radius: var(--radius);
      border: 1px solid var(--line);
      background: linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,.02));
      box-shadow: var(--shadow);
      overflow:hidden;
      position: relative;
    }
    .hero-copy{ padding: 34px 32px 28px; }
    .badge{
      display:inline-flex; align-items:center; gap:8px;
      padding: 8px 12px;
      border-radius: 999px;
      border: 1px solid rgba(215,180,106,.35);
      background: rgba(215,180,106,.12);
      color: rgba(245,247,255,.92);
      font-size: 12px;
      font-weight: 700;
      letter-spacing:.06em;
    }
    h1{
      margin: 14px 0 10px;
      font-size: clamp(28px, 3.2vw, 44px);
      line-height: 1.18;
      letter-spacing: .01em;
    }
    .lead{
      margin: 0 0 18px;
      color: var(--muted);
      font-size: 15px;
    }
    .hero-actions{ display:flex; flex-wrap:wrap; gap: 10px; margin-top: 14px; }
    .hero-meta{
      display:flex; flex-wrap:wrap; gap: 10px;
      margin-top: 18px;
      color: rgba(245,247,255,.82);
      font-size: 13px;
    }
    .pill{
      display:inline-flex; align-items:center; gap:8px;
      padding: 10px 12px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.05);
    }
    .pill small{ color: var(--muted); }

    .hero-photo{
      min-height: 340px;
      background:
        radial-gradient(600px 250px at 40% 10%, rgba(255,59,48,.22), transparent 60%),
        radial-gradient(600px 320px at 90% 60%, rgba(215,180,106,.16), transparent 55%),
        linear-gradient(180deg, rgba(255,255,255,.02), rgba(255,255,255,.04));
      position: relative;
    }
    .hero-photo::before{
      content:"";
      position:absolute; inset:0;
      background:
        linear-gradient(180deg, rgba(0,0,0,.15), rgba(0,0,0,.55)),
        url("images/hero.jpg") center/cover no-repeat;
      opacity: .92;
    }
    .hero-photo .photo-caption{
      position:absolute; left:18px; bottom:18px;
      right:18px;
      display:flex; gap:10px; flex-wrap:wrap;
      align-items:center; justify-content:space-between;
      z-index: 2;
    }
    .caption-chip{
      display:inline-flex; align-items:center; gap:8px;
      padding: 10px 12px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,.18);
      background: rgba(0,0,0,.35);
      color: rgba(245,247,255,.92);
      font-size: 12px;
    }

    section{ padding: 34px 0; }
    .section-head{
      display:flex; align-items:flex-end; justify-content:space-between;
      gap: 16px;
      margin-bottom: 16px;
    }
    .section-head h2{ margin:0; font-size: 22px; letter-spacing:.02em; }
    .section-head p{ margin:0; color: var(--muted); font-size: 13px; max-width: 52ch; }

    .grid-3{ display:grid; grid-template-columns: repeat(3, 1fr); gap: 14px; }
    .grid-2{ display:grid; grid-template-columns: 1fr 1fr; gap: 14px; }

    .card{
      border-radius: var(--radius);
      border: 1px solid var(--line);
      background: rgba(255,255,255,.05);
      box-shadow: 0 10px 22px rgba(0,0,0,.22);
      overflow:hidden;
    }
    .card .inner{ padding: 18px; }
    .card h3{ margin: 0 0 8px; font-size: 16px; }
    .card p{ margin:0; color: var(--muted); font-size: 13px; }
    .icon{
      width: 38px; height: 38px;
      border-radius: 14px;
      display:grid; place-items:center;
      margin-bottom: 10px;
      border: 1px solid rgba(255,255,255,.14);
      background: linear-gradient(135deg, rgba(215,180,106,.14), rgba(192,0,21,.10));
    }

    .menu-list{ display:grid; grid-template-columns: 1fr 1fr; gap: 14px; }
    .menu-item{
      padding: 16px;
      border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.04);
      display:flex; justify-content:space-between; gap:10px;
      align-items:flex-start;
    }
    .menu-item strong{ font-size: 14px; }
    .menu-item span{ color: var(--muted); font-size: 12px; }
    .menu-note{ margin-top: 12px; color: var(--muted); font-size: 12px; }

    .reserve{
      background:
        radial-gradient(900px 420px at 10% 20%, rgba(192,0,21,.22), transparent 60%),
        radial-gradient(800px 420px at 90% 0%, rgba(215,180,106,.14), transparent 55%),
        rgba(255,255,255,.03);
      border-top: 1px solid var(--line);
      border-bottom: 1px solid var(--line);
    }
    .reserve-box{
      padding: 22px;
      border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.22);
      box-shadow: var(--shadow);
      display:flex; flex-wrap:wrap; gap: 12px;
      align-items:center; justify-content:space-between;
    }
    .reserve-box .text{ max-width: 60ch; }
    .reserve-box .text h2{ margin:0 0 6px; font-size: 20px; }
    .reserve-box .text p{ margin:0; color: var(--muted); font-size: 13px; }
    .reserve-actions{ display:flex; gap:10px; flex-wrap:wrap; }

    .gallery{ display:grid; grid-template-columns: repeat(4, 1fr); gap: 10px; }
    .ph{
      aspect-ratio: 4 / 3;
      border-radius: 16px;
      border: 1px solid rgba(255,255,255,.14);
      background:
        radial-gradient(120px 90px at 20% 25%, rgba(255,59,48,.18), transparent 60%),
        radial-gradient(140px 100px at 80% 70%, rgba(215,180,106,.14), transparent 60%),
        rgba(255,255,255,.04);
      overflow:hidden;
      position:relative;
    }
    .ph img{ width:100%; height:100%; object-fit: cover; filter: saturate(1.05) contrast(1.05); }

    .access{ display:grid; grid-template-columns: 1fr 1fr; gap: 14px; align-items: stretch; }
    .map{
      border-radius: var(--radius);
      border: 1px solid var(--line);
      overflow:hidden;
      background: rgba(255,255,255,.04);
      min-height: 320px;
    }
    .map iframe{ width:100%; height:100%; border:0; min-height: 320px; }

    .info-table{
      width:100%;
      border-collapse: collapse;
      font-size: 13px;
      background: rgba(255,255,255,.03);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      overflow:hidden;
    }
    .info-table th, .info-table td{
      padding: 14px 14px;
      border-bottom: 1px solid rgba(255,255,255,.10);
      vertical-align: top;
    }
    .info-table th{
      width: 32%;
      color: rgba(245,247,255,.92);
      background: rgba(0,0,0,.20);
      font-weight: 700;
    }
    .info-table td{ color: var(--muted); }

    details{
      border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.04);
      padding: 12px 14px;
    }
    details + details{ margin-top: 10px; }
    summary{
      cursor:pointer;
      font-weight: 700;
      color: rgba(245,247,255,.92);
      list-style: none;
    }
    summary::-webkit-details-marker{ display:none; }
    details p{ margin: 10px 0 0; color: var(--muted); font-size: 13px; }

    footer{
      padding: 28px 0 40px;
      color: rgba(245,247,255,.65);
      border-top: 1px solid var(--line);
      background: rgba(0,0,0,.22);
    }
    .foot{
      display:flex; flex-wrap:wrap; gap: 12px;
      align-items:center; justify-content:space-between;
      font-size: 12px;
    }
    .links{ display:flex; gap: 10px; flex-wrap:wrap; }
    .link{
      padding: 8px 10px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.04);
    }

    .float-call{
      position: fixed;
      right: 16px;
      bottom: 16px;
      z-index: 60;
      display:none;
    }

    @media (max-width: 980px){
      .hero-grid{ grid-template-columns: 1fr; }
      .hero-photo{ min-height: 300px; }
      .grid-3{ grid-template-columns: 1fr; }
      .grid-2{ grid-template-columns: 1fr; }
      .menu-list{ grid-template-columns: 1fr; }
      .gallery{ grid-template-columns: repeat(2, 1fr); }
      .access{ grid-template-columns: 1fr; }
    }
    @media (max-width: 860px){
      nav ul{ display:none; }
      .hamburger{ display:inline-grid; place-items:center; }
      .nav-cta{ min-width: auto; }
      .float-call{ display:block; }
      .btn{ padding: 12px 14px; }
    }

    .mobile{
      display:none;
      border-top: 1px solid var(--line);
      background: rgba(11,12,16,.85);
    }
    .mobile.open{ display:block; }
    .mobile .container{ padding: 10px 0 14px; }
    .mobile a{
      display:block;
      padding: 12px 10px;
      border-radius: 12px;
      color: rgba(245,247,255,.90);
    }
    .mobile a:hover{ background: rgba(255,255,255,.06); }
    .divider{ height:1px; background: var(--line); margin: 10px 0; }
  </style>

  <!-- 構造化データ（店舗情報：電話番号を統一） -->
  <script type="application/ld+json">
  {
    "@context":"https://schema.org",
    "@type":"Restaurant",
    "name":"火鍋シスター（姐妹）",
    "telephone":"0198-24-0171",
    "address":{
      "@type":"PostalAddress",
      "addressRegion":"岩手県",
      "addressLocality":"花巻市",
      "streetAddress":"東町4-3",
      "addressCountry":"JP"
    },
    "servesCuisine":["火鍋","中華"],
    "priceRange":"¥¥"
  }
  </script>
</head>

<body>
  <a class="skip" href="#main">本文へスキップ</a>

  <header>
    <div class="container">
      <div class="nav">
        <a class="brand" href="#top" aria-label="トップへ">
          <div class="logo">姐</div>
          <div class="name">
            <strong>火鍋シスター（姐妹）</strong>
            <span>花巻の本格火鍋</span>
          </div>
        </a>

        <nav aria-label="ページ内ナビゲーション">
          <ul>
            <li><a href="#about">特徴</a></li>
            <li><a href="#menu">メニュー</a></li>
            <li><a href="#reserve">予約</a></li>
            <li><a href="#access">アクセス</a></li>
            <li><a href="#faq">FAQ</a></li>
          </ul>
        </nav>

        <div class="nav-cta">
          <a class="btn btn-ghost" href="#access">📍地図</a>
          <a class="btn btn-primary" href="tel:0198240171" aria-label="電話で予約する">📞 予約</a>
          <button class="hamburger" id="hamburger" aria-expanded="false" aria-controls="mobileMenu" aria-label="メニューを開く">☰</button>
        </div>
      </div>
    </div>

    <div class="mobile" id="mobileMenu" aria-label="モバイルメニュー">
      <div class="container">
        <a href="#about" class="m-link">特徴</a>
        <a href="#menu" class="m-link">メニュー</a>
        <a href="#reserve" class="m-link">予約</a>
        <a href="#gallery" class="m-link">店内・写真</a>
        <a href="#access" class="m-link">アクセス</a>
        <a href="#info" class="m-link">店舗情報</a>
        <a href="#faq" class="m-link">FAQ</a>
        <div class="divider"></div>
        <a class="btn btn-primary" style="width:100%" href="tel:0198240171">📞 0198-24-0171 へ電話</a>
      </div>
    </div>
  </header>

  <!-- Floating call button (mobile) -->
  <div class="float-call">
    <a class="btn btn-primary" href="tel:0198240171" aria-label="電話で予約する（固定ボタン）">📞 予約する</a>
  </div>

  <main id="main">
    <div id="top" class="hero">
      <div class="container">
        <div class="hero-grid">
          <div class="hero-card">
            <div class="hero-copy">
              <div class="badge">花巻の本格火鍋</div>
              <h1>香り立つスープと具材で、<br>身体が喜ぶ “あったか火鍋”。</h1>
              <p class="lead">
                はじめての方も安心。食べ方やおすすめの具材はスタッフがご案内します。<br>
                ご家族・ご友人・宴会にもどうぞ。
              </p>

              <div class="hero-actions">
                <a class="btn btn-primary" href="tel:0198240171">📞 電話で予約する</a>
                <a class="btn" href="#reserve">🗓 予約案内を見る</a>
                <a class="btn" href="#menu">🍲 メニュー</a>
              </div>

              <div class="hero-meta">
                <div class="pill">📍 <span>岩手県花巻市 東町4-3</span></div>
                <div class="pill">⏰ <span><small>営業時間：</small>（ここを実情報に）</span></div>
                <div class="pill">📞 <span><small>予約：</small>0198-24-0171</span></div>
              </div>
            </div>
          </div>

          <div class="hero-card hero-photo" aria-label="火鍋イメージ写真">
            <div class="photo-caption">
              <span class="caption-chip">🔥 2色スープもおすすめ</span>
              <a class="caption-chip" href="#gallery">📷 写真を見る</a>
            </div>
          </div>
        </div>
      </div>
    </div>

    <section id="about">
      <div class="container">
        <div class="section-head">
          <div>
            <h2>シスターの火鍋</h2>
            <p>香り・辛み・旨みのバランスにこだわった一杯。食べ進めるほどクセになります。</p>
          </div>
          <a class="btn" href="#reserve">予約へ →</a>
        </div>

        <div class="grid-3">
          <div class="card">
            <div class="inner">
              <div class="icon">🍲</div>
              <h3>本格スープ</h3>
              <p>香辛料の風味と旨みが引き立つスープ。辛さの目安もご案内します。</p>
            </div>
          </div>

          <div class="card">
            <div class="inner">
              <div class="icon">🥬</div>
              <h3>具材いろいろ</h3>
              <p>きくらげ／春雨／湯葉など、火鍋の定番具材も充実（内容は仕入れで変動）。</p>
            </div>
          </div>

          <div class="card">
            <div class="inner">
              <div class="icon">👪</div>
              <h3>グループでも</h3>
              <p>ご家族・友人・宴会にも。席の相談はお電話でどうぞ。</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="menu">
      <div class="container">
        <div class="section-head">
          <div>
            <h2>メニュー（抜粋）</h2>
            <p>季節・仕入れで内容が変わる場合があります。最新は店頭／SNSでご案内します。</p>
          </div>
        </div>

        <div class="menu-list">
          <div class="menu-item">
            <div>
              <strong>火鍋（2〜4名推奨）</strong><br>
              <span>スープ・具材はお好みで。おすすめもご案内します。</span>
            </div>
            <span>¥¥</span>
          </div>

          <div class="menu-item">
            <div>
              <strong>追加具材（例）</strong><br>
              <span>野菜／肉／麺／豆腐／きのこ など</span>
            </div>
            <span>—</span>
          </div>

          <div class="menu-item">
            <div>
              <strong>サイド（例）</strong><br>
              <span>唐揚げ／揚げ物／一品 など</span>
            </div>
            <span>—</span>
          </div>

          <div class="menu-item">
            <div>
              <strong>ランチ（例）</strong><br>
              <span>内容は日替わり・告知ベース（実運用に合わせて記載）。</span>
            </div>
            <span>—</span>
          </div>
        </div>

        <p class="menu-note">※「メニュー表（紙）」の写真を1枚置いて差し替える運用が最もラクです。</p>
      </div>
    </section>

    <section id="reserve" class="reserve">
      <div class="container">
        <div class="reserve-box">
          <div class="text">
            <h2>ご予約</h2>
            <p>
              混雑時はご案内までお時間をいただく場合があります。人数が多い場合はお早めにご連絡ください。<br>
              <span style="color:rgba(245,247,255,.85)">電話：</span><strong>0198-24-0171</strong>
            </p>
          </div>
          <div class="reserve-actions">
            <a class="btn btn-primary" href="tel:0198240171">📞 電話で予約</a>
            <a class="btn" href="#access">📍 アクセス</a>
          </div>
        </div>
      </div>
    </section>

    <section id="gallery">
      <div class="container">
        <div class="section-head">
          <div>
            <h2>店内・写真</h2>
            <p>写真は「外観・席・鍋アップ」の3点があると、初来店の不安が減ります。</p>
          </div>
        </div>

        <div class="gallery">
          <div class="ph"><img src="images/photo1.jpg" alt="火鍋の写真（差し替え）" loading="lazy"></div>
          <div class="ph"><img src="images/photo2.jpg" alt="店内の写真（差し替え）" loading="lazy"></div>
          <div class="ph"><img src="images/photo3.jpg" alt="外観の写真（差し替え）" loading="lazy"></div>
          <div class="ph"><img src="images/photo4.jpg" alt="サイドメニューの写真（差し替え）" loading="lazy"></div>
        </div>
      </div>
    </section>

    <section id="access">
      <div class="container">
        <div class="section-head">
          <div>
            <h2>アクセス</h2>
            <p>住所：岩手県花巻市 東町4-3（地図は埋め込みURL差し替え推奨）</p>
          </div>
        </div>

        <div class="access">
          <div class="map card" aria-label="Googleマップ">
            <iframe
              title="火鍋シスター（姐妹） 地図"
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
              src="https://www.google.com/maps?q=%E5%B2%A9%E6%89%8B%E7%9C%8C%E8%8A%B1%E5%B7%BB%E5%B8%82%E6%9D%B1%E7%94%BA4-3&output=embed">
            </iframe>
          </div>

          <div class="card">
            <div class="inner">
              <h3>目印・駐車場</h3>
              <p>
                ・駐車場：<strong>（例：店舗前◯台／近隣◯台）</strong><br>
                ・目印：<strong>（例：◯◯の近く、看板の色など）</strong><br>
                ・徒歩：<strong>（例：花巻駅から◯分）</strong><br>
                <br>
                ※ここを具体的に書くと、来店トラブルが激減します。
              </p>

              <div style="margin-top:14px; display:flex; gap:10px; flex-wrap:wrap;">
                <a class="btn btn-primary" href="tel:0198240171">📞 予約する</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="info">
      <div class="container">
        <div class="section-head">
          <div>
            <h2>店舗情報</h2>
            <p>営業時間・定休日・支払いは、確定情報に置き換えてください。</p>
          </div>
        </div>

        <table class="info-table" aria-label="店舗情報一覧">
          <tr><th>店舗名</th><td>火鍋シスター（姐妹）</td></tr>
          <tr><th>住所</th><td>岩手県花巻市 東町4-3</td></tr>
          <tr><th>電話</th><td><a class="link" href="tel:0198240171">0198-24-0171</a></td></tr>
          <tr><th>営業時間</th><td>（例）11:00–14:00 / 17:00–22:00（LO含む）</td></tr>
          <tr><th>定休日</th><td>（例）不定休（SNSで告知）</td></tr>
          <tr><th>お支払い</th><td>（例）現金／カード／QR</td></tr>
        </table>
      </div>
    </section>

    <section id="faq">
      <div class="container">
        <div class="section-head">
          <div>
            <h2>よくある質問</h2>
            <p>お客様の不安を先回りして解消すると、予約のハードルが下がります。</p>
          </div>
        </div>

        <details>
          <summary>辛さは選べますか？</summary>
          <p>はい。辛さの目安をご案内します。はじめての方は“おすすめ”からどうぞ。</p>
        </details>

        <details>
          <summary>支払い方法は何が使えますか？</summary>
          <p>（例）現金／クレジットカード／QRコード決済をご利用いただけます。</p>
        </details>

        <details>
          <summary>予約なしでも入れますか？</summary>
          <p>お席に空きがあればご案内できますが、混雑時はご予約がおすすめです。</p>
        </details>

        <details>
          <summary>駐車場はありますか？</summary>
          <p>（場所・台数・注意点）を具体的に記載してください。</p>
        </details>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <div class="foot">
        <div>© <span id="year"></span> 火鍋シスター（姐妹）</div>
        <div class="links">
          <a class="link" href="#top">↑ トップ</a>
          <a class="link" href="#reserve">予約</a>
          <a class="link" href="tel:0198240171">📞 0198-24-0171</a>
        </div>
      </div>
    </div>
  </footer>

  <script>
    document.getElementById("year").textContent = new Date().getFullYear();

    const btn = document.getElementById("hamburger");
    const menu = document.getElementById("mobileMenu");
    const links = document.querySelectorAll(".m-link");

    btn?.addEventListener("click", () => {
      const isOpen = menu.classList.toggle("open");
      btn.setAttribute("aria-expanded", String(isOpen));
      btn.textContent = isOpen ? "✕" : "☰";
    });

    links.forEach(a => {
      a.addEventListener("click", () => {
        menu.classList.remove("open");
        btn.setAttribute("aria-expanded", "false");
        btn.textContent = "☰";
      });
    });
  </script>
</body>
</html>
