# Sandgate-Barbershop-html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sandgate Barbershop — 5 Fifth Ave, Sandgate QLD</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Oswald:wght@400;500;600;700&family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,500;1,9..144,400;1,9..144,500&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#15161d;
    --ink-2:#1d1f28;
    --cream:#f2e8d3;
    --cream-dim:#cfc4ab;
    --brass:#c9a24b;
    --brass-bright:#e2c374;
    --red:#9c2b2b;
    --teal:#33544f;
    --line: rgba(242,232,211,0.14);
    --radius: 2px;
  }

  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--ink);
    color:var(--cream);
    font-family:'IBM Plex Mono', monospace;
    line-height:1.6;
    overflow-x:hidden;
  }

  ::selection{ background:var(--brass); color:var(--ink); }

  h1,h2,h3{
    font-family:'Oswald', sans-serif;
    text-transform:uppercase;
    letter-spacing:0.02em;
    font-weight:600;
    color:var(--cream);
  }

  .tagline, .quote-mark, em.script{
    font-family:'Fraunces', serif;
    font-style:italic;
    font-weight:400;
    text-transform:none;
    letter-spacing:0;
  }

  a{ color:inherit; text-decoration:none; }

  .eyebrow{
    font-family:'IBM Plex Mono', monospace;
    font-size:0.72rem;
    letter-spacing:0.28em;
    text-transform:uppercase;
    color:var(--brass);
  }

  .wrap{
    max-width:1120px;
    margin:0 auto;
    padding:0 28px;
  }

  /* ---------- Barber pole signature ---------- */
  .pole-rail{
    position:fixed;
    top:0; left:0;
    width:10px; height:100vh;
    z-index:40;
    background:repeating-linear-gradient(
      -45deg,
      var(--red) 0 14px,
      var(--cream) 14px 28px,
      var(--teal) 28px 42px,
      var(--cream) 42px 56px
    );
    background-size:200% 200%;
    animation: pole-turn 6s linear infinite;
    box-shadow: 2px 0 12px rgba(0,0,0,0.4);
  }
  @keyframes pole-turn{
    0%{ background-position:0 0; }
    100%{ background-position:0 -112px; }
  }
  @media (max-width:720px){ .pole-rail{ width:6px; } }

  .pole-divider{
    height:6px;
    width:100%;
    background:repeating-linear-gradient(
      -45deg,
      var(--red) 0 14px,
      var(--cream) 14px 28px,
      var(--teal) 28px 42px,
      var(--cream) 42px 56px
    );
    background-size:200% 200%;
    animation: pole-turn 5s linear infinite;
    opacity:0.9;
  }

  /* ---------- Header ---------- */
  header{
    position:sticky; top:0; z-index:30;
    background:rgba(21,22,29,0.92);
    backdrop-filter:blur(6px);
    border-bottom:1px solid var(--line);
    padding-left:10px;
  }
  .nav{
    display:flex; align-items:center; justify-content:space-between;
    padding:18px 28px;
    max-width:1120px; margin:0 auto;
  }
  .brand{
    font-family:'Oswald', sans-serif;
    font-size:1.05rem;
    font-weight:700;
    letter-spacing:0.08em;
    text-transform:uppercase;
    display:flex; align-items:center; gap:10px;
  }
  .brand-mark{
    width:22px; height:22px;
    border-radius:50%;
    background:repeating-linear-gradient(-45deg, var(--red) 0 4px, var(--cream) 4px 8px, var(--teal) 8px 12px, var(--cream) 12px 16px);
    background-size:200% 200%;
    animation: pole-turn 4s linear infinite;
    flex-shrink:0;
    border:1px solid var(--line);
  }
  nav.links{ display:flex; gap:28px; font-size:0.78rem; letter-spacing:0.14em; text-transform:uppercase; }
  nav.links a{ color:var(--cream-dim); transition:color 0.2s; }
  nav.links a:hover{ color:var(--brass-bright); }
  .nav-cta{
    border:1px solid var(--brass);
    color:var(--brass-bright);
    padding:9px 18px;
    font-size:0.72rem;
    letter-spacing:0.18em;
    text-transform:uppercase;
    transition:all 0.2s;
  }
  .nav-cta:hover{ background:var(--brass); color:var(--ink); }
  @media (max-width:760px){ nav.links{ display:none; } }

  /* ---------- Hero ---------- */
  .hero{
    padding-left:10px;
    position:relative;
    padding-top:min(14vh,120px);
    padding-bottom:80px;
    border-bottom:1px solid var(--line);
    overflow:hidden;
  }
  .hero::before{
    content:"";
    position:absolute;
    top:-20%; right:-10%;
    width:60vw; height:60vw;
    max-width:700px; max-height:700px;
    background:radial-gradient(circle, rgba(201,162,75,0.10) 0%, transparent 70%);
    pointer-events:none;
  }
  .hero-grid{
    display:grid;
    grid-template-columns:1.3fr 0.9fr;
    gap:60px;
    align-items:center;
  }
  @media (max-width:860px){ .hero-grid{ grid-template-columns:1fr; } }

  .rating-badge{
    display:inline-flex; align-items:center; gap:10px;
    border:1px solid var(--line);
    padding:8px 14px;
    font-size:0.78rem;
    margin-bottom:28px;
    letter-spacing:0.04em;
  }
  .stars{ color:var(--brass-bright); letter-spacing:2px; }

  .hero h1{
    font-size:clamp(2.6rem, 7vw, 5.2rem);
    line-height:0.96;
    margin-bottom:22px;
  }
  .hero h1 span{ display:block; }
  .hero h1 .accent{ color:var(--red); -webkit-text-stroke:0; }

  .hero .tagline{
    font-size:clamp(1.1rem, 2vw, 1.5rem);
    color:var(--cream-dim);
    max-width:520px;
    margin-bottom:36px;
  }

  .hero-ctas{ display:flex; gap:16px; flex-wrap:wrap; margin-bottom:44px; }
  .btn-primary{
    background:var(--red);
    color:var(--cream);
    padding:15px 30px;
    font-family:'IBM Plex Mono', monospace;
    font-size:0.8rem;
    letter-spacing:0.14em;
    text-transform:uppercase;
    border:1px solid var(--red);
    transition:all 0.2s;
  }
  .btn-primary:hover{ background:transparent; color:var(--red); }
  .btn-secondary{
    padding:15px 30px;
    font-size:0.8rem;
    letter-spacing:0.14em;
    text-transform:uppercase;
    border:1px solid var(--cream-dim);
    color:var(--cream);
    transition:all 0.2s;
  }
  .btn-secondary:hover{ border-color:var(--brass); color:var(--brass-bright); }

  .hero-meta{
    display:flex; gap:32px;
    font-size:0.75rem;
    color:var(--cream-dim);
    letter-spacing:0.05em;
    flex-wrap:wrap;
  }
  .hero-meta strong{ color:var(--cream); display:block; font-size:0.68rem; letter-spacing:0.16em; text-transform:uppercase; color:var(--brass); margin-bottom:4px; }

  /* Razor illustration */
  .razor-art{ position:relative; }
  .razor-svg{ width:100%; height:auto; display:block; }

  /* ---------- Ticket price list ---------- */
  .services{ padding:110px 0; padding-left:10px; border-bottom:1px solid var(--line); }
  .section-head{ margin-bottom:56px; max-width:640px; }
  .section-head .eyebrow{ margin-bottom:14px; display:block; }
  .section-head h2{ font-size:clamp(1.8rem,4vw,2.6rem); margin-bottom:16px; }
  .section-head p{ color:var(--cream-dim); font-size:0.95rem; }

  .ticket{
    border:1px solid var(--line);
    background:var(--ink-2);
    position:relative;
  }
  .ticket-row{
    display:flex; justify-content:space-between; align-items:baseline;
    padding:22px 30px;
    border-bottom:1px dashed var(--line);
    gap:20px;
  }
  .ticket-row:last-child{ border-bottom:none; }
  .ticket-row .name{ font-family:'Oswald', sans-serif; text-transform:uppercase; font-size:1.02rem; letter-spacing:0.02em; }
  .ticket-row .desc{ color:var(--cream-dim); font-size:0.8rem; margin-top:4px; font-family:'IBM Plex Mono',monospace; }
  .ticket-row .price{ font-family:'Oswald', sans-serif; font-size:1.15rem; color:var(--brass-bright); white-space:nowrap; }
  .ticket-note{
    padding:16px 30px;
    font-size:0.72rem;
    color:var(--cream-dim);
    letter-spacing:0.05em;
    border-top:1px solid var(--line);
  }

  /* ---------- Reviews ---------- */
  .reviews{ padding:110px 0; padding-left:10px; border-bottom:1px solid var(--line); background:var(--ink-2); }
  .review-top{
    display:flex; align-items:flex-end; justify-content:space-between; gap:30px; flex-wrap:wrap;
    margin-bottom:56px;
  }
  .review-score{ display:flex; align-items:baseline; gap:16px; }
  .review-score .num{ font-family:'Oswald', sans-serif; font-size:4.2rem; font-weight:700; color:var(--brass-bright); line-height:0.9; }
  .review-score .meta{ font-size:0.78rem; color:var(--cream-dim); }
  .review-score .stars{ font-size:1.1rem; display:block; margin-bottom:4px; }

  .review-grid{ display:grid; grid-template-columns:repeat(3,1fr); gap:1px; background:var(--line); border:1px solid var(--line); }
  @media (max-width:820px){ .review-grid{ grid-template-columns:1fr; } }
  .review-card{ background:var(--ink-2); padding:34px 30px; }
  .review-card .quote-mark{ font-size:2.4rem; color:var(--brass); display:block; line-height:0.6; margin-bottom:14px; }
  .review-card p{ font-size:0.92rem; color:var(--cream); margin-bottom:20px; }
  .review-card .who{ font-size:0.72rem; letter-spacing:0.1em; text-transform:uppercase; color:var(--cream-dim); }

  /* ---------- Location ---------- */
  .location{ padding:110px 0; padding-left:10px; }
  .loc-grid{ display:grid; grid-template-columns:1fr 1fr; gap:60px; align-items:start; }
  @media (max-width:860px){ .loc-grid{ grid-template-columns:1fr; } }

  .loc-list{ display:flex; flex-direction:column; gap:0; }
  .loc-item{ padding:26px 0; border-top:1px solid var(--line); }
  .loc-item:last-child{ border-bottom:1px solid var(--line); }
  .loc-item .eyebrow{ display:block; margin-bottom:10px; }
  .loc-item .val{ font-family:'Oswald', sans-serif; font-size:1.15rem; text-transform:none; letter-spacing:0.01em; }
  .loc-item .sub{ font-size:0.78rem; color:var(--cream-dim); margin-top:6px; }
  .loc-item a.val:hover{ color:var(--brass-bright); }

  .map-frame{
    border:1px solid var(--line);
    aspect-ratio: 4/3.2;
    position:relative;
    overflow:hidden;
    background:var(--ink-2);
  }
  .map-frame iframe{ width:100%; height:100%; border:0; filter:grayscale(0.4) contrast(1.05) invert(0.92) hue-rotate(180deg); }

  /* ---------- Footer ---------- */
  footer{ padding:60px 0 40px; padding-left:10px; border-top:1px solid var(--line); }
  .foot-grid{ display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:20px; }
  .foot-brand{ font-family:'Oswald', sans-serif; letter-spacing:0.08em; text-transform:uppercase; font-size:0.95rem; display:flex; align-items:center; gap:10px; }
  .foot-links{ display:flex; gap:26px; font-size:0.75rem; letter-spacing:0.08em; text-transform:uppercase; color:var(--cream-dim); }
  .foot-links a:hover{ color:var(--brass-bright); }
  .foot-fine{ margin-top:30px; font-size:0.68rem; color:var(--cream-dim); opacity:0.7; letter-spacing:0.04em; }

  @media (prefers-reduced-motion: reduce){
    .pole-rail, .pole-divider, .brand-mark{ animation:none; }
  }

  section{ scroll-margin-top:80px; }
</style>
</head>
<body>

<div class="pole-rail" aria-hidden="true"></div>

<header>
  <div class="nav">
    <div class="brand"><span class="brand-mark" aria-hidden="true"></span> Sandgate Barbershop</div>
    <nav class="links">
      <a href="#services">Services</a>
      <a href="#reviews">Reviews</a>
      <a href="#location">Location</a>
    </nav>
    <a class="nav-cta" href="tel:+61000000000">Call to Book</a>
  </div>
</header>

<section class="hero">
  <div class="wrap">
    <div class="hero-grid">
      <div>
        <div class="rating-badge">
          <span class="stars">★★★★★</span>
          <span>5.0 rating · 25 Google reviews</span>
        </div>
        <h1>
          <span>Sharp cuts,</span>
          <span class="accent">Sandgate</span>
          <span>standard.</span>
        </h1>
        <p class="tagline">A neighbourhood barbershop on Fifth Ave — straight razors, honest fades, and no rushing a good haircut.</p>
        <div class="hero-ctas">
          <a class="btn-primary" href="tel:+61000000000">Book a Chair</a>
          <a class="btn-secondary" href="#location">Get Directions</a>
        </div>
        <div class="hero-meta">
          <div><strong>Address</strong>5 Fifth Ave, Sandgate QLD 4017</div>
          <div><strong>Hours</strong>Mon–Fri 8:30–4:30 · Sat 8–12</div>
          <div><strong>Find us</strong>@ instagram.com</div>
        </div>
      </div>

      <div class="razor-art" aria-hidden="true">
        <svg class="razor-svg" viewBox="0 0 400 420" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="200" cy="210" r="170" stroke="#c9a24b" stroke-opacity="0.25" stroke-width="1"/>
          <circle cx="200" cy="210" r="130" stroke="#c9a24b" stroke-opacity="0.18" stroke-width="1"/>
          <!-- open razor -->
          <g transform="translate(70,140) rotate(-18)">
            <rect x="0" y="0" width="230" height="16" rx="3" fill="#f2e8d3" fill-opacity="0.92"/>
            <path d="M230 0 H262 C270 0 276 8 276 16 C276 24 270 32 262 32 L230 16 Z" fill="#e2c374"/>
            <rect x="-46" y="4" width="50" height="8" rx="4" fill="#9c2b2b"/>
          </g>
          <!-- comb -->
          <g transform="translate(60,300)">
            <rect x="0" y="0" width="200" height="18" rx="2" fill="#33544f"/>
            <g fill="#33544f">
              <rect x="6" y="18" width="4" height="26"/>
              <rect x="20" y="18" width="4" height="26"/>
              <rect x="34" y="18" width="4" height="26"/>
              <rect x="48" y="18" width="4" height="26"/>
              <rect x="62" y="18" width="4" height="26"/>
              <rect x="76" y="18" width="4" height="26"/>
              <rect x="90" y="18" width="4" height="26"/>
              <rect x="104" y="18" width="4" height="26"/>
              <rect x="118" y="18" width="4" height="26"/>
              <rect x="132" y="18" width="4" height="26"/>
              <rect x="146" y="18" width="4" height="26"/>
              <rect x="160" y="18" width="4" height="26"/>
              <rect x="174" y="18" width="4" height="26"/>
              <rect x="188" y="18" width="4" height="26"/>
            </g>
          </g>
          <!-- scissors -->
          <g transform="translate(230,260) rotate(24)">
            <circle cx="0" cy="0" r="16" stroke="#c9a24b" stroke-width="6" fill="none"/>
            <circle cx="0" cy="46" r="16" stroke="#c9a24b" stroke-width="6" fill="none"/>
            <path d="M12 10 L120 -60" stroke="#f2e8d3" stroke-width="7" stroke-linecap="round"/>
            <path d="M12 36 L120 96" stroke="#f2e8d3" stroke-width="7" stroke-linecap="round"/>
          </g>
        </svg>
      </div>
    </div>
  </div>
</section>

<div class="pole-divider" aria-hidden="true"></div>

<section class="services" id="services">
  <div class="wrap">
    <div class="section-head">
      <span class="eyebrow">On the Board</span>
      <h2>The <em class="script">Cut List</em></h2>
      <p>Sample pricing below — swap in your real menu and we'll drop it straight in. Every service finishes with a hot towel and a neck shave, no upsell required.</p>
    </div>

    <div class="ticket">
      <div class="ticket-row">
        <div>
          <div class="name">Classic Cut</div>
          <div class="desc">Scissor or clipper, styled &amp; finished</div>
        </div>
        <div class="price">$40</div>
      </div>
      <div class="ticket-row">
        <div>
          <div class="name">Skin Fade</div>
          <div class="desc">Precision fade, blended by hand</div>
        </div>
        <div class="price">$45</div>
      </div>
      <div class="ticket-row">
        <div>
          <div class="name">Beard Trim &amp; Shape</div>
          <div class="desc">Hot towel, line-up, oil finish</div>
        </div>
        <div class="price">$25</div>
      </div>
      <div class="ticket-row">
        <div>
          <div class="name">Cut &amp; Beard Combo</div>
          <div class="desc">Full service, front to jaw</div>
        </div>
        <div class="price">$60</div>
      </div>
      <div class="ticket-row">
        <div>
          <div class="name">Straight Razor Shave</div>
          <div class="desc">Traditional hot towel shave</div>
        </div>
        <div class="price">$35</div>
      </div>
      <div class="ticket-row">
        <div>
          <div class="name">Junior Cut (Under 12)</div>
          <div class="desc">Same care, kid-sized patience</div>
        </div>
        <div class="price">$28</div>
      </div>
      <div class="ticket-note">Prices shown are placeholders — replace with your actual menu.</div>
    </div>
  </div>
</section>

<section class="reviews" id="reviews">
  <div class="wrap">
    <div class="review-top">
      <div class="review-score">
        <div class="num">5.0</div>
        <div class="meta"><span class="stars">★★★★★</span>Based on 25 Google reviews</div>
      </div>
      <a class="btn-secondary" href="#" target="_blank" rel="noopener">Read on Google</a>
    </div>

    <div class="review-grid">
      <div class="review-card">
        <span class="quote-mark">“</span>
        <p>Great service from lovely staff.</p>
        <div class="who">Google review</div>
      </div>
      <div class="review-card">
        <span class="quote-mark">“</span>
        <p>Relaxing environment and just pure business - I like that style.</p>
        <div class="who">Google review</div>
      </div>
      <div class="review-card">
        <span class="quote-mark">“</span>
        <p>Perfect haircut with attention to detail.</p>
        <div class="who">Google review</div>
      </div>
    </div>

    <div class="review-grid" style="margin-top:1px;">
      <div class="review-card">
        <p style="font-size:0.85rem; color:var(--cream-dim);">Said his first cut here nailed exactly the style he asked for, in a relaxed, friendly shop.</p>
        <div class="who">Ambrogio Di Dio · 4 weeks ago</div>
      </div>
      <div class="review-card">
        <p style="font-size:0.85rem; color:var(--cream-dim);">Rates them the best on the north side — fast, professional, and staff who remember regulars.</p>
        <div class="who">Jure Tokic · Local Guide · 2 months ago</div>
      </div>
      <div class="review-card">
        <p style="font-size:0.85rem; color:var(--cream-dim);">Calls them the best barbers he's found on Brisbane's north side.</p>
        <div class="who">Robert Fleming · 5 months ago</div>
      </div>
    </div>
  </div>
</section>

<section class="location" id="location">
  <div class="wrap">
    <div class="section-head">
      <span class="eyebrow">Find the Chair</span>
      <h2>On Fifth Ave, <em class="script">Sandgate</em></h2>
    </div>

    <div class="loc-grid">
      <div class="loc-list">
        <div class="loc-item">
          <span class="eyebrow">Address</span>
          <a class="val" href="https://www.google.com/maps/search/?api=1&query=5+Fifth+Ave+Sandgate+QLD+4017" target="_blank" rel="noopener">5 Fifth Ave, Sandgate QLD 4017</a>
          <div class="sub">Plus code: M3J9+Q8 Sandgate, Queensland</div>
        </div>
        <div class="loc-item">
          <span class="eyebrow">Hours</span>
          <div class="val">Mon, Tue, Thu, Fri — 8:30 am–4:30 pm</div>
          <div class="sub">Saturday 8 am–12 pm · Wednesday &amp; Sunday closed</div>
        </div>
        <div class="loc-item">
          <span class="eyebrow">Instagram</span>
          <a class="val" href="https://instagram.com" target="_blank" rel="noopener">@sandgatebarbershop</a>
          <div class="sub">Swap in your real handle and link.</div>
        </div>
        <div class="loc-item">
          <span class="eyebrow">Phone</span>
          <a class="val" href="tel:+61000000000">Add phone number</a>
          <div class="sub">Walk-ins welcome, or call ahead for a chair.</div>
        </div>
      </div>

      <div class="map-frame">
        <iframe
          src="https://www.google.com/maps?q=5+Fifth+Ave,+Sandgate+QLD+4017&output=embed"
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
          title="Map to Sandgate Barbershop">
        </iframe>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="wrap">
    <div class="foot-grid">
      <div class="foot-brand"><span class="brand-mark" aria-hidden="true"></span> Sandgate Barbershop</div>
      <div class="foot-links">
        <a href="#services">Services</a>
        <a href="#reviews">Reviews</a>
        <a href="#location">Location</a>
        <a href="https://instagram.com" target="_blank" rel="noopener">Instagram</a>
      </div>
    </div>
    <div class="foot-fine">5 Fifth Ave, Sandgate QLD 4017 · Placeholder site — replace sample copy, prices, hours and photos with the real thing.</div>
  </div>
</footer>

</body>
</html>
