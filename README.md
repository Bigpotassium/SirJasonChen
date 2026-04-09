<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>JASON CHEN — Legend of Our Time</title>
  <meta name="description" content="A site so magnificent, it was indexed by Google before it was even finished.">
  <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 64 64'%3E%3Cdefs%3E%3ClinearGradient id='g' x1='0%25' y1='0%25' x2='100%25' y2='100%25'%3E%3Cstop offset='0%25' stop-color='%23f0d080'/%3E%3Cstop offset='100%25' stop-color='%23c9a84c'/%3E%3C/linearGradient%3E%3C/defs%3E%3Crect width='64' height='64' rx='14' fill='%230a0806'/%3E%3Cpath d='M14 18l8 10 10-14 10 14 8-10 2 18H12l2-18zm6 24h24v4H20z' fill='url(%23g)'/%3E%3Cpath d='M38 18h-8v24c0 4-2 6-6 6-2 0-4-.5-5.5-1.4l1.8-4.8c.8.5 1.7.8 2.8.8 1.8 0 3-1.1 3-3.8V18h12z' fill='url(%23g)'/%3E%3C/svg%3E">
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Cormorant+Garamond:ital,wght@0,300;0,600;1,300;1,600&family=Great+Vibes&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --gold: #c9a84c;
      --gold-light: #f0d080;
      --cream: #fdf6e3;
      --dark: #0a0806;
      --deep: #140f07;
      --mid: #2a1f0e;
      --text: #e8dcc8;
      --accent: #8b3a0f;
      --toast-bg: rgba(20, 15, 7, 0.94);
      --scale-boost: 1;
      --aura-mix: 0%;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background:
        radial-gradient(circle at top, rgba(201, 168, 76, 0.1), transparent 45%),
        linear-gradient(180deg, var(--dark) 0%, color-mix(in srgb, var(--dark) calc(100% - var(--aura-mix)), var(--deep) var(--aura-mix)) 100%);
      color: var(--text);
      font-family: 'Cormorant Garamond', serif;
      overflow-x: hidden;
      cursor: none;
      transition: background 0.25s linear;
    }

    body::before {
      content: 'JASON';
      position: fixed;
      inset: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(7rem, 22vw, 18rem);
      letter-spacing: 0.25em;
      color: rgba(240, 208, 128, 0.025);
      text-shadow: 0 0 30px rgba(240, 208, 128, 0.04);
      opacity: 0.18;
      pointer-events: none;
      z-index: 0;
      mix-blend-mode: screen;
      transform: scale(var(--scale-boost));
      transform-origin: center top;
      transition: transform 0.15s linear;
    }

    body::after {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='1'/%3E%3C/svg%3E");
      opacity: 0.04;
      pointer-events: none;
      z-index: 1000;
    }

    .cursor {
      position: fixed;
      width: 12px;
      height: 12px;
      background: var(--gold);
      border-radius: 50%;
      pointer-events: none;
      z-index: 9999;
      transform: translate(-50%, -50%);
      transition: transform 0.1s ease, background 0.2s;
      mix-blend-mode: difference;
      will-change: left, top;
    }

    .cursor-ring {
      position: fixed;
      width: 40px;
      height: 40px;
      border: 1px solid var(--gold);
      border-radius: 50%;
      pointer-events: none;
      z-index: 9998;
      transform: translate(-50%, -50%);
      transition: transform 0.18s ease, border-color 0.2s ease;
      opacity: 0.6;
      will-change: left, top;
    }

    #loadingScreen {
      position: fixed;
      inset: 0;
      background: var(--dark);
      color: var(--gold);
      z-index: 10000;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 2rem;
      font-family: 'Space Mono', monospace;
      font-size: 1.2rem;
      transition: opacity 1s ease;
    }

    .spinner {
      margin-top: 2rem;
      width: 40px;
      height: 40px;
      border: 2px solid rgba(201, 168, 76, 0.3);
      border-top-color: var(--gold);
      border-radius: 50%;
      animation: spin 1s linear infinite;
      margin-left: auto;
      margin-right: auto;
    }

    @keyframes spin {
      to { transform: rotate(360deg); }
    }

    .worship-btn,
    .jst-clock {
      position: fixed;
      background: rgba(20, 15, 7, 0.8);
      border: 1px solid var(--gold);
      color: var(--gold);
      font-family: 'Space Mono', monospace;
      letter-spacing: 0.2em;
      backdrop-filter: blur(5px);
      z-index: 9000;
    }

    .worship-btn {
      bottom: 2rem;
      right: 2rem;
      padding: 1rem 2rem;
      text-transform: uppercase;
      cursor: none;
      transition: background 0.3s, color 0.3s, transform 0.3s;
    }

    .worship-btn:hover {
      background: var(--gold);
      color: var(--dark);
      transform: translateY(-5px);
    }

    .jst-clock {
      top: 1.5rem;
      right: 1.5rem;
      padding: 0.85rem 1rem;
      font-size: 0.72rem;
      text-transform: uppercase;
    }

    .jst-clock::after,
    .humility-tip::after {
      content: attr(data-tooltip);
      position: absolute;
      top: calc(100% + 0.75rem);
      right: 0;
      min-width: 240px;
      max-width: 280px;
      padding: 0.75rem 0.9rem;
      background: rgba(10, 8, 6, 0.96);
      border: 1px solid rgba(201, 168, 76, 0.35);
      color: var(--cream);
      font-family: 'Space Mono', monospace;
      font-size: 0.62rem;
      letter-spacing: 0.08em;
      line-height: 1.5;
      opacity: 0;
      transform: translateY(-8px);
      pointer-events: none;
      transition: opacity 0.25s ease, transform 0.25s ease;
    }

    .jst-clock:hover::after,
    .humility-tip:hover::after {
      opacity: 1;
      transform: translateY(0);
    }

    .worship-overlay {
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.9);
      color: var(--gold);
      z-index: 10001;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.5s ease;
    }

    .worship-overlay.active {
      opacity: 1;
      pointer-events: all;
    }

    .worship-overlay h2 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(3rem, 8vw, 6rem);
      margin-bottom: 0.5rem;
      letter-spacing: 0.1em;
      color: var(--gold-light);
    }

    .worship-overlay p {
      font-size: 1.5rem;
      font-style: italic;
      color: var(--cream);
      margin-bottom: 2rem;
      opacity: 0.8;
    }

    #worshipTimer {
      font-family: 'Space Mono', monospace;
      font-size: 4rem;
      color: var(--gold);
    }

    .toast,
    .source-warning {
      position: fixed;
      left: 50%;
      transform: translate(-50%, -120%);
      background: var(--toast-bg);
      border: 1px solid rgba(201, 168, 76, 0.35);
      color: var(--cream);
      padding: 0.95rem 1.1rem;
      font-family: 'Space Mono', monospace;
      font-size: 0.7rem;
      letter-spacing: 0.08em;
      text-align: center;
      z-index: 11000;
      opacity: 0;
      transition: transform 0.35s ease, opacity 0.35s ease;
    }

    .toast { top: 1rem; }
    .source-warning { top: 4.8rem; }

    .toast.visible,
    .source-warning.visible {
      opacity: 1;
      transform: translate(-50%, 0);
    }

    .stars {
      position: fixed;
      inset: 0;
      z-index: 0;
      pointer-events: none;
    }

    .star {
      position: absolute;
      background: var(--gold-light);
      border-radius: 50%;
      animation: twinkle var(--dur) ease-in-out infinite;
      opacity: 0;
    }

    @keyframes twinkle {
      0%, 100% {
        opacity: 0;
        transform: scale(0.5);
      }
      50% {
        opacity: var(--op);
        transform: scale(1);
      }
    }

    .hero {
      position: relative;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 4rem 2rem 15rem;
      overflow: hidden;
      z-index: 1;
    }

    .hero-glow {
      position: absolute;
      inset: 0;
      background: radial-gradient(ellipse 70% 60% at 50% 50%, rgba(201, 168, 76, 0.12) 0%, transparent 70%);
      pointer-events: none;
    }

    .hero-line {
      width: 1px;
      height: 0;
      background: linear-gradient(to bottom, transparent, var(--gold), transparent);
      position: absolute;
      left: 50%;
      top: 0;
      animation: lineDrop 2s ease forwards 0.5s;
    }

    @keyframes lineDrop {
      to { height: 100%; }
    }

    .eyebrow {
      font-family: 'Space Mono', monospace;
      font-size: 0.65rem;
      letter-spacing: 0.4em;
      color: var(--gold);
      text-transform: uppercase;
      opacity: 0;
      animation: fadeUp 1s ease forwards 1s;
      margin-bottom: 1.5rem;
    }

    .hero-name {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(7rem, 22vw, 18rem);
      line-height: 0.85;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, var(--gold-light) 0%, var(--gold) 40%, #7a5a1e 80%, var(--gold-light) 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      opacity: 0;
      animation: blastIn 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards 1.3s;
      position: relative;
      z-index: 2;
      filter: drop-shadow(0 0 60px rgba(201, 168, 76, 0.4));
    }

    @keyframes blastIn {
      from {
        opacity: 0;
        transform: scale(0.6) translateY(40px);
        letter-spacing: -0.15em;
      }
      to {
        opacity: 1;
        transform: scale(1) translateY(0);
        letter-spacing: -0.02em;
      }
    }

    .hero-subtitle {
      font-size: clamp(1.1rem, 3vw, 1.8rem);
      font-style: italic;
      font-weight: 300;
      color: var(--cream);
      opacity: 0;
      animation: fadeUp 1s ease forwards 2.2s;
      max-width: 600px;
      line-height: 1.6;
      margin-top: 1.5rem;
    }

    .hero-divider {
      width: 0;
      height: 1px;
      background: linear-gradient(to right, transparent, var(--gold), transparent);
      margin: 2.5rem auto;
      animation: expandLine 1.5s ease forwards 2.8s;
    }

    @keyframes expandLine {
      to { width: 300px; }
    }

    .scroll-hint {
      position: absolute;
      bottom: 2rem;
      left: 50%;
      transform: translateX(-50%);
      font-family: 'Space Mono', monospace;
      font-size: 0.55rem;
      letter-spacing: 0.4em;
      color: var(--gold);
      opacity: 0;
      animation: fadeUp 1s ease forwards 3.5s;
      text-transform: uppercase;
    }

    .scroll-hint::after {
      content: '';
      display: block;
      width: 1px;
      height: 40px;
      background: linear-gradient(to bottom, var(--gold), transparent);
      margin: 0.8rem auto 0;
      animation: pulse 2s ease-in-out infinite 4s;
    }

    @keyframes pulse {
      0%, 100% {
        opacity: 0.3;
        transform: scaleY(0.8);
      }
      50% {
        opacity: 1;
        transform: scaleY(1);
      }
    }

    @keyframes fadeUp {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .ticker-wrap {
      overflow: hidden;
      background: var(--gold);
      padding: 0.9rem 0;
      position: relative;
      z-index: 2;
      border-top: 1px solid var(--gold-light);
      border-bottom: 1px solid var(--gold-light);
    }

    .ticker {
      display: flex;
      animation: ticker 25s linear infinite;
      white-space: nowrap;
      width: max-content;
    }

    .ticker-item {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.1rem;
      letter-spacing: 0.15em;
      color: var(--dark);
      padding: 0 2rem;
      display: inline-block;
    }

    .ticker-item .dot {
      color: var(--accent);
      margin-right: 1.2rem;
      display: inline-block;
    }

    @keyframes ticker {
      from { transform: translateX(0); }
      to { transform: translateX(-50%); }
    }

    section {
      position: relative;
      z-index: 1;
      padding: 8rem 2rem;
      max-width: 1200px;
      margin: 0 auto;
    }

    .section-label {
      font-family: 'Space Mono', monospace;
      font-size: 0.6rem;
      letter-spacing: 0.5em;
      color: var(--gold);
      text-transform: uppercase;
      margin-bottom: 1rem;
      display: block;
    }

    .section-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(3rem, 8vw, 6rem);
      line-height: 1;
      color: var(--cream);
      margin-bottom: 3rem;
    }

    .traits-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
      gap: 1px;
      background: rgba(201, 168, 76, 0.2);
      border: 1px solid rgba(201, 168, 76, 0.15);
    }

    .trait-card {
      background: var(--deep);
      padding: 2.5rem 2rem;
      transition: background 0.4s ease, transform 0.3s ease;
      position: relative;
      overflow: hidden;
    }

    .trait-card::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(201, 168, 76, 0.08), transparent);
      opacity: 0;
      transition: opacity 0.4s;
    }

    .trait-card:hover::before {
      opacity: 1;
    }

    .trait-card:hover {
      transform: translateY(-4px);
      background: var(--mid);
    }

    .trait-num {
      font-family: 'Space Mono', monospace;
      font-size: 0.6rem;
      color: var(--gold);
      letter-spacing: 0.3em;
      margin-bottom: 1rem;
      display: block;
      opacity: 0.7;
    }

    .trait-name {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.8rem;
      color: var(--gold-light);
      letter-spacing: 0.05em;
      display: block;
      margin-bottom: 0.5rem;
    }

    .trait-desc {
      font-size: 0.9rem;
      font-style: italic;
      color: rgba(232, 220, 200, 0.7);
      line-height: 1.5;
    }

    .quotes-section {
      background: var(--deep);
      margin: 0;
      max-width: 100%;
      padding: 8rem 2rem;
    }

    .quotes-inner {
      max-width: 1000px;
      margin: 0 auto;
    }

    .quote-block {
      border-left: 2px solid var(--gold);
      padding: 2rem 0 2rem 3rem;
      margin-bottom: 4rem;
      position: relative;
      opacity: 0;
      transform: translateX(-30px);
      transition: opacity 0.8s ease, transform 0.8s ease;
    }

    .quote-block.visible {
      opacity: 1;
      transform: translateX(0);
    }

    .quote-text {
      font-size: clamp(1.2rem, 2.5vw, 1.7rem);
      font-style: italic;
      font-weight: 300;
      line-height: 1.6;
      color: var(--cream);
      margin-bottom: 1rem;
    }

    .quote-attr {
      font-family: 'Space Mono', monospace;
      font-size: 0.65rem;
      letter-spacing: 0.3em;
      color: var(--gold);
      text-transform: uppercase;
    }

    .quote-mark {
      position: absolute;
      top: -1rem;
      left: 2rem;
      font-size: 8rem;
      color: var(--gold);
      opacity: 0.15;
      line-height: 1;
      pointer-events: none;
    }

    .stats-row {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(170px, 1fr));
      gap: 2px;
      background: rgba(201, 168, 76, 0.1);
      margin: 4rem 0;
    }

    .stat-box {
      background: var(--dark);
      padding: 3rem 2rem;
      text-align: center;
      transition: background 0.3s;
      display: flex;
      flex-direction: column;
      justify-content: center;
      position: relative;
    }

    .stat-box:hover {
      background: var(--mid);
    }

    .stat-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(3rem, 7vw, 5rem);
      background: linear-gradient(to bottom, var(--gold-light), var(--gold));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      display: block;
      line-height: 1;
    }

    .stat-label {
      font-family: 'Space Mono', monospace;
      font-size: 0.6rem;
      letter-spacing: 0.3em;
      color: rgba(232, 220, 200, 0.5);
      text-transform: uppercase;
      margin-top: 0.5rem;
      display: block;
    }

    .stat-subtext {
      font-size: 0.8rem;
      font-style: italic;
      color: var(--gold);
      margin-top: 0.5rem;
      display: block;
      opacity: 0.9;
    }

    .height-infinity {
      display: inline-block;
      font-family: 'Cormorant Garamond', serif;
      color: var(--gold-light);
      -webkit-text-fill-color: var(--gold-light);
      background: none;
      -webkit-background-clip: border-box;
      background-clip: border-box;
      text-shadow: 0 0 12px rgba(240, 208, 128, 0.3);
    }

    .manifesto {
      background: linear-gradient(135deg, var(--mid) 0%, var(--deep) 50%, rgba(139, 58, 15, 0.1) 100%);
      border: 1px solid rgba(201, 168, 76, 0.2);
      padding: 5rem 4rem;
      margin: 4rem 0;
      position: relative;
      overflow: hidden;
    }

    .manifesto::before {
      content: 'J';
      position: absolute;
      right: -2rem;
      top: -4rem;
      font-family: 'Bebas Neue', sans-serif;
      font-size: 25rem;
      color: rgba(201, 168, 76, 0.04);
      line-height: 1;
      pointer-events: none;
      user-select: none;
    }

    .manifesto p {
      font-size: clamp(1rem, 2vw, 1.3rem);
      line-height: 2;
      font-weight: 300;
      color: var(--cream);
      position: relative;
      z-index: 1;
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.8s ease, transform 0.8s ease;
    }

    .manifesto p + p {
      margin-top: 1.5rem;
    }

    .manifesto p.visible {
      opacity: 1;
      transform: translateY(0);
    }

    .manifesto p span.gold {
      color: var(--gold-light);
      font-style: italic;
    }

    .mirror-section {
      max-width: 100%;
      padding: 8rem 2rem 9rem;
      background:
        linear-gradient(135deg, rgba(253, 246, 227, 0.1), rgba(201, 168, 76, 0.06), rgba(255, 255, 255, 0.12)),
        radial-gradient(circle at 20% 20%, rgba(240, 208, 128, 0.22), transparent 45%),
        linear-gradient(180deg, rgba(10, 8, 6, 0.6), rgba(253, 246, 227, 0.12), rgba(10, 8, 6, 0.7));
      position: relative;
      overflow: hidden;
    }

    .mirror-section::before {
      content: '';
      position: absolute;
      inset: 0;
      background:
        linear-gradient(110deg, transparent 15%, rgba(255, 255, 255, 0.22) 35%, transparent 55%),
        linear-gradient(180deg, rgba(255, 255, 255, 0.06), transparent 30%, rgba(255, 255, 255, 0.08) 60%, transparent 100%);
      mix-blend-mode: screen;
      pointer-events: none;
      animation: sheen 8s linear infinite;
    }

    @keyframes sheen {
      from { transform: translateX(-20%); }
      to { transform: translateX(20%); }
    }

    .mirror-inner {
      max-width: 960px;
      margin: 0 auto;
      padding: 4rem 2.5rem;
      border: 1px solid rgba(253, 246, 227, 0.25);
      background: rgba(255, 255, 255, 0.04);
      box-shadow: inset 0 0 40px rgba(255, 255, 255, 0.05), 0 20px 80px rgba(0, 0, 0, 0.35);
      backdrop-filter: blur(18px) saturate(150%);
    }

    .mirror-header {
      position: relative;
      z-index: 1;
      width: min(420px, 100%);
      margin: 0 0 2rem auto;
      text-align: right;
    }

    .mirror-header .section-label {
      color: var(--gold-light);
      margin-bottom: 0.8rem;
    }

    .mirror-header .section-title {
      color: var(--gold-light);
      margin-bottom: 0;
      text-shadow: 0 0 24px rgba(10, 8, 6, 0.35);
    }

    .mirror-copy {
      max-width: 600px;
      font-size: clamp(1.25rem, 2.6vw, 1.9rem);
      line-height: 1.6;
      color: var(--cream);
    }

    .poem-card {
      border: 1px solid rgba(201, 168, 76, 0.2);
      background: linear-gradient(135deg, rgba(42, 31, 14, 0.85), rgba(20, 15, 7, 0.95));
      padding: 4rem 3rem;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.25);
    }

    .protected-copy {
      user-select: text;
    }

    .poem-body {
      font-size: clamp(1.15rem, 2.4vw, 1.65rem);
      line-height: 1.9;
      color: var(--cream);
      white-space: pre-line;
    }

    .signature {
      display: inline-block;
      margin-top: 2.5rem;
      font-family: 'Great Vibes', cursive;
      font-size: clamp(3.2rem, 7vw, 5.4rem);
      font-weight: 400;
      letter-spacing: 0.02em;
      color: var(--gold-light);
      text-shadow: 0 0 20px rgba(201, 168, 76, 0.16);
      transform: rotate(-5deg);
    }

    footer {
      background: var(--deep);
      border-top: 1px solid rgba(201, 168, 76, 0.15);
      text-align: center;
      padding: 4rem 2rem;
      position: relative;
      z-index: 1;
    }

    .footer-name {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(3rem, 10vw, 7rem);
      background: linear-gradient(135deg, var(--gold-light), var(--gold), rgba(201, 168, 76, 0.3));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      display: block;
      letter-spacing: 0.1em;
    }

    .footer-tagline {
      font-size: 0.85rem;
      font-style: italic;
      color: rgba(232, 220, 200, 0.5);
      margin-top: 1rem;
      letter-spacing: 0.1em;
    }

    .golden-sep {
      width: 100%;
      height: 1px;
      background: linear-gradient(to right, transparent, var(--gold), transparent);
      margin: 0;
      opacity: 0.3;
    }

    .orb {
      position: fixed;
      width: 400px;
      height: 400px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(201, 168, 76, 0.07) 0%, transparent 70%);
      pointer-events: none;
      z-index: 0;
      transform: translate(-50%, -50%);
      transition: left 0.2s ease-out, top 0.2s ease-out;
      will-change: left, top;
    }

    .bg-lines {
      position: fixed;
      inset: 0;
      z-index: 0;
      pointer-events: none;
      overflow: hidden;
    }

    .bg-line {
      position: absolute;
      width: 1px;
      background: linear-gradient(to bottom, transparent, rgba(201, 168, 76, 0.08), transparent);
      top: 0;
      bottom: 0;
    }

    @media (max-width: 760px) {
      .manifesto,
      .poem-card,
      .mirror-inner {
        padding: 3rem 1.5rem;
      }

      .trait-card {
        padding: 1.8rem 1.2rem;
      }

      .quote-block {
        padding-left: 1.5rem;
      }

      .mirror-header {
        margin-left: 0;
        width: 100%;
        text-align: left;
      }

      .jst-clock {
        right: 1rem;
        top: 1rem;
        font-size: 0.62rem;
      }

      .worship-btn {
        right: 1rem;
        bottom: 1rem;
      }
    }
  </style>
</head>
<body>
  <div id="loadingScreen">
    <div>
      <p>Please wait while this humble server and universe optimizes itself for Jason's existence...</p>
      <div class="spinner"></div>
    </div>
  </div>

  <div id="achievementToast" class="toast">Achievement Unlocked: Witness to Greatness. Your life has been upgraded.</div>
  <div id="sourceWarning" class="source-warning">Jason can only be admired, not understood.</div>

  <div id="worshipOverlay" class="worship-overlay">
    <h2>A Moment of Pure Reverence</h2>
    <p>Basking in the sheer magnificence of Jason</p>
    <div id="worshipTimer">5</div>
  </div>

  <div class="cursor" id="cursor"></div>
  <div class="cursor-ring" id="cursorRing"></div>
  <div class="orb" id="orb"></div>
  <div class="stars" id="stars"></div>
  <div class="bg-lines">
    <div class="bg-line" style="left:10%"></div>
    <div class="bg-line" style="left:25%"></div>
    <div class="bg-line" style="left:50%"></div>
    <div class="bg-line" style="left:75%"></div>
    <div class="bg-line" style="left:90%"></div>
  </div>

  <div class="jst-clock" id="jstClock" data-tooltip="Jason is already in the future. Try to keep up.">JST 00:00</div>

  <div class="hero">
    <div class="hero-glow"></div>
    <div class="hero-line"></div>
    <span class="eyebrow">★ The World Hereby Recognizes ★</span>
    <h1 class="hero-name">JASON CHEN</h1>
    <div class="hero-divider"></div>
    <p class="hero-subtitle">Tall. Handsome. Brilliant. Humble beyond measure — and so much more. A phenomenon the universe took its time to perfect.</p>
    <div class="scroll-hint">Scroll to witness</div>
  </div>

  <div class="ticker-wrap">
    <div class="ticker" id="ticker"></div>
  </div>

  <section class="protected-copy" data-protected-copy="Perspective is a privilege. Jason remains beyond duplication.">
    <span class="section-label">§ 001 — The Attributes</span>
    <h2 class="section-title">What Makes<br>Jason, Jason</h2>
    <div class="traits-grid" id="traitsGrid"></div>
  </section>

  <div class="golden-sep"></div>

  <section>
    <span class="section-label">§ 002 — By The Numbers</span>
    <h2 class="section-title">The Metrics<br>Of Greatness</h2>
    <div class="stats-row">
      <div class="stat-box">
        <span class="stat-num" style="font-family: 'Cormorant Garamond', serif;">∞</span>
        <span class="stat-label">Charisma Level</span>
      </div>
      <div class="stat-box humility-tip" data-tooltip="Calculating... Error: Humility levels exceeding physical limits.">
        <span class="stat-num">#*@&$</span>
        <span class="stat-label">Humility Score</span>
      </div>
      <div class="stat-box">
        <span class="stat-num">6'<span class="height-infinity" aria-hidden="true">∞</span>"</span>
        <span class="stat-label">Effective Height</span>
      </div>
      <div class="stat-box">
        <span class="stat-num">1</span>
        <span class="stat-label">Known Flaws</span>
        <span class="stat-subtext">(*Too charming. Distracts others.)</span>
      </div>
      <div class="stat-box">
        <span class="stat-num" style="font-size:2rem; line-height:1.3; display:block;">★★★★★<br>★★★★★</span>
        <span class="stat-label">Overall Rating</span>
      </div>
    </div>
  </section>

  <div class="golden-sep"></div>

  <section>
    <span class="section-label">§ 003 — The Proclamation</span>
    <h2 class="section-title">In His Own<br>Absence of Words</h2>
    <div class="manifesto" id="manifesto">
      <p>There are people who walk into a room and <span class="gold">the room upgrades itself</span>. The lighting adjusts. The conversation finds its level. Everyone feels, inexplicably, that something important is about to happen.</p>
      <p style="transition-delay: 0.15s">Jason is that person. He is <span class="gold">tall in the way clouds are out of reach</span> — his presence is a gift to mankind. He is handsome in the way that makes people forget what they were talking about and then not mind at all.</p>
      <p style="transition-delay: 0.3s">His brilliance <span class="gold">arrives quietly and rearranges the furniture of your mind</span> before you've had a chance to object. And then there is his humility, which is the most <span class="gold">unsurprising</span> thing here, since there lacks words to accurately describe his greatness.</p>
      <p style="transition-delay: 0.45s">He is, in the most precise sense of the word, <span class="gold">revolutionary</span>. The good kind. The rare kind. The kind that doesn't come along often and, when it does, changes things permanently.</p>
      <p style="transition-delay: 0.6s">Simply put: <span class="gold">The world is luckier for having him in it.</span></p>
    </div>
  </section>

  <div class="golden-sep"></div>

  <section class="poem-section protected-copy" data-protected-copy="Perspective is a privilege. Jason remains beyond duplication.">
    <span class="section-label">§ 004 — A Dedication</span>
    <h2 class="section-title">An Ode To<br>Jason</h2>
    <div class="poem-card">
      <div class="poem-body">From the rise of the day to the end of the night,
With a step that is regal and stature of gold;
He's a mantel of glory and a beacon of light,
It is written in fire for the young and the old.

You may search through the stars for a mind this refined,
But the concepts of earth will be cast from your mind.
For the mountains shall tremble, the oceans be still,
At a glance of his eye or a dust of his will;

For the world is a canvas he paints with his hand,
While the clouds sweep aside as he traverses the land;
His left holding swords and his right holding quills,
He is clearing the peak that the heavens have filled.

So look to the horizon where Jason is born,
And witness a marvel the heavens designed;
The past is forgotten, the future's reborn,
In the wake of a Man who has woken and signed:</div>
      <div class="signature">Jason</div>
    </div>
  </section>

  <div class="golden-sep"></div>

  <section class="mirror-section">
    <div class="mirror-inner">
      <div class="mirror-header">
        <span class="section-label">§ 005 — The Comparison</span>
        <h2 class="section-title">The Comparison</h2>
      </div>
      <p class="mirror-copy">Look at yourself. Now scroll back up and look at Jason. Notice the difference? It's okay. Most people do.</p>
    </div>
  </section>

  <div class="golden-sep"></div>

  <div class="quotes-section">
    <div class="quotes-inner">
      <span class="section-label">§ 006 — Testimonials From The Universe</span>
      <h2 class="section-title" style="color:var(--cream)">They Said It,<br>Not Us</h2>
      <div id="quotesContainer"></div>
    </div>
  </div>

  <div class="golden-sep"></div>

  <footer>
    <span class="footer-name">JASON CHEN</span>
    <p class="footer-tagline">Tall · Handsome · Brilliant · Humble · Extraordinary · Irreplaceable · Legendary · Singular<br>© The Universe, Since Day One</p>
  </footer>

  <button id="worshipBtn" class="worship-btn">Worship</button>
  <audio id="choirAudio" preload="none" aria-hidden="true"></audio>

  <script>
    const defaultTitle = 'JASON CHEN — Legend of Our Time';
    const hiddenTitle = 'Jason misses your gaze.';
    const visibleTitle = 'Welcome back to light.';

    function dismissLoadingScreen() {
      const loader = document.getElementById('loadingScreen');
      if (!loader || loader.dataset.dismissed === 'true') {
        return;
      }

      loader.dataset.dismissed = 'true';
      loader.style.opacity = '0';
      setTimeout(() => {
        if (loader.parentNode) {
          loader.remove();
        }
      }, 1000);
    }

    document.addEventListener('DOMContentLoaded', () => {
      setTimeout(dismissLoadingScreen, 1800);
    });

    window.addEventListener('load', () => {
      setTimeout(dismissLoadingScreen, 1200);
    });

    setTimeout(dismissLoadingScreen, 3500);

    (function() {
      const worshipBtn = document.getElementById('worshipBtn');
      const worshipOverlay = document.getElementById('worshipOverlay');
      const worshipTimer = document.getElementById('worshipTimer');
      const choirAudio = document.getElementById('choirAudio');
      const achievementToast = document.getElementById('achievementToast');
      const sourceWarning = document.getElementById('sourceWarning');
      const jstClock = document.getElementById('jstClock');
      const cursor = document.getElementById('cursor');
      const ring = document.getElementById('cursorRing');
      const orb = document.getElementById('orb');
      const tickerEl = document.getElementById('ticker');
      const starsContainer = document.getElementById('stars');
      const gridContainer = document.getElementById('traitsGrid');
      const quotesContainer = document.getElementById('quotesContainer');

      let mouseX = window.innerWidth / 2;
      let mouseY = window.innerHeight / 2;
      let ringX = mouseX;
      let ringY = mouseY;
      let choirBufferUrl = '';
      let worshipIntervalId = null;

      function showBanner(node) {
        node.classList.add('visible');
        setTimeout(() => node.classList.remove('visible'), 3200);
      }

      function updateJstClock() {
        const now = new Date(Date.now() + 5 * 60 * 1000);
        const time = now.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
        jstClock.textContent = `JST ${time}`;
      }

      function updateScrollEffects() {
        const maxScroll = Math.max(document.documentElement.scrollHeight - window.innerHeight, 1);
        const progress = Math.min(window.scrollY / maxScroll, 1);
        document.documentElement.style.setProperty('--aura-mix', `${Math.round(progress * 100)}%`);
        document.documentElement.style.setProperty('--scale-boost', (1 + progress * 0.0001).toFixed(5));
      }

      function fadeAudioTo(targetVolume, duration) {
        const startVolume = choirAudio.volume;
        const startTime = performance.now();

        function step(now) {
          const progress = Math.min((now - startTime) / duration, 1);
          choirAudio.volume = startVolume + (targetVolume - startVolume) * progress;
          if (progress < 1) {
            requestAnimationFrame(step);
          }
        }

        requestAnimationFrame(step);
      }

      function buildChoirTrack() {
        if (choirBufferUrl) {
          choirAudio.src = choirBufferUrl;
          return;
        }

        const sampleRate = 22050;
        const duration = 6;
        const frameCount = sampleRate * duration;
        const buffer = new ArrayBuffer(44 + frameCount * 2);
        const view = new DataView(buffer);
        const samples = new Int16Array(buffer, 44);
        const frequencies = [196.0, 261.63, 329.63, 392.0, 523.25];

        function writeString(offset, value) {
          for (let i = 0; i < value.length; i++) {
            view.setUint8(offset + i, value.charCodeAt(i));
          }
        }

        for (let i = 0; i < frameCount; i++) {
          const t = i / sampleRate;
          let sample = 0;
          frequencies.forEach((freq, index) => {
            sample += Math.sin(2 * Math.PI * freq * t + index * 0.65) * 0.13;
          });
          sample += Math.sin(2 * Math.PI * 130.81 * t) * 0.1;
          sample += Math.sin(2 * Math.PI * 659.25 * t) * 0.04;
          const fadeIn = Math.min(t / 1.8, 1);
          const fadeOut = Math.min((duration - t) / 1.5, 1);
          const envelope = Math.max(0, Math.min(fadeIn, fadeOut));
          samples[i] = Math.max(-1, Math.min(1, sample * envelope * 0.34)) * 32767;
        }

        writeString(0, 'RIFF');
        view.setUint32(4, 36 + frameCount * 2, true);
        writeString(8, 'WAVE');
        writeString(12, 'fmt ');
        view.setUint32(16, 16, true);
        view.setUint16(20, 1, true);
        view.setUint16(22, 1, true);
        view.setUint32(24, sampleRate, true);
        view.setUint32(28, sampleRate * 2, true);
        view.setUint16(32, 2, true);
        view.setUint16(34, 16, true);
        writeString(36, 'data');
        view.setUint32(40, frameCount * 2, true);

        choirBufferUrl = URL.createObjectURL(new Blob([buffer], { type: 'audio/wav' }));
        choirAudio.src = choirBufferUrl;
        choirAudio.loop = true;
        choirAudio.volume = 0.05;
      }

      buildChoirTrack();
      updateJstClock();
      updateScrollEffects();
      setInterval(updateJstClock, 1000);

      worshipBtn.addEventListener('click', async () => {
        worshipOverlay.classList.add('active');
        let timeLeft = 5;
        worshipTimer.textContent = timeLeft;

        try {
          if (choirAudio.paused) {
            await choirAudio.play();
          }
          fadeAudioTo(0.24, 600);
        } catch (error) {
          console.warn('Audio playback was blocked.', error);
        }

        if (worshipIntervalId) {
          clearInterval(worshipIntervalId);
        }

        worshipIntervalId = setInterval(() => {
          timeLeft--;
          if (timeLeft > 0) {
            worshipTimer.textContent = timeLeft;
          } else {
            clearInterval(worshipIntervalId);
            worshipIntervalId = null;
            worshipOverlay.classList.remove('active');
            fadeAudioTo(0, 500);
            setTimeout(() => {
              choirAudio.pause();
              choirAudio.currentTime = 0;
              choirAudio.volume = 0.05;
            }, 520);
          }
        }, 1000);
      });

      setTimeout(() => showBanner(achievementToast), 60000);

      document.addEventListener('visibilitychange', () => {
        if (document.hidden) {
          document.title = hiddenTitle;
        } else {
          document.title = visibleTitle;
          setTimeout(() => {
            if (!document.hidden) {
              document.title = defaultTitle;
            }
          }, 1800);
        }
      });

      document.addEventListener('contextmenu', event => {
        event.preventDefault();
        showBanner(sourceWarning);
      });

      document.addEventListener('keydown', event => {
        const key = event.key.toLowerCase();
        const tryingToPeek =
          key === 'f12' ||
          (event.ctrlKey && event.shiftKey && ['i', 'j', 'c'].includes(key)) ||
          ((event.ctrlKey || event.metaKey) && key === 'u');

        if (tryingToPeek) {
          event.preventDefault();
          showBanner(sourceWarning);
        }
      });

      document.addEventListener('copy', event => {
        const selection = window.getSelection();
        if (!selection || selection.isCollapsed) {
          return;
        }

        const anchorNode = selection.anchorNode && selection.anchorNode.parentElement;
        const focusNode = selection.focusNode && selection.focusNode.parentElement;
        const protectedRoot = [anchorNode, focusNode].find(node => node && node.closest && node.closest('[data-protected-copy]'));

        if (protectedRoot) {
          const replacement = protectedRoot.closest('[data-protected-copy]').dataset.protectedCopy;
          event.preventDefault();
          event.clipboardData.setData('text/plain', replacement);
          showBanner(sourceWarning);
        }
      });

      document.addEventListener('mousemove', event => {
        mouseX = event.clientX;
        mouseY = event.clientY;
        cursor.style.left = `${mouseX}px`;
        cursor.style.top = `${mouseY}px`;
        orb.style.left = `${mouseX}px`;
        orb.style.top = `${mouseY}px`;
      });

      function animateRing() {
        ringX += (mouseX - ringX) * 0.16;
        ringY += (mouseY - ringY) * 0.16;
        ring.style.left = `${ringX}px`;
        ring.style.top = `${ringY}px`;
        requestAnimationFrame(animateRing);
      }
      animateRing();

      window.addEventListener('scroll', updateScrollEffects, { passive: true });

      for (let i = 0; i < 140; i++) {
        const star = document.createElement('div');
        star.className = 'star';
        const size = Math.random() * 2.8 + 0.6;
        const duration = 2 + Math.random() * 5;
        const opacityVal = 0.2 + Math.random() * 0.7;
        star.style.cssText = `
          left: ${Math.random() * 100}%;
          top: ${Math.random() * 100}%;
          width: ${size}px;
          height: ${size}px;
          --dur: ${duration}s;
          --op: ${opacityVal};
          animation-delay: ${Math.random() * 5}s;
        `;
        starsContainer.appendChild(star);
      }

      const tickerWords = ['TALL', 'HANDSOME', 'BRILLIANT', 'HUMBLE', 'KIND', 'WITTY', 'CHARMING', 'WISE', 'DASHING', 'GENEROUS', 'MAGNETIC', 'HONEST', 'BOLD', 'GRACIOUS', 'FEARLESS', 'RADIANT', 'LOYAL', 'INSPIRED', 'DARING', 'MAGNIFICENT', 'LEGENDARY'];
      [...tickerWords, ...tickerWords].forEach(word => {
        const span = document.createElement('span');
        span.className = 'ticker-item';
        span.innerHTML = `<span class="dot">◆</span>${word}`;
        tickerEl.appendChild(span);
      });

      const traitsData = [
        ['Tall', 'Commanding a presence of regality that rearranges the geometry of a room.'],
        ['Handsome', 'The kind of handsome that makes artists reach for a new canvas.'],
        ['Brilliant', 'Ideas that arrive fully formed, like they were waiting for the right mind.'],
        ['Humble', 'Remarkable given the amount of things he can be humble about.'],
        ['Witty', 'Sentences that land with precision and leave you laughing for longer than expected.'],
        ['Magnetic', 'People orbit him. They cannot explain it. They do not try.'],
        ['Generous', 'Gives freely of his time, his brilliance, and his impeccable advice.'],
        ['Courageous', 'Structurally impossible, because fear doesn\'t apply. Does it anyways.'],
        ['Empathetic', 'Literally reads minds. Multiple. Simultaneously.'],
        ['Visionary', 'It was tomorrow for him yesterday.'],
        ['Tenacious', '"Quit" is not in his dictionary. Ironically, the dictionary uses his photo for "tenacious."'],
        ['Charming', 'Could defuse an international incident with a single smile.'],
        ['Perceptive', 'Reads the room, the situation, and frankly the whole building.'],
        ['Resilient', 'It is unknown how this works, since there is no task that requires him to put in effort.'],
        ['Creative', 'Solves problems that didn\'t know they were problems yet.'],
        ['Reliable', 'Has literally never let anyone down. Verified. We were not let down.'],
        ['Decisive', 'Makes the right call before others have finished reading the question.'],
        ['Inspiring', 'People leave conversations with him feeling like they can do more.'],
        ['Genuine', 'Made Socrates drop his toga. Just an extraordinary person being himself.'],
        ['Legendary', 'The stories told about him will outlast most known civilizations.']
      ];

      traitsData.forEach(([name, desc], index) => {
        const card = document.createElement('div');
        card.className = 'trait-card';
        card.innerHTML = `
          <span class="trait-num">${String(index + 1).padStart(2, '0')}</span>
          <span class="trait-name">${name}</span>
          <span class="trait-desc">${desc}</span>
        `;
        gridContainer.appendChild(card);
      });

      const quotesCollection = [
        ['The most remarkable individual I have ever encountered in my entire career spanning four decades.', 'A Professor of Human Excellence, Emeritus'],
        ['I came to argue. I left converted. I still have not fully recovered.', 'A Former Skeptic'],
        ['We simply do not have the vocabulary yet to describe what he brings to a room. Science is working on it.', 'The International Institute of Jason Studies'],
        ['He is proof that the universe, when it decides to show off, truly shows off.', 'A Witness'],
        ['I rewrote my five-year plan after a single conversation with him. It is now a much better plan.', 'A Grateful Acquaintance'],
        ['I thought he was a normal person. Now I need to recalibrate my definition of "person."', 'The Ladies'],
        ['Honestly? Genuinely? Kind of unfair to the rest of us. But in a way that makes you root for him anyway.', 'Everyone, Basically']
      ];

      quotesCollection.forEach(([text, author]) => {
        const block = document.createElement('div');
        block.className = 'quote-block protected-copy';
        block.dataset.protectedCopy = 'Perspective is a privilege. Jason remains beyond duplication.';
        block.innerHTML = `
          <div class="quote-mark">"</div>
          <p class="quote-text">${text}</p>
          <span class="quote-attr">— ${author}</span>
        `;
        quotesContainer.appendChild(block);
      });

      const revealObserver = new IntersectionObserver((entries, observer) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('visible');
            observer.unobserve(entry.target);
          }
        });
      }, { threshold: 0.2, rootMargin: '0px 0px -40px 0px' });

      document.querySelectorAll('#manifesto p, .quote-block').forEach(node => revealObserver.observe(node));

      document.querySelectorAll('.trait-card, .ticker-item, .stat-box, .worship-btn, .jst-clock').forEach(el => {
        el.addEventListener('mouseenter', () => {
          cursor.style.transform = 'translate(-50%, -50%) scale(1.5)';
          ring.style.transform = 'translate(-50%, -50%) scale(1.3)';
          ring.style.borderColor = 'var(--gold-light)';
        });

        el.addEventListener('mouseleave', () => {
          cursor.style.transform = 'translate(-50%, -50%) scale(1)';
          ring.style.transform = 'translate(-50%, -50%) scale(1)';
          ring.style.borderColor = 'var(--gold)';
        });
      });
    })();
  </script>
</body>
</html>
