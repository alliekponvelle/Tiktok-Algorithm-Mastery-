<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TikTok Algorithm Mastery ✨</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900;1000&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --pink:   #ff2d78;
    --teal:   #00e5d1;
    --purple: #a855f7;
    --yellow: #ffd166;
    --dark:   #0d0d14;
    --card:   #16162a;
    --card2:  #1e1e38;
    --text:   #f0eeff;
    --muted:  #9490b8;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Nunito', sans-serif;
    background: var(--dark);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── FLOATING BUBBLES BG ── */
  .bubbles-bg {
    position: fixed; inset: 0; pointer-events: none; z-index: 0; overflow: hidden;
  }
  .bubble {
    position: absolute;
    border-radius: 50%;
    opacity: 0.07;
    animation: floatUp linear infinite;
  }
  @keyframes floatUp {
    0%   { transform: translateY(110vh) scale(1); opacity: 0.07; }
    100% { transform: translateY(-20vh) scale(1.3); opacity: 0; }
  }

  /* ── WRAPPER ── */
  .page { position: relative; z-index: 1; }

  /* ── HERO ── */
  .hero {
    background: linear-gradient(160deg, #120d2a 0%, #1a0d2e 40%, #0d1a2a 100%);
    text-align: center;
    padding: 70px 24px 80px;
    position: relative;
    overflow: hidden;
  }
  .hero::after {
    content: '';
    position: absolute;
    bottom: -2px; left: 0; right: 0;
    height: 60px;
    background: var(--dark);
    clip-path: ellipse(55% 100% at 50% 100%);
  }
  .hero-glow {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
  }
  .hero-glow.g1 { width: 500px; height: 500px; background: rgba(255,45,120,0.18); top: -150px; left: -100px; }
  .hero-glow.g2 { width: 400px; height: 400px; background: rgba(0,229,209,0.14); top: -100px; right: -80px; }
  .hero-glow.g3 { width: 350px; height: 350px; background: rgba(168,85,247,0.14); bottom: -50px; left: 50%; transform: translateX(-50%); }

  .hero-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: linear-gradient(135deg, rgba(255,45,120,0.2), rgba(0,229,209,0.2));
    border: 1.5px solid rgba(255,255,255,0.18);
    color: #fff;
    font-size: 12px; font-weight: 800; letter-spacing: 1.5px; text-transform: uppercase;
    padding: 9px 22px; border-radius: 50px; margin-bottom: 28px;
    backdrop-filter: blur(10px);
  }
  .hero h1 {
    font-size: clamp(2.4rem, 6vw, 4rem);
    font-weight: 1000;
    line-height: 1.1;
    margin-bottom: 20px;
    color: #fff;
  }
  .hero h1 .pink  { color: var(--pink); }
  .hero h1 .teal  { color: var(--teal); }
  .hero-sub {
    font-size: 1.1rem; color: var(--muted); max-width: 600px;
    margin: 0 auto 40px; line-height: 1.8; font-weight: 600;
  }
  .hero-pills {
    display: flex; flex-wrap: wrap; justify-content: center; gap: 10px;
    max-width: 700px; margin: 0 auto;
  }
  .pill {
    background: rgba(255,255,255,0.06);
    border: 1.5px solid rgba(255,255,255,0.12);
    border-radius: 50px; padding: 8px 18px;
    font-size: 0.82rem; font-weight: 700; color: var(--text);
    display: inline-flex; align-items: center; gap: 6px;
    transition: all 0.25s;
  }
  .pill:hover { background: rgba(255,255,255,0.12); transform: translateY(-2px); }

  /* ── MAIN CONTAINER ── */
  .container { max-width: 960px; margin: 0 auto; padding: 0 20px 80px; }

  /* ── SECTION TITLE ── */
  .section-title {
    text-align: center; margin: 60px 0 32px;
  }
  .section-title .eyebrow {
    display: inline-block;
    font-size: 11px; font-weight: 900; letter-spacing: 2.5px; text-transform: uppercase;
    color: var(--teal); margin-bottom: 10px;
  }
  .section-title h2 {
    font-size: clamp(1.8rem, 4vw, 2.6rem);
    font-weight: 900; color: #fff; line-height: 1.2;
  }
  .section-title h2 span { color: var(--pink); }

  /* ── REASON CARDS (accordion) ── */
  .reasons-grid { display: flex; flex-direction: column; gap: 14px; }

  .reason-card {
    background: var(--card);
    border-radius: 22px;
    border: 2px solid rgba(255,255,255,0.07);
    overflow: hidden;
    transition: border-color 0.3s, box-shadow 0.3s;
    cursor: pointer;
  }
  .reason-card:hover  { border-color: rgba(255,255,255,0.15); }
  .reason-card.active { border-color: var(--pink); box-shadow: 0 0 30px rgba(255,45,120,0.18); }
  .reason-card.active.color-teal   { border-color: var(--teal);   box-shadow: 0 0 30px rgba(0,229,209,0.15); }
  .reason-card.active.color-purple { border-color: var(--purple); box-shadow: 0 0 30px rgba(168,85,247,0.15); }
  .reason-card.active.color-yellow { border-color: var(--yellow); box-shadow: 0 0 30px rgba(255,209,102,0.15); }

  .reason-header {
    display: flex; align-items: center; gap: 16px;
    padding: 20px 24px;
  }
  .reason-num {
    width: 46px; height: 46px; border-radius: 50%; flex-shrink: 0;
    display: flex; align-items: center; justify-content: center;
    font-size: 1rem; font-weight: 900; color: #fff;
    background: linear-gradient(135deg, var(--pink), #ff6eb4);
    box-shadow: 0 4px 16px rgba(255,45,120,0.35);
    transition: transform 0.2s;
  }
  .reason-card:hover .reason-num { transform: scale(1.08); }
  .color-teal   .reason-num { background: linear-gradient(135deg, var(--teal), #00ffd5); box-shadow: 0 4px 16px rgba(0,229,209,0.3); }
  .color-purple .reason-num { background: linear-gradient(135deg, var(--purple), #c084fc); box-shadow: 0 4px 16px rgba(168,85,247,0.3); }
  .color-yellow .reason-num { background: linear-gradient(135deg, var(--yellow), #ffec99); box-shadow: 0 4px 16px rgba(255,209,102,0.3); }

  .reason-emoji { font-size: 1.6rem; flex-shrink: 0; }
  .reason-title { font-size: 1.05rem; font-weight: 900; color: #fff; flex: 1; line-height: 1.3; }
  .reason-arrow {
    font-size: 1.1rem; color: var(--muted); transition: transform 0.3s;
    flex-shrink: 0;
  }
  .reason-card.active .reason-arrow { transform: rotate(180deg); color: var(--pink); }
  .color-teal.active   .reason-arrow { color: var(--teal);   }
  .color-purple.active .reason-arrow { color: var(--purple); }
  .color-yellow.active .reason-arrow { color: var(--yellow); }

  .reason-body {
    max-height: 0; overflow: hidden;
    transition: max-height 0.45s ease, padding 0.3s;
    padding: 0 24px;
  }
  .reason-card.active .reason-body { max-height: 600px; padding: 0 24px 24px; }

  .reason-body p {
    font-size: 0.97rem; color: #bdb8e0; line-height: 1.85; margin-bottom: 14px; font-weight: 600;
  }
  .reason-body p:last-child { margin-bottom: 0; }

  .bubble-list {
    list-style: none; display: flex; flex-direction: column; gap: 8px; margin-bottom: 14px;
  }
  .bubble-list li {
    display: flex; align-items: flex-start; gap: 10px;
    font-size: 0.93rem; font-weight: 700; color: var(--text); line-height: 1.6;
  }
  .bubble-list li .dot {
    width: 8px; height: 8px; border-radius: 50%; background: var(--pink);
    flex-shrink: 0; margin-top: 7px;
  }
  .color-teal   .bubble-list li .dot { background: var(--teal);   }
  .color-purple .bubble-list li .dot { background: var(--purple); }
  .color-yellow .bubble-list li .dot { background: var(--yellow); }

  .result-row {
    display: flex; gap: 10px; flex-wrap: wrap; margin-top: 12px;
  }
  .result-chip {
    border-radius: 50px; padding: 7px 16px;
    font-size: 0.8rem; font-weight: 800; letter-spacing: 0.3px;
    display: inline-flex; align-items: center; gap: 5px;
  }
  .chip-yes  { background: rgba(0,229,209,0.12); border: 1.5px solid rgba(0,229,209,0.3); color: var(--teal); }
  .chip-no   { background: rgba(255,45,120,0.1);  border: 1.5px solid rgba(255,45,120,0.25); color: #ff7aab; }

  /* ── BOTTOM LINE BOX ── */
  .bottom-line {
    background: linear-gradient(135deg, #1a0a22, #0a1a22);
    border: 2px solid rgba(255,45,120,0.3);
    border-radius: 28px;
    padding: 40px 36px;
    text-align: center;
    margin-top: 52px;
    position: relative;
    overflow: hidden;
  }
  .bottom-line::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse at 50% 0%, rgba(255,45,120,0.12) 0%, transparent 70%);
    pointer-events: none;
  }
  .bottom-line h3 {
    font-size: 1.7rem; font-weight: 1000; color: #fff; margin-bottom: 24px;
  }
  .bottom-line h3 span { color: var(--pink); }
  .checklist {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 12px; margin-bottom: 28px;
  }
  .check-item {
    background: rgba(255,255,255,0.05);
    border: 1.5px solid rgba(255,255,255,0.1);
    border-radius: 16px;
    padding: 14px 16px;
    display: flex; align-items: center; gap: 10px;
    font-size: 0.9rem; font-weight: 800; color: var(--text);
    transition: all 0.2s;
  }
  .check-item:hover { background: rgba(255,255,255,0.09); transform: translateY(-2px); }
  .check-icon { font-size: 1.1rem; }
  .tagline {
    font-size: 1.1rem; font-weight: 900; color: var(--muted);
    letter-spacing: 0.3px;
  }
  .tagline strong { color: var(--teal); }

  /* ── SHADOW BAN SECTION ── */
  .shadowban-section { margin-top: 60px; }
  .shadowban-hero {
    background: linear-gradient(135deg, #1a0505, #0a0505);
    border: 2px solid rgba(255,80,80,0.35);
    border-radius: 28px;
    padding: 36px 36px 28px;
    text-align: center;
    margin-bottom: 24px;
    position: relative; overflow: hidden;
  }
  .shadowban-hero::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse at 50% 0%, rgba(255,80,80,0.1) 0%, transparent 60%);
  }
  .shadowban-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(255,80,80,0.15);
    border: 1.5px solid rgba(255,80,80,0.35);
    border-radius: 50px; padding: 8px 20px;
    font-size: 11px; font-weight: 900; letter-spacing: 2px; text-transform: uppercase;
    color: #ff8080; margin-bottom: 18px;
  }
  .shadowban-hero h2 {
    font-size: clamp(1.6rem, 4vw, 2.4rem);
    font-weight: 1000; color: #fff; line-height: 1.2; margin-bottom: 14px;
  }
  .shadowban-hero p {
    font-size: 1rem; color: #cc9999; max-width: 560px; margin: 0 auto;
    line-height: 1.8; font-weight: 600;
  }

  .shadowban-steps { display: flex; flex-direction: column; gap: 12px; }
  .sb-step {
    background: var(--card);
    border: 2px solid rgba(255,255,255,0.06);
    border-radius: 20px;
    padding: 20px 24px;
    display: flex; align-items: flex-start; gap: 18px;
    transition: all 0.25s;
    position: relative; overflow: hidden;
  }
  .sb-step::before {
    content: '';
    position: absolute; left: 0; top: 0; bottom: 0; width: 4px;
    border-radius: 4px 0 0 4px;
    background: linear-gradient(180deg, var(--pink), var(--purple));
    opacity: 0;
    transition: opacity 0.3s;
  }
  .sb-step:hover { border-color: rgba(255,45,120,0.3); background: var(--card2); }
  .sb-step:hover::before { opacity: 1; }

  .sb-icon {
    width: 48px; height: 48px; border-radius: 14px; flex-shrink: 0;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.4rem;
    background: rgba(255,255,255,0.06);
    transition: transform 0.2s;
  }
  .sb-step:hover .sb-icon { transform: scale(1.1); }
  .sb-content { flex: 1; }
  .sb-label {
    font-size: 0.7rem; font-weight: 900; text-transform: uppercase;
    letter-spacing: 2px; color: var(--muted); margin-bottom: 4px;
  }
  .sb-title { font-size: 1rem; font-weight: 900; color: #fff; margin-bottom: 6px; line-height: 1.3; }
  .sb-desc  { font-size: 0.88rem; color: #9490b8; font-weight: 600; line-height: 1.7; }

  .sb-last {
    background: linear-gradient(135deg, rgba(255,45,120,0.12), rgba(168,85,247,0.12));
    border: 2px solid rgba(255,45,120,0.3) !important;
    margin-top: 4px;
  }
  .sb-last .sb-icon { background: linear-gradient(135deg, rgba(255,45,120,0.25), rgba(168,85,247,0.25)); }
  .sb-last .sb-title { color: #ff9fc8; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding: 40px 20px 60px;
    color: var(--muted);
    font-size: 0.85rem;
    font-weight: 600;
  }
  .footer span { color: var(--pink); }

  /* ── PROGRESS BAR ── */
  .progress-wrap { margin: 8px 0 0; }
  .progress-label {
    display: flex; justify-content: space-between;
    font-size: 0.75rem; font-weight: 800; color: var(--muted); margin-bottom: 5px;
  }
  .progress-bar {
    height: 7px; border-radius: 50px;
    background: rgba(255,255,255,0.07);
    overflow: hidden;
  }
  .progress-fill {
    height: 100%; border-radius: 50px;
    background: linear-gradient(90deg, var(--pink), #ff6eb4);
    width: 0%;
    transition: width 1s ease 0.3s;
  }
  .color-teal   .progress-fill { background: linear-gradient(90deg, var(--teal), #00ffd5); }
  .color-purple .progress-fill { background: linear-gradient(90deg, var(--purple), #c084fc); }
  .color-yellow .progress-fill { background: linear-gradient(90deg, var(--yellow), #ffec99); }

  /* ── RESPONSIVE ── */
  @media (max-width: 600px) {
    .hero { padding: 50px 16px 70px; }
    .reason-header { padding: 16px 18px; gap: 12px; }
    .reason-title  { font-size: 0.95rem; }
    .reason-body   { padding: 0 18px; }
    .reason-card.active .reason-body { padding: 0 18px 20px; }
    .bottom-line   { padding: 28px 20px; }
    .shadowban-hero { padding: 28px 20px 24px; }
    .sb-step { padding: 16px 18px; gap: 14px; }
    .checklist { grid-template-columns: 1fr 1fr; }
  }
</style>
</head>
<body>

<!-- Floating bubble background -->
<div class="bubbles-bg" id="bubblesBg"></div>

<div class="page">

  <!-- ══ HERO ══ -->
  <section class="hero">
    <div class="hero-glow g1"></div>
    <div class="hero-glow g2"></div>
    <div class="hero-glow g3"></div>
    <div class="hero-badge">🎵 Digital Creator Mastery</div>
    <h1>
      You <span class="pink">NEED</span> to Learn<br>
      the <span class="teal">TikTok Algorithm</span>
    </h1>
    <p class="hero-sub">This isn't optional. It's the single skill that separates creators who <em>hope</em> from creators who <em>know.</em></p>
    <div class="hero-pills">
      <span class="pill">👁️ Visibility</span>
      <span class="pill">💰 Sales Daily</span>
      <span class="pill">📡 Live Push</span>
      <span class="pill">🏆 Battle Wins</span>
      <span class="pill">📈 Scalable Income</span>
      <span class="pill">🎯 Buyer Audience</span>
    </div>
  </section>

  <div class="container">

    <!-- ══ REASONS ══ -->
    <div class="section-title">
      <div class="eyebrow">✨ Here's Why</div>
      <h2>8 Reasons the Algorithm<br><span>Changes Everything</span></h2>
    </div>

    <div class="reasons-grid" id="reasons">

      <!-- 1 -->
      <div class="reason-card color-pink" onclick="toggleCard(this)">
        <div class="reason-header">
          <div class="reason-num">1</div>
          <div class="reason-emoji">📡</div>
          <div class="reason-title">The Algorithm Controls Your VISIBILITY</div>
          <div class="reason-arrow">▼</div>
        </div>
        <div class="reason-body">
          <p>TikTok does <strong>not</strong> show your content to everyone by default. It asks a series of questions before deciding who sees your video:</p>
          <ul class="bubble-list">
            <li><span class="dot"></span>Do people watch this video?</li>
            <li><span class="dot"></span>Do they engage with it?</li>
            <li><span class="dot"></span>Do they stay 'til the end?</li>
            <li><span class="dot"></span>Do they come back for more?</li>
          </ul>
          <div class="result-row">
            <span class="result-chip chip-yes">✅ Yes → Thousands to MILLIONS</span>
            <span class="result-chip chip-no">❌ No → Content dies in minutes</span>
          </div>
          <div class="progress-wrap">
            <div class="progress-label"><span>Impact Level</span><span>Critical</span></div>
            <div class="progress-bar"><div class="progress-fill" data-width="98%"></div></div>
          </div>
        </div>
      </div>

      <!-- 2 -->
      <div class="reason-card color-teal" onclick="toggleCard(this)">
        <div class="reason-header">
          <div class="reason-num">2</div>
          <div class="reason-emoji">💵</div>
          <div class="reason-title">The Algorithm Decides How Much MONEY You Make</div>
          <div class="reason-arrow">▼</div>
        </div>
        <div class="reason-body">
          <p>No views = no money. It really is that simple. Every revenue stream you have on TikTok runs through the algorithm:</p>
          <ul class="bubble-list">
            <li><span class="dot"></span>Sales of digital products</li>
            <li><span class="dot"></span>Live viewers during battles</li>
            <li><span class="dot"></span>Gifts &amp; diamonds</li>
            <li><span class="dot"></span>Affiliate commissions</li>
            <li><span class="dot"></span>Creator Fund payouts</li>
          </ul>
          <p>You could have the <em>best product in the world</em> and still make $0 if TikTok doesn't push your content. The algorithm is the gatekeeper.</p>
          <div class="progress-wrap">
            <div class="progress-label"><span>Impact Level</span><span>Maximum</span></div>
            <div class="progress-bar"><div class="progress-fill" data-width="100%"></div></div>
          </div>
        </div>
      </div>

      <!-- 3 -->
      <div class="reason-card color-purple" onclick="toggleCard(this)">
        <div class="reason-header">
          <div class="reason-num">3</div>
          <div class="reason-emoji">🚀</div>
          <div class="reason-title">TikTok Pushes Content Based on BEHAVIOR, Not Followers</div>
          <div class="reason-arrow">▼</div>
        </div>
        <div class="reason-body">
          <p>This is your biggest advantage as a creator. Followers don't determine reach — <strong>behavior signals do.</strong></p>
          <p>With the right triggers, you can:</p>
          <ul class="bubble-list">
            <li><span class="dot"></span>Have 200 followers and go viral</li>
            <li><span class="dot"></span>Outsell creators with 100K+ followers</li>
            <li><span class="dot"></span>Win battles with a smaller account</li>
          </ul>
          <p>But ONLY if your content hits the key algorithm triggers: watch time, retention, replays, shares, and comments.</p>
          <div class="progress-wrap">
            <div class="progress-label"><span>Your Advantage</span><span>Huge</span></div>
            <div class="progress-bar"><div class="progress-fill" data-width="92%"></div></div>
          </div>
        </div>
      </div>

      <!-- 4 -->
      <div class="reason-card color-yellow" onclick="toggleCard(this)">
        <div class="reason-header">
          <div class="reason-num">4</div>
          <div class="reason-emoji">🎯</div>
          <div class="reason-title">The Algorithm Tells TikTok WHO to Show Your Content To</div>
          <div class="reason-arrow">▼</div>
        </div>
        <div class="reason-body">
          <p>TikTok "<strong>labels</strong>" your account. If you don't understand how this works:</p>
          <ul class="bubble-list">
            <li><span class="dot"></span>You get shown to the wrong audience</li>
            <li><span class="dot"></span>Your lives attract non-buyers</li>
            <li><span class="dot"></span>Your battles pull low gifters</li>
            <li><span class="dot"></span>Your page grows but doesn't convert</li>
          </ul>
          <p>Learning it means attracting <strong>buyers, not just viewers.</strong> There's a big difference between 10K watchers who never buy and 1K watchers who all buy.</p>
          <div class="progress-wrap">
            <div class="progress-label"><span>Conversion Impact</span><span>Very High</span></div>
            <div class="progress-bar"><div class="progress-fill" data-width="88%"></div></div>
          </div>
        </div>
      </div>

      <!-- 5 -->
      <div class="reason-card color-pink" onclick="toggleCard(this)">
        <div class="reason-header">
          <div class="reason-num">5</div>
          <div class="reason-emoji">📲</div>
          <div class="reason-title">The Algorithm Affects LIVE STREAMS &amp; BATTLES — Hugely</div>
          <div class="reason-arrow">▼</div>
        </div>
        <div class="reason-body">
          <p>This one's huge for live creators. During live streams, TikTok asks in real time:</p>
          <ul class="bubble-list">
            <li><span class="dot"></span>Are people staying in the room?</li>
            <li><span class="dot"></span>Are they tapping, commenting, gifting?</li>
            <li><span class="dot"></span>Are they joining fast?</li>
          </ul>
          <div class="result-row">
            <span class="result-chip chip-yes">✅ Yes → More push, more gifters, WIN battles</span>
            <span class="result-chip chip-no">❌ No → TikTok stops pushing your live</span>
          </div>
          <p style="margin-top:12px;">Knowing the algorithm helps you start lives correctly, warm up your room, trigger gifts early, and avoid dead rooms.</p>
          <div class="progress-wrap">
            <div class="progress-label"><span>Live Stream Impact</span><span>Game Changing</span></div>
            <div class="progress-bar"><div class="progress-fill" data-width="95%"></div></div>
          </div>
        </div>
      </div>

      <!-- 6 -->
      <div class="reason-card color-teal" onclick="toggleCard(this)">
        <div class="reason-header">
          <div class="reason-num">6</div>
          <div class="reason-emoji">🔄</div>
          <div class="reason-title">The Algorithm Changes — But the Patterns Don't</div>
          <div class="reason-arrow">▼</div>
        </div>
        <div class="reason-body">
          <p>People say "TikTok changes every day." That's not fully true. The surface tweaks — but the core always stays the same:</p>
          <ul class="bubble-list">
            <li><span class="dot"></span>Strong hooks that stop the scroll</li>
            <li><span class="dot"></span>Clear niche &amp; consistent content</li>
            <li><span class="dot"></span>Maximized engagement</li>
            <li><span class="dot"></span>Watch time &amp; retention</li>
          </ul>
          <p>Learning the algorithm means you <strong>adapt fast</strong> instead of guessing every time something shifts.</p>
          <div class="progress-wrap">
            <div class="progress-label"><span>Long-term Value</span><span>Forever</span></div>
            <div class="progress-bar"><div class="progress-fill" data-width="85%"></div></div>
          </div>
        </div>
      </div>

      <!-- 7 -->
      <div class="reason-card color-purple" onclick="toggleCard(this)">
        <div class="reason-header">
          <div class="reason-num">7</div>
          <div class="reason-emoji">⏱️</div>
          <div class="reason-title">It Saves You TIME and Prevents Burnout</div>
          <div class="reason-arrow">▼</div>
        </div>
        <div class="reason-body">
          <div class="result-row" style="margin-bottom:14px;">
            <span class="result-chip chip-no">❌ Without: Post daily, 12 viewers, want to quit</span>
            <span class="result-chip chip-yes">✅ With: Post less, smarter, content works for YOU</span>
          </div>
          <p>Without algorithm knowledge you post daily with no results, go live to 12 viewers, feel shadowbanned, and want to quit.</p>
          <p>With it, you post smarter not harder. Your lives get pushed. Your content works <em>for</em> you around the clock.</p>
          <div class="progress-wrap">
            <div class="progress-label"><span>Burnout Prevention</span><span>Essential</span></div>
            <div class="progress-bar"><div class="progress-fill" data-width="90%"></div></div>
          </div>
        </div>
      </div>

      <!-- 8 -->
      <div class="reason-card color-yellow" onclick="toggleCard(this)">
        <div class="reason-header">
          <div class="reason-num">8</div>
          <div class="reason-emoji">💎</div>
          <div class="reason-title">The Algorithm Is a SKILL That Pays Forever</div>
          <div class="reason-arrow">▼</div>
        </div>
        <div class="reason-body">
          <p>Once you master it, you unlock an entirely new level of opportunity:</p>
          <ul class="bubble-list">
            <li><span class="dot"></span>Grow any niche from scratch</li>
            <li><span class="dot"></span>Flip accounts for profit</li>
            <li><span class="dot"></span>Run faceless pages</li>
            <li><span class="dot"></span>Sell anything, any time</li>
            <li><span class="dot"></span>Teach it — and get paid for that too 💰</li>
          </ul>
          <p>It's one of the <strong>highest-income digital skills</strong> available right now. And once you have it, nobody can take it away.</p>
          <div class="progress-wrap">
            <div class="progress-label"><span>ROI Potential</span><span>Unlimited</span></div>
            <div class="progress-bar"><div class="progress-fill" data-width="100%"></div></div>
          </div>
        </div>
      </div>

    </div>

    <!-- ══ BOTTOM LINE ══ -->
    <div class="bottom-line">
      <h3>The <span>Bottom Line</span></h3>
      <div class="checklist">
        <div class="check-item"><span class="check-icon">✔️</span> Consistent Views</div>
        <div class="check-item"><span class="check-icon">✔️</span> Sales Every Day</div>
        <div class="check-item"><span class="check-icon">✔️</span> Strong Live Streams</div>
        <div class="check-item"><span class="check-icon">✔️</span> Winning Battles</div>
        <div class="check-item"><span class="check-icon">✔️</span> Scalable Income</div>
        <div class="check-item"><span class="check-icon">✔️</span> No More Guessing</div>
      </div>
      <p class="tagline">It's the difference between <strong>hoping</strong> and <strong>knowing.</strong></p>
    </div>

    <!-- ══ SHADOW BAN ══ -->
    <div class="shadowban-section">
      <div class="shadowban-hero">
        <div class="shadowban-badge">🚨 Emergency Guide</div>
        <h2>What Do I Do If<br>I'm Shadow Banned??</h2>
        <p>Don't panic — don't quit. Here's exactly what to do, step by step, to fight back and come back stronger.</p>
      </div>

      <div class="shadowban-steps">

        <div class="sb-step">
          <div class="sb-icon">📩</div>
          <div class="sb-content">
            <div class="sb-label">Step 01</div>
            <div class="sb-title">Reach Out to TikTok Directly</div>
            <div class="sb-desc">Send an inquiry asking them <em>why</em> you are shadow banned. Go through the Help Center and submit a formal appeal. Document everything.</div>
          </div>
        </div>

        <div class="sb-step">
          <div class="sb-icon">🔍</div>
          <div class="sb-content">
            <div class="sb-label">Step 02</div>
            <div class="sb-title">Search Your Target Audience &amp; Engage, Engage, ENGAGE</div>
            <div class="sb-desc">Go find your ideal viewers and engage with their content. Like, comment, follow. Signal to TikTok exactly who your audience is through your own behavior.</div>
          </div>
        </div>

        <div class="sb-step">
          <div class="sb-icon">🎬</div>
          <div class="sb-content">
            <div class="sb-label">Step 03</div>
            <div class="sb-title">Post More Content Targeted to Your Audience</div>
            <div class="sb-desc">Don't go silent — go strategic. Post content that speaks directly to your target audience. Every post is a signal to the algorithm about who you are and who should see you.</div>
          </div>
        </div>

        <div class="sb-step">
          <div class="sb-icon">🖼️</div>
          <div class="sb-content">
            <div class="sb-label">Step 04</div>
            <div class="sb-title">Update Your Banner to Speak to Your Audience</div>
            <div class="sb-desc">Your profile visuals send signals. Make sure your banner and bio clearly communicate your niche and attract the right people at first glance.</div>
          </div>
        </div>

        <div class="sb-step">
          <div class="sb-icon">📅</div>
          <div class="sb-content">
            <div class="sb-label">Step 05</div>
            <div class="sb-title">Be More Consistent</div>
            <div class="sb-desc">Consistency is the reset button. Regular posting tells TikTok you're a reliable creator. The algorithm rewards accounts that show up on schedule.</div>
          </div>
        </div>

        <div class="sb-step">
          <div class="sb-icon">🤝</div>
          <div class="sb-content">
            <div class="sb-label">Step 06</div>
            <div class="sb-title">Rely on Your Community to Support Your Livestreams</div>
            <div class="sb-desc">Ask your loyal followers to join your lives, engage, and gift. Their activity signals to TikTok that your lives are worth pushing to new people.</div>
          </div>
        </div>

        <div class="sb-step sb-last">
          <div class="sb-icon">🌟</div>
          <div class="sb-content">
            <div class="sb-label">Last Resort — But Don't Fear It</div>
            <div class="sb-title">Create a New Page. Don't Be Afraid of Starting Over!</div>
            <div class="sb-desc">A fresh start is not a failure — it's a superpower. You now know what you're doing. A new account with your current knowledge can grow faster than your old one ever did. Start clean, start smart.</div>
          </div>
        </div>

      </div>
    </div>

  </div>

  <!-- ══ FOOTER ══ -->
  <footer class="footer">
    Made with <span>♥</span> for Creators Who Mean Business
  </footer>

</div>

<script>
  // ── Floating Bubbles ──
  (function() {
    const bg = document.getElementById('bubblesBg');
    const colors = ['#ff2d78','#00e5d1','#a855f7','#ffd166','#ff6eb4','#00ffd5'];
    for (let i = 0; i < 18; i++) {
      const b = document.createElement('div');
      b.className = 'bubble';
      const size = Math.random() * 120 + 30;
      b.style.cssText = `
        width:${size}px; height:${size}px;
        left:${Math.random()*100}%;
        bottom:-${size}px;
        background:${colors[Math.floor(Math.random()*colors.length)]};
        animation-duration:${Math.random()*18+12}s;
        animation-delay:-${Math.random()*20}s;
      `;
      bg.appendChild(b);
    }
  })();

  // ── Accordion ──
  function toggleCard(card) {
    const wasActive = card.classList.contains('active');
    // close all
    document.querySelectorAll('.reason-card').forEach(c => c.classList.remove('active'));
    // open this one if it wasn't active
    if (!wasActive) {
      card.classList.add('active');
      // animate progress bars inside
      card.querySelectorAll('.progress-fill').forEach(bar => {
        bar.style.width = bar.getAttribute('data-width');
      });
    }
  }

  // ── Intersection Observer for progress bars that are already open ──
  // (runs on first open; subsequent opens handled above)
  document.querySelectorAll('.progress-fill').forEach(bar => {
    bar.style.width = '0%';
  });
</script>
</body>
</html>
