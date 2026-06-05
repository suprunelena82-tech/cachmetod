<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Cash Method — Метод, який перетворить ваш контент на прибуток</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Unbounded:wght@300;400;600;700;900&family=Manrope:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
/* ============================================
   CSS VARIABLES & RESET
   ============================================ */
:root {
  --black:       #0D0D0D;
  --surface:     #1A1A1A;
  --surface-2:   #222222;
  --surface-3:   #2A2A2A;
  --gold:        #FFD600;
  --gold-light:  #FFE44D;
  --gold-dim:    rgba(255,214,0,0.13);
  --red:         #CC0000;
  --cream:       #FFFFFF;
  --cream-dim:   rgba(255,255,255,0.65);
  --white:       #FFFFFF;
  --border:      rgba(255,214,0,0.22);
  --radius-sm:   8px;
  --radius-md:   16px;
  --radius-lg:   28px;
  --radius-xl:   40px;
  --font-display: 'Unbounded', sans-serif;
  --font-body:    'Manrope', sans-serif;
  --max-w: 1200px;
  --section-pad: 120px 24px;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; font-size: 16px; }

body {
  background: var(--black);
  color: var(--cream);
  font-family: var(--font-body);
  line-height: 1.6;
  overflow-x: hidden;
}

/* Grain texture overlay */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 1000;
  opacity: 0.6;
}

img { max-width: 100%; display: block; }
a { text-decoration: none; color: inherit; }

/* ============================================
   TYPOGRAPHY
   ============================================ */
.display-xl {
  font-family: var(--font-display);
  font-size: clamp(3rem, 8vw, 7rem);
  font-weight: 900;
  line-height: 0.95;
  letter-spacing: -0.03em;
}
.display-lg {
  font-family: var(--font-display);
  font-size: clamp(2rem, 5vw, 4.5rem);
  font-weight: 700;
  line-height: 1.0;
  letter-spacing: -0.025em;
}
.display-md {
  font-family: var(--font-display);
  font-size: clamp(1.4rem, 3vw, 2.5rem);
  font-weight: 700;
  line-height: 1.1;
  letter-spacing: -0.02em;
}
.heading {
  font-family: var(--font-display);
  font-size: clamp(1rem, 2vw, 1.5rem);
  font-weight: 600;
  line-height: 1.2;
  letter-spacing: -0.01em;
}
.label {
  font-family: var(--font-display);
  font-size: 0.65rem;
  font-weight: 600;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}
.body-lg { font-size: clamp(1rem, 1.5vw, 1.125rem); line-height: 1.75; font-weight: 400; }
.body-sm { font-size: 0.875rem; line-height: 1.65; font-weight: 400; }

.gold { color: var(--gold); }
.red  { color: var(--red);  }
.dim  { color: var(--cream-dim); }

/* ============================================
   LAYOUT UTILITIES
   ============================================ */
.container { max-width: var(--max-w); margin: 0 auto; padding: 0 24px; }
.section { padding: var(--section-pad); }

.grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; }
.grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; }
.grid-4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: 20px; }

/* ============================================
   COMPONENTS — BUTTONS
   ============================================ */
.btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 18px 40px;
  border-radius: 100px;
  font-family: var(--font-display);
  font-size: 0.8rem;
  font-weight: 700;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  cursor: pointer;
  border: none;
  position: relative;
  overflow: hidden;
  transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1),
              box-shadow 0.3s ease;
  text-decoration: none;
}
.btn::after {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  background: white;
  opacity: 0;
  transition: opacity 0.2s;
}
.btn:hover::after { opacity: 0.08; }
.btn:hover { transform: translateY(-3px) scale(1.02); }
.btn:active { transform: translateY(0) scale(0.98); }

.btn-gold {
  background: var(--gold);
  color: var(--black);
  box-shadow: 0 8px 32px rgba(245,166,35,0.3);
}
.btn-gold:hover { box-shadow: 0 16px 48px rgba(245,166,35,0.5); }

.btn-red {
  background: var(--red);
  color: var(--white);
  box-shadow: 0 8px 32px rgba(224,48,48,0.35);
}
.btn-red:hover { box-shadow: 0 16px 48px rgba(224,48,48,0.55); }

.btn-outline {
  background: transparent;
  color: var(--gold);
  border: 1.5px solid var(--border);
  box-shadow: none;
}
.btn-outline:hover { border-color: var(--gold); background: var(--gold-dim); }

.btn-lg { padding: 22px 56px; font-size: 0.875rem; }
.btn-xl { padding: 26px 64px; font-size: 1rem; }

/* Arrow icon in button */
.btn-arrow {
  width: 20px;
  height: 20px;
  transition: transform 0.3s ease;
}
.btn:hover .btn-arrow { transform: translateX(4px); }

/* ============================================
   COMPONENTS — CARDS
   ============================================ */
.card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 40px;
  position: relative;
  overflow: hidden;
  transition: border-color 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease;
}
.card::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  background: radial-gradient(ellipse at top left, rgba(245,166,35,0.06) 0%, transparent 60%);
  pointer-events: none;
}
.card:hover {
  border-color: rgba(245,166,35,0.4);
  transform: translateY(-4px);
  box-shadow: 0 24px 64px rgba(0,0,0,0.5), 0 0 0 1px rgba(245,166,35,0.2);
}

.card-glass {
  background: rgba(255,255,255,0.03);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: var(--radius-lg);
  padding: 40px;
}

/* ============================================
   COMPONENTS — BADGE / TAG
   ============================================ */
.badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 8px 18px;
  border-radius: 100px;
  font-family: var(--font-display);
  font-size: 0.6rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
}
.badge-gold {
  background: var(--gold-dim);
  color: var(--gold);
  border: 1px solid rgba(245,166,35,0.3);
}
.badge-red {
  background: rgba(224,48,48,0.12);
  color: #FF6B6B;
  border: 1px solid rgba(224,48,48,0.3);
}

/* ============================================
   COMPONENTS — SECTION HEADER
   ============================================ */
.section-header {
  text-align: center;
  margin-bottom: 80px;
}
.section-header .label { color: var(--gold); margin-bottom: 16px; }
.section-header .display-lg { margin-bottom: 20px; }
.section-header .body-lg { color: var(--cream-dim); max-width: 600px; margin: 0 auto; }

/* ============================================
   DIVIDER
   ============================================ */
.divider {
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--border) 30%, var(--border) 70%, transparent);
  margin: 0;
}

/* ============================================
   SCROLL ANIMATION
   ============================================ */
.reveal {
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1),
              transform 0.8s cubic-bezier(0.16, 1, 0.3, 1);
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}
.reveal-delay-1 { transition-delay: 0.1s; }
.reveal-delay-2 { transition-delay: 0.2s; }
.reveal-delay-3 { transition-delay: 0.3s; }
.reveal-delay-4 { transition-delay: 0.4s; }
.reveal-delay-5 { transition-delay: 0.5s; }

/* ============================================
   NAV
   ============================================ */
.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  padding: 20px 24px;
  transition: background 0.4s ease, backdrop-filter 0.4s ease, padding 0.3s ease;
}
.nav.scrolled {
  background: rgba(8,8,8,0.85);
  backdrop-filter: blur(24px);
  -webkit-backdrop-filter: blur(24px);
  padding: 14px 24px;
  border-bottom: 1px solid var(--border);
}
.nav-inner {
  max-width: var(--max-w);
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.nav-logo {
  font-family: var(--font-display);
  font-size: 1.1rem;
  font-weight: 900;
  letter-spacing: -0.02em;
  color: var(--white);
}
.nav-logo span { color: var(--gold); }

/* ============================================
   HERO SECTION
   ============================================ */
#hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding: 140px 24px 100px;
}

.hero-bg {
  position: absolute;
  inset: 0;
  z-index: 0;
}
.hero-bg-gradient {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse 80% 60% at 70% 50%, rgba(245,166,35,0.08) 0%, transparent 60%),
    radial-gradient(ellipse 50% 80% at 30% 20%, rgba(224,48,48,0.05) 0%, transparent 50%),
    linear-gradient(180deg, rgba(8,8,8,0) 0%, rgba(8,8,8,1) 100%);
}
.hero-grid-lines {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(245,166,35,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(245,166,35,0.04) 1px, transparent 1px);
  background-size: 80px 80px;
}
.hero-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  pointer-events: none;
}
.hero-orb-1 {
  width: 600px; height: 600px;
  background: rgba(245,166,35,0.12);
  top: -100px; right: -100px;
  animation: orbFloat 8s ease-in-out infinite;
}
.hero-orb-2 {
  width: 400px; height: 400px;
  background: rgba(224,48,48,0.07);
  bottom: 0; left: -50px;
  animation: orbFloat 10s ease-in-out infinite reverse;
}
@keyframes orbFloat {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(20px, -20px) scale(1.05); }
}

.hero-content {
  position: relative;
  z-index: 1;
  max-width: var(--max-w);
  margin: 0 auto;
  width: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: center;
}
.hero-text {}
.hero-eyebrow {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 32px;
  animation: fadeUp 0.8s ease both;
}
.hero-eyebrow-line {
  width: 40px;
  height: 2px;
  background: var(--gold);
}
.hero-title {
  margin-bottom: 28px;
  animation: fadeUp 0.8s 0.1s ease both;
}
.hero-title em {
  font-style: normal;
  color: var(--gold);
  position: relative;
  display: inline-block;
}
.hero-subtitle {
  color: var(--cream-dim);
  max-width: 500px;
  margin-bottom: 48px;
  animation: fadeUp 0.8s 0.2s ease both;
}
.hero-cta-group {
  display: flex;
  align-items: center;
  gap: 20px;
  flex-wrap: wrap;
  animation: fadeUp 0.8s 0.3s ease both;
}
.hero-stats {
  display: flex;
  gap: 40px;
  margin-top: 56px;
  padding-top: 40px;
  border-top: 1px solid var(--border);
  animation: fadeUp 0.8s 0.4s ease both;
}
.hero-stat {}
.hero-stat-num {
  font-family: var(--font-display);
  font-size: 2rem;
  font-weight: 900;
  color: var(--gold);
  line-height: 1;
  margin-bottom: 6px;
}
.hero-stat-label {
  font-size: 0.8rem;
  color: var(--cream-dim);
  text-transform: uppercase;
  letter-spacing: 0.1em;
}

.hero-visual {
  position: relative;
  animation: fadeUp 0.8s 0.2s ease both;
}
.hero-photo-wrap {
  position: relative;
  border-radius: var(--radius-xl);
  overflow: hidden;
  aspect-ratio: 4/5;
  background: var(--surface-2);
}
.hero-photo-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: grayscale(20%) contrast(1.05);
}
.hero-photo-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(180deg, transparent 40%, rgba(8,8,8,0.8) 100%);
}
.hero-photo-badge {
  position: absolute;
  bottom: 32px;
  left: 24px;
  right: 24px;
  background: rgba(8,8,8,0.7);
  backdrop-filter: blur(20px);
  border: 1px solid var(--border);
  border-radius: var(--radius-md);
  padding: 20px 24px;
}
.hero-floating-card {
  position: absolute;
  top: 40px;
  right: -24px;
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius-md);
  padding: 16px 20px;
  min-width: 160px;
  animation: cardFloat 4s ease-in-out infinite;
  box-shadow: 0 20px 60px rgba(0,0,0,0.5);
}
@keyframes cardFloat {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-8px); }
}
.hero-floating-card-2 {
  top: auto;
  bottom: 120px;
  right: -32px;
  animation-delay: 2s;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(30px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* ============================================
   FOR WHO SECTION
   ============================================ */
#for-who {
  padding: 120px 24px;
  background: linear-gradient(180deg, var(--black) 0%, var(--surface) 50%, var(--black) 100%);
}
.for-who-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}
.for-who-card {
  background: var(--surface-2);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 36px;
  position: relative;
  overflow: hidden;
  transition: all 0.3s ease;
}
.for-who-card::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at top left, rgba(245,166,35,0.05), transparent 60%);
}
.for-who-card:hover {
  border-color: rgba(245,166,35,0.35);
  transform: translateY(-4px);
  box-shadow: 0 20px 60px rgba(0,0,0,0.4);
}
.for-who-number {
  font-family: var(--font-display);
  font-size: 4rem;
  font-weight: 900;
  color: rgba(245,166,35,0.1);
  line-height: 1;
  margin-bottom: -12px;
  position: relative;
  z-index: 1;
}
.for-who-title {
  font-family: var(--font-display);
  font-size: 1rem;
  font-weight: 700;
  color: var(--white);
  margin-bottom: 12px;
  position: relative;
  z-index: 1;
}
.for-who-text {
  font-size: 0.9rem;
  color: var(--cream-dim);
  line-height: 1.7;
  position: relative;
  z-index: 1;
}
.for-who-text strong { color: var(--gold); font-weight: 600; }
.for-who-card-large {
  grid-column: span 2;
  background: linear-gradient(135deg, rgba(245,166,35,0.08) 0%, var(--surface-2) 100%);
  border-color: rgba(245,166,35,0.25);
}

/* ============================================
   BONUSES SECTION
   ============================================ */
#bonuses {
  padding: 120px 24px;
}
.bonus-main-grid {
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 24px;
  margin-bottom: 24px;
}
.bonus-card-annual {
  background: linear-gradient(135deg, rgba(245,166,35,0.15) 0%, var(--surface) 60%);
  border: 1px solid rgba(245,166,35,0.35);
  border-radius: var(--radius-xl);
  padding: 52px;
  position: relative;
  overflow: hidden;
}
.bonus-card-annual::after {
  content: '';
  position: absolute;
  top: -80px; right: -80px;
  width: 300px; height: 300px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(245,166,35,0.2), transparent 70%);
}
.bonus-card-tools {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius-xl);
  padding: 52px;
}
.bonus-list {
  list-style: none;
  margin-top: 24px;
}
.bonus-list li {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  padding: 12px 0;
  border-bottom: 1px solid var(--border);
  font-size: 0.9rem;
  color: var(--cream-dim);
}
.bonus-list li:last-child { border-bottom: none; }
.bonus-list-icon {
  width: 20px;
  height: 20px;
  background: var(--gold-dim);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  margin-top: 2px;
}
.bonus-list-icon::after {
  content: '';
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--gold);
}

/* ============================================
   TIMELINE / 5 DAYS SECTION
   ============================================ */
#days {
  padding: 120px 24px;
  background: var(--surface);
}
.timeline {
  position: relative;
  max-width: 900px;
  margin: 0 auto;
}
.timeline::before {
  content: '';
  position: absolute;
  left: 48px;
  top: 0;
  bottom: 0;
  width: 1px;
  background: linear-gradient(180deg, transparent, var(--gold) 10%, var(--gold) 90%, transparent);
  opacity: 0.3;
}
.timeline-item {
  display: grid;
  grid-template-columns: 96px 1fr;
  gap: 40px;
  padding-bottom: 64px;
  position: relative;
}
.timeline-item:last-child { padding-bottom: 0; }
.timeline-left { display: flex; flex-direction: column; align-items: center; gap: 12px; }
.timeline-dot {
  width: 96px;
  height: 96px;
  border-radius: 50%;
  background: var(--surface-2);
  border: 1px solid var(--border);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  position: relative;
  transition: all 0.3s ease;
}
.timeline-item:hover .timeline-dot {
  background: var(--gold-dim);
  border-color: var(--gold);
  box-shadow: 0 0 32px rgba(245,166,35,0.3);
}
.timeline-day-num {
  font-family: var(--font-display);
  font-size: 1.5rem;
  font-weight: 900;
  color: var(--gold);
}
.timeline-right {}
.timeline-day-label {
  font-family: var(--font-display);
  font-size: 0.6rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 8px;
}
.timeline-day-title {
  font-family: var(--font-display);
  font-size: clamp(1.1rem, 2vw, 1.5rem);
  font-weight: 700;
  color: var(--white);
  margin-bottom: 16px;
  line-height: 1.2;
}
.timeline-day-sub {
  font-size: 0.8rem;
  color: var(--gold);
  font-style: italic;
  margin-bottom: 12px;
}
.timeline-day-text {
  font-size: 0.9rem;
  color: var(--cream-dim);
  line-height: 1.75;
}
.timeline-result {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  margin-top: 16px;
  padding: 10px 20px;
  background: var(--gold-dim);
  border-radius: 100px;
  font-size: 0.8rem;
  color: var(--gold);
  font-weight: 600;
}
.timeline-result::before {
  content: '★';
  font-size: 0.75rem;
}

/* ============================================
   TRANSFORMATION SECTION
   ============================================ */
#transformation {
  padding: 120px 24px;
  background: linear-gradient(180deg, var(--surface) 0%, var(--black) 100%);
}
.transformation-grid {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  gap: 32px;
  align-items: center;
}
.transformation-card {
  border-radius: var(--radius-xl);
  padding: 48px;
  position: relative;
  overflow: hidden;
}
.transformation-before {
  background: var(--surface-2);
  border: 1px solid rgba(255,255,255,0.08);
}
.transformation-after {
  background: linear-gradient(135deg, rgba(245,166,35,0.1), var(--surface-2));
  border: 1px solid rgba(245,166,35,0.3);
}
.transformation-badge {
  display: inline-block;
  margin-bottom: 20px;
}
.transformation-text {
  font-size: 0.95rem;
  color: var(--cream-dim);
  line-height: 1.75;
}
.transformation-arrow {
  width: 56px;
  height: 56px;
  background: var(--gold);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  font-size: 1.5rem;
  color: var(--black);
}

/* ============================================
   PRICING / ACCESS SECTION
   ============================================ */
#access {
  padding: 120px 24px;
}
.price-hero {
  text-align: center;
  padding: 80px 48px;
  background: linear-gradient(135deg, rgba(245,166,35,0.1) 0%, rgba(224,48,48,0.05) 100%);
  border: 1px solid rgba(245,166,35,0.25);
  border-radius: var(--radius-xl);
  max-width: 700px;
  margin: 0 auto;
  position: relative;
  overflow: hidden;
}
.price-hero::before {
  content: '';
  position: absolute;
  top: -100px; left: 50%;
  transform: translateX(-50%);
  width: 400px; height: 200px;
  background: radial-gradient(ellipse, rgba(245,166,35,0.2), transparent 70%);
  pointer-events: none;
}
.price-amount {
  font-family: var(--font-display);
  font-size: clamp(3rem, 6vw, 5rem);
  font-weight: 900;
  color: var(--gold);
  line-height: 1;
  margin: 24px 0 8px;
}
.price-old {
  font-size: 1.2rem;
  color: var(--cream-dim);
  text-decoration: line-through;
  margin-bottom: 4px;
}
.price-save {
  display: inline-block;
  padding: 6px 16px;
  background: rgba(224,48,48,0.15);
  color: #FF6B6B;
  border-radius: 100px;
  font-size: 0.8rem;
  font-weight: 700;
  margin-bottom: 32px;
}

/* ============================================
   ABOUT SECTION
   ============================================ */
#about {
  padding: 120px 24px;
  background: var(--surface);
}
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1.4fr;
  gap: 80px;
  align-items: start;
}
.about-photo {
  position: sticky;
  top: 100px;
}
.about-photo-frame {
  position: relative;
  border-radius: var(--radius-xl);
  overflow: hidden;
  aspect-ratio: 3/4;
  background: var(--surface-2);
}
.about-photo-frame::after {
  content: '';
  position: absolute;
  inset: 0;
  background:
    linear-gradient(180deg, transparent 50%, rgba(8,8,8,0.7) 100%),
    linear-gradient(90deg, transparent 60%, rgba(8,8,8,0.4) 100%);
  pointer-events: none;
}
.about-photo-frame img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: grayscale(15%) contrast(1.1);
}
.about-photo-accent {
  position: absolute;
  bottom: -20px;
  right: -20px;
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background: var(--gold);
  opacity: 0.15;
  filter: blur(30px);
}
.about-content {}
.about-achievement {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 20px;
  background: var(--surface-2);
  border: 1px solid var(--border);
  border-radius: var(--radius-md);
  margin-bottom: 12px;
  transition: all 0.3s ease;
}
.about-achievement:hover {
  border-color: rgba(245,166,35,0.35);
}
.about-achievement-icon {
  width: 44px;
  height: 44px;
  background: var(--gold-dim);
  border-radius: var(--radius-sm);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  flex-shrink: 0;
}
.about-achievement-text {
  font-size: 0.9rem;
  color: var(--cream);
  line-height: 1.5;
}
.about-achievement-text strong {
  display: block;
  color: var(--white);
  font-weight: 600;
  margin-bottom: 2px;
}

/* ============================================
   FEATURES GRID
   ============================================ */
#features {
  padding: 120px 24px;
}
.features-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
.feature-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 36px;
  position: relative;
  overflow: hidden;
  transition: all 0.3s ease;
}
.feature-card:hover {
  border-color: rgba(245,166,35,0.35);
  transform: translateY(-4px);
  box-shadow: 0 20px 60px rgba(0,0,0,0.5);
}
.feature-icon {
  font-size: 2rem;
  margin-bottom: 20px;
  display: block;
}
.feature-title {
  font-family: var(--font-display);
  font-size: 1rem;
  font-weight: 700;
  color: var(--white);
  margin-bottom: 12px;
}
.feature-text {
  font-size: 0.875rem;
  color: var(--cream-dim);
  line-height: 1.7;
}

/* ============================================
   FAQ SECTION
   ============================================ */
#faq {
  padding: 120px 24px;
  background: var(--surface);
}
.faq-list {
  max-width: 800px;
  margin: 0 auto;
}
.faq-item {
  border-bottom: 1px solid var(--border);
}
.faq-question {
  width: 100%;
  background: none;
  border: none;
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 28px 0;
  text-align: left;
  font-family: var(--font-body);
  font-size: 1rem;
  font-weight: 600;
  color: var(--cream);
  gap: 20px;
  transition: color 0.2s;
}
.faq-question:hover { color: var(--gold); }
.faq-icon {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  border: 1px solid var(--border);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  transition: all 0.3s ease;
  font-size: 1.2rem;
  color: var(--gold);
}
.faq-item.open .faq-icon {
  background: var(--gold-dim);
  border-color: var(--gold);
  transform: rotate(45deg);
}
.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.4s ease;
}
.faq-answer-inner {
  padding-bottom: 28px;
  font-size: 0.925rem;
  color: var(--cream-dim);
  line-height: 1.75;
}

/* ============================================
   FINAL CTA
   ============================================ */
#cta {
  padding: 140px 24px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
#cta::before {
  content: '';
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse 70% 60% at 50% 50%, rgba(245,166,35,0.1), transparent 70%);
}
.cta-ghost-text {
  font-family: var(--font-display);
  font-size: clamp(4rem, 12vw, 14rem);
  font-weight: 900;
  color: rgba(245,166,35,0.04);
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  white-space: nowrap;
  pointer-events: none;
  letter-spacing: -0.05em;
}
.cta-content { position: relative; z-index: 1; }
.cta-content .display-lg { margin-bottom: 24px; }
.cta-content .body-lg { color: var(--cream-dim); max-width: 560px; margin: 0 auto 48px; }

/* ============================================
   FOOTER
   ============================================ */
footer {
  background: var(--black);
  border-top: 1px solid var(--border);
  padding: 48px 24px;
}
.footer-inner {
  max-width: var(--max-w);
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 24px;
}
.footer-copy {
  font-size: 0.8rem;
  color: rgba(242,234,216,0.3);
}

/* ============================================
   SCROLLBAR
   ============================================ */
::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: var(--black); }
::-webkit-scrollbar-thumb { background: rgba(245,166,35,0.4); border-radius: 4px; }

/* ============================================
   RESPONSIVE
   ============================================ */
@media (max-width: 1024px) {
  .hero-content { grid-template-columns: 1fr; gap: 60px; }
  .hero-visual { display: block; margin-top: 40px; }
  .hero-photo-wrap { aspect-ratio: 3/4; max-width: 340px; margin: 0 auto; }
  .about-grid { grid-template-columns: 1fr; gap: 48px; }
  .about-photo { position: static; }
  .transformation-grid { grid-template-columns: 1fr; }
  .transformation-arrow { transform: rotate(90deg); margin: 0 auto; }
  .bonus-main-grid { grid-template-columns: 1fr; }
  .features-grid { grid-template-columns: 1fr 1fr; }
}
@media (max-width: 768px) {
  .hero-visual { display: block !important; }
  :root { --section-pad: 80px 20px; }
  .for-who-grid { grid-template-columns: 1fr; }
  .for-who-card-large { grid-column: span 1; }
  .timeline { padding-left: 0; }
  .timeline::before { display: none; }
  .timeline-item { grid-template-columns: 1fr; gap: 16px; }
  .timeline-dot { width: 64px; height: 64px; }
  .features-grid { grid-template-columns: 1fr; }
  .hero-stats { flex-direction: column; gap: 20px; }
  .hero-cta-group { flex-direction: column; align-items: flex-start; }
  .footer-inner { flex-direction: column; text-align: center; }
}
</style>
</head>

<body>

<!-- ============================================
     NAVIGATION
     ============================================ -->
<nav class="nav" id="mainNav">
  <div class="nav-inner">
    <div class="nav-logo">THE <span>CASH</span> МЕТОД</div>
    <div style="display:flex;align-items:center;gap:16px;margin-right:20px;">
        <a href="#" aria-label="Instagram" style="color:var(--cream-dim);transition:color 0.2s;" onmouseover="this.style.color='var(--gold)'" onmouseout="this.style.color='var(--cream-dim)'">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
            <rect x="2" y="2" width="20" height="20" rx="5" ry="5"/>
            <circle cx="12" cy="12" r="4"/>
            <circle cx="17.5" cy="6.5" r="1.2" fill="currentColor" stroke="none"/>
          </svg>
        </a>
        <a href="#" aria-label="YouTube" style="color:var(--cream-dim);transition:color 0.2s;" onmouseover="this.style.color='var(--gold)'" onmouseout="this.style.color='var(--cream-dim)'">
          <svg width="24" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
            <path d="M22.54 6.42a2.78 2.78 0 0 0-1.95-1.96C18.88 4 12 4 12 4s-6.88 0-8.59.46A2.78 2.78 0 0 0 1.46 6.42 29 29 0 0 0 1 12a29 29 0 0 0 .46 5.58 2.78 2.78 0 0 0 1.95 1.96C5.12 20 12 20 12 20s6.88 0 8.59-.46a2.78 2.78 0 0 0 1.96-1.96A29 29 0 0 0 23 12a29 29 0 0 0-.46-5.58z"/>
            <polygon points="9.75 15.02 15.5 12 9.75 8.98 9.75 15.02" fill="currentColor" stroke="none"/>
          </svg>
        </a>
      </div><a href="#cta" class="btn btn-gold" style="padding:12px 28px;font-size:0.65rem;">Отримати доступ</a>
  </div>
</nav>

<!-- ============================================
     HERO
     ============================================ -->
<section id="hero">
  <div class="hero-bg">
    <div class="hero-grid-lines"></div>
    <div class="hero-bg-gradient"></div>
    <div class="hero-orb hero-orb-1"></div>
    <div class="hero-orb hero-orb-2"></div>
  </div>

  <div class="hero-content">
    <div class="hero-text">
      <div class="hero-eyebrow">
        <div class="hero-eyebrow-line"></div>
        <span class="label" style="color: var(--gold);">Метод, який перетворить ваш контент на прибуток</span>
      </div>

      <h1 class="display-xl hero-title">
        THE<br>
        <em>CASH</em><br>
        <span style="color:var(--cream-dim); font-weight:300;">METHOD</span>
      </h1>

      <p class="body-lg hero-subtitle">
        Перетвори за <strong style="color:var(--gold);">5 днів</strong> свій блог на бізнес-систему,
        яка генерує тобі гроші щодня.
      </p>

      <div class="hero-cta-group">
        <a href="#cta" class="btn btn-gold btn-xl">
          Забрати метод
          <svg class="btn-arrow" viewBox="0 0 20 20" fill="none">
            <path d="M4 10h12M11 5l5 5-5 5" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </a>
        <a href="#days" class="btn btn-outline">Дізнатись більше</a>
      </div>

      <div class="hero-stats">
        <div class="hero-stat">
          <div class="hero-stat-num">5</div>
          <div class="hero-stat-label">Днів до результату</div>
        </div>
        <div class="hero-stat">
          <div class="hero-stat-num">₴1М+</div>
          <div class="hero-stat-label">Зароблено учасниками</div>
        </div>
        <div class="hero-stat">
          <div class="hero-stat-num">2K+</div>
          <div class="hero-stat-label">Учасників пройшли</div>
        </div>
      </div>
    </div>

    <div class="hero-visual">
      
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ============================================
     FOR WHO
     ============================================ -->
<section id="for-who" class="section">
  <div class="container">
    <div class="section-header reveal">
      <div class="label" style="color:var(--gold);margin-bottom:16px;display:block;">Цільова аудиторія</div>
      <h2 class="display-lg">Для кого підійде<br><span class="gold">мій метод?</span></h2>
    </div>

    <div class="for-who-grid">
      <div class="for-who-card reveal reveal-delay-1">
        <div class="for-who-number">01</div>
        <div class="for-who-title">Ти експерт</div>
        <div class="for-who-text">Маєш знання у своїй ніші, але <strong>не знаєш, як монетизувати</strong> свою аудиторію. Ти вже пишеш, знімаєш, ділишся — але грошей це не приносить.</div>
      </div>

      <div class="for-who-card reveal reveal-delay-2">
        <div class="for-who-number">02</div>
        <div class="for-who-title">Ти хочеш масштабуватись</div>
        <div class="for-who-text">Вже маєш якийсь дохід, але <strong>хочеш вийти на системний рівень</strong>. Тобі потрібен чіткий план, а не черговий хаотичний рух.</div>
      </div>

      <div class="for-who-card reveal reveal-delay-3">
        <div class="for-who-number">03</div>
        <div class="for-who-title">Витрачаєш багато часу на контент</div>
        <div class="for-who-text">Сидиш годинами, придумуєш теми, знімаєш, монтуєш — а результату мало. <strong>Час перестати витрачати час</strong> і почати заробляти.</div>
      </div>

      <div class="for-who-card reveal reveal-delay-4">
        <div class="for-who-number">04</div>
        <div class="for-who-title">Ти не знаєш з чого почати</div>
        <div class="for-who-text">Бачиш як інші блогери заробляють, але <strong>не розумієш їхньої системи</strong>. Здається, ніби у них є якийсь секрет. Він є. І я тобі його розкрию.</div>
      </div>

      <div class="for-who-card for-who-card-large reveal reveal-delay-5">
        <div class="for-who-number" style="font-size:6rem; color:rgba(245,166,35,0.06);">05</div>
        <div class="for-who-title" style="font-size:1.2rem;">Тобі потрібна працюча система</div>
        <div class="for-who-text" style="font-size:1rem; max-width:600px;">Ти втомився від хаосу. Хочеш чітку систему, яка <strong>генерує гроші на автопілоті</strong>. Не просто ідеї — а покроковий механізм, перевірений на практиці.</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ============================================
     BONUSES
     ============================================ -->
<section id="bonuses" class="section">
  <div class="container">
    <div class="section-header reveal">
      <div class="label" style="color:var(--gold);margin-bottom:16px;display:block;">Додаткова цінність</div>
      <h2 class="display-lg">Тебе чекають<br><span class="gold">БОНУСИ</span></h2>
    </div>

    <div class="bonus-main-grid">
      <div class="bonus-card-annual reveal reveal-delay-1">
        <div class="badge badge-gold" style="margin-bottom:24px;">🎯 Головний бонус</div>
        <h3 class="display-md" style="margin-bottom:8px; color:var(--white);">AI-АСИСТЕНТ</h3>
        <p class="body-sm dim" style="margin-bottom:24px;">Твій особистий AI-асистент, який допоможе генерувати контент за 60 секунд. Більше не потрібно годинами думати над темами.</p>
        <ul class="bonus-list">
          <li>
            <div class="bonus-list-icon"></div>
            Генерація контент-плану за 60 секунд
          </li>
          <li>
            <div class="bonus-list-icon"></div>
            Автоматичне написання постів та скриптів
          </li>
          <li>
            <div class="bonus-list-icon"></div>
            Аналіз конкурентів та трендів
          </li>
          <li>
            <div class="bonus-list-icon"></div>
            Створення воронок та офферів
          </li>
        </ul>
      </div>

      <div class="bonus-card-tools reveal reveal-delay-2">
        <div class="badge badge-gold" style="margin-bottom:24px;">🛠️ Інструменти</div>
        <h3 class="display-md" style="margin-bottom:8px; color:var(--white);">Практичні інструменти</h3>
        <p class="body-sm dim" style="margin-bottom:24px;">Шаблони, таблиці та скрипти, які допоможуть побудувати бізнес-систему.</p>
        <ul class="bonus-list">
          <li>
            <div class="bonus-list-icon"></div>
            Планування відеоконтенту
          </li>
          <li>
            <div class="bonus-list-icon"></div>
            Шаблон ефективного лінктрі
          </li>
          <li>
            <div class="bonus-list-icon"></div>
            Чорний список рекламодавців
          </li>
          <li>
            <div class="bonus-list-icon"></div>
            Структура правильного офферу
          </li>
          <li>
            <div class="bonus-list-icon"></div>
            Таблиця-трекер для партнерок
          </li>
        </ul>
      </div>
    </div>

    <div style="text-align:center; margin-top:48px;" class="reveal">
      <a href="#cta" class="btn btn-gold btn-lg">
        Хочу бонуси та метод
        <svg class="btn-arrow" viewBox="0 0 20 20" fill="none">
          <path d="M4 10h12M11 5l5 5-5 5" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </a>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ============================================
     5 DAYS TIMELINE
     ============================================ -->
<section id="days">
  <div class="container" style="padding-top:120px; padding-bottom:120px;">
    <div class="section-header reveal">
      <div class="label" style="color:var(--gold);margin-bottom:16px;display:block;">Програма</div>
      <h2 class="display-lg">5 днів — твоя дорога<br>до <span class="gold">«грошей у касі»</span></h2>
    </div>

    <div class="timeline">
      <div class="timeline-item reveal reveal-delay-1">
        <div class="timeline-left">
          <div class="timeline-dot"><span class="timeline-day-num">1</span></div>
        </div>
        <div class="timeline-right">
          <div class="timeline-day-label">День перший</div>
          <h3 class="timeline-day-title">Позиціонування та аудиторія — Малюємо маршрут</h3>
          <div class="timeline-day-sub">Ти знайдеш свою унікальну позицію на ринку</div>
          <p class="timeline-day-text">Ти зрозумієш, хто твоя справжня аудиторія і чому вони готові платити. Без правильного позиціонування будь-які продажі — це лотерея.</p>
          <div class="timeline-result">Чіткий аватар клієнта та унікальна пропозиція</div>
        </div>
      </div>

      <div class="timeline-item reveal reveal-delay-2">
        <div class="timeline-left">
          <div class="timeline-dot"><span class="timeline-day-num">2</span></div>
        </div>
        <div class="timeline-right">
          <div class="timeline-day-label">День другий</div>
          <h3 class="timeline-day-title">Упаковка — Ставимо колеса</h3>
          <div class="timeline-day-sub">Твій профіль стане магнітом для клієнтів</div>
          <p class="timeline-day-text">Ми налаштуємо автоматичне обладнання для автоматизованої обробки та доставки замовлень. Ти будеш виглядати як справжній експерт, навіть якщо починаєш з нуля.</p>
          <div class="timeline-result">Профіль, який продає без слів</div>
        </div>
      </div>

      <div class="timeline-item reveal reveal-delay-3">
        <div class="timeline-left">
          <div class="timeline-dot"><span class="timeline-day-num">3</span></div>
        </div>
        <div class="timeline-right">
          <div class="timeline-day-label">День третій</div>
          <h3 class="timeline-day-title">Контент-система — Зав'язуємо бантик</h3>
          <div class="timeline-day-sub">Контент, що продає, а не просто набирає лайки</div>
          <p class="timeline-day-text">Ти отримаєш систему, яка дозволяє виробляти контент швидко і при цьому кожен піст буде вести до покупки. Не просто красиво — а ефективно.</p>
          <div class="timeline-result">Готовий контент-план на місяць</div>
        </div>
      </div>

      <div class="timeline-item reveal reveal-delay-4">
        <div class="timeline-left">
          <div class="timeline-dot"><span class="timeline-day-num">4</span></div>
        </div>
        <div class="timeline-right">
          <div class="timeline-day-label">День четвертий</div>
          <h3 class="timeline-day-title">Воронки — Заводимо двигун</h3>
          <div class="timeline-day-sub">Автоматичні продажі, поки ти спиш</div>
          <p class="timeline-day-text">Ти налаштуєш воронку, яка самостійно конвертує підписників у покупців. Одного разу зробив — і система працює без твоєї участі.</p>
          <div class="timeline-result">Автоматична воронка продажів</div>
        </div>
      </div>

      <div class="timeline-item reveal reveal-delay-5">
        <div class="timeline-left">
          <div class="timeline-dot"><span class="timeline-day-num">5</span></div>
        </div>
        <div class="timeline-right">
          <div class="timeline-day-label">День п'ятий</div>
          <h3 class="timeline-day-title">Продажі — Відкриваємо прийом</h3>
          <div class="timeline-day-sub">Перші гроші від системи, яку ти збудував</div>
          <p class="timeline-day-text">Ти зробиш перший продаж за допомогою нової системи. Не просто продаж — а перший крок до стабільного доходу, який зростатиме щомісяця.</p>
          <div class="timeline-result" style="background:rgba(224,48,48,0.12); color:#FF6B6B; --star-color:#FF6B6B;">Перший продаж із системи</div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ============================================
     TRANSFORMATION
     ============================================ -->
<section id="transformation">
  <div class="container" style="padding-top:120px; padding-bottom:120px;">
    <div class="section-header reveal">
      <div class="label" style="color:var(--gold);margin-bottom:16px;display:block;">Трансформація</div>
      <h2 class="display-lg">Твій результат,<br>який ти <span class="gold">отримаєш</span></h2>
    </div>

    <div class="transformation-grid reveal">
      <div class="transformation-card transformation-before">
        <div class="transformation-badge">
          <span class="badge" style="background:rgba(255,255,255,0.05); color:var(--cream-dim); border:1px solid rgba(255,255,255,0.1);">До інтенсиву</span>
        </div>
        <ul style="list-style:none; margin-top:20px;">
          <li style="display:flex;gap:12px;margin-bottom:16px;color:var(--cream-dim);font-size:0.9rem;">
            <span style="color:#666; flex-shrink:0;">✕</span> Ведеш блог без чіткої системи
          </li>
          <li style="display:flex;gap:12px;margin-bottom:16px;color:var(--cream-dim);font-size:0.9rem;">
            <span style="color:#666; flex-shrink:0;">✕</span> Витрачаєш години на контент без результату
          </li>
          <li style="display:flex;gap:12px;margin-bottom:16px;color:var(--cream-dim);font-size:0.9rem;">
            <span style="color:#666; flex-shrink:0;">✕</span> Не знаєш, як монетизувати аудиторію
          </li>
          <li style="display:flex;gap:12px;color:var(--cream-dim);font-size:0.9rem;">
            <span style="color:#666; flex-shrink:0;">✕</span> Дохід нестабільний або відсутній
          </li>
        </ul>
      </div>

      <div class="transformation-arrow">→</div>

      <div class="transformation-card transformation-after">
        <div class="transformation-badge">
          <span class="badge badge-gold">Після інтенсиву</span>
        </div>
        <ul style="list-style:none; margin-top:20px;">
          <li style="display:flex;gap:12px;margin-bottom:16px;color:var(--cream);font-size:0.9rem;">
            <span style="color:var(--gold); flex-shrink:0;">✓</span> Маєш чітку бізнес-систему в блозі
          </li>
          <li style="display:flex;gap:12px;margin-bottom:16px;color:var(--cream);font-size:0.9rem;">
            <span style="color:var(--gold); flex-shrink:0;">✓</span> Контент займає 1–2 години на тиждень
          </li>
          <li style="display:flex;gap:12px;margin-bottom:16px;color:var(--cream);font-size:0.9rem;">
            <span style="color:var(--gold); flex-shrink:0;">✓</span> Автоматичні продажі 24/7 без участі
          </li>
          <li style="display:flex;gap:12px;color:var(--cream);font-size:0.9rem;">
            <span style="color:var(--gold); flex-shrink:0;">✓</span> Стабільний та зростаючий дохід
          </li>
        </ul>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ============================================
     ABOUT
     ============================================ -->
<section id="about" class="section">
  <div class="container">
    <div class="about-grid">
      <div class="about-photo reveal">
        <div class="about-photo-frame">
          <img src="data:image/png;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4gHYSUNDX1BST0ZJTEUAAQEAAAHIAAAAAAQwAABtbnRyUkdCIFhZWiAH4AABAAEAAAAAAABhY3NwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAA9tYAAQAAAADTLQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAlkZXNjAAAA8AAAACRyWFlaAAABFAAAABRnWFlaAAABKAAAABRiWFlaAAABPAAAABR3dHB0AAABUAAAABRyVFJDAAABZAAAAChnVFJDAAABZAAAAChiVFJDAAABZAAAAChjcHJ0AAABjAAAADxtbHVjAAAAAAAAAAEAAAAMZW5VUwAAAAgAAAAcAHMAUgBHAEJYWVogAAAAAAAAb6IAADj1AAADkFhZWiAAAAAAAABimQAAt4UAABjaWFlaIAAAAAAAACSgAAAPhAAAts9YWVogAAAAAAAA9tYAAQAAAADTLXBhcmEAAAAAAAQAAAACZmYAAPKnAAANWQAAE9AAAApbAAAAAAAAAABtbHVjAAAAAAAAAAEAAAAMZW5VUwAAACAAAAAcAEcAbwBvAGcAbABlACAASQBuAGMALgAgADIAMAAxADb/2wBDAAUDBAQEAwUEBAQFBQUGBwwIBwcHBw8LCwkMEQ8SEhEPERETFhwXExQaFRERGCEYGh0dHx8fExciJCIeJBweHx7/2wBDAQUFBQcGBw4ICA4eFBEUHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh7/wAARCAY4BFgDASIAAhEBAxEB/8QAHQABAAIDAQEBAQAAAAAAAAAAAAECAwQFBgcICf/EAE0QAAIBAwIEBAUBBgMGBAMFCQABAgMEEQUhBhIxQRMiUWEHMnGBkRQII0JSobEVM2IkcoKSwdEWQ4PhNJPwFyVERVNjczVUovEYJrL/xAAaAQEBAQEBAQEAAAAAAAAAAAAAAQIDBAUG/8QAKBEBAQACAgIDAAICAgMBAAAAAAECEQMSITEEE0EiURQyBWEVI0Jx/9oADAMBAAIRAxEAPwD7wADDQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAGCCQBUE4AEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACRgATgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAGCMEgCCCwAqCcDAEAnAAgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABIwBAJwMAQSSAIwTgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAIcorq0vuVdWkv/ADIf8yAuCsalN9Jxf0Zb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" alt="Автор методу" style="width:100%;height:100%;object-fit:cover;object-position:center top;filter:grayscale(15%) contrast(1.1) brightness(0.85);">
          <div class="about-photo-accent"></div>
        </div>
      </div>

      <div class="about-content reveal reveal-delay-1">
        <div class="label" style="color:var(--gold);margin-bottom:16px;display:block;">Про автора</div>
        <div class="label" style="color:var(--gold);margin-bottom:8px;font-size:0.9rem;letter-spacing:0.05em;">Сергій Дєлєєв</div>
        <h2 class="display-md" style="margin-bottom:8px; color:var(--white);">Хто я і чому<br>мій метод працює?</h2>

        <div style="width:48px;height:3px;background:var(--gold);margin:20px 0 28px;border-radius:2px;"></div>

        <div class="body-sm dim" style="margin-bottom:32px; line-height:1.9;">
          Привіт — я Сергій Дєлєєв. До того, як я почав заробляти в інтернеті, я навчився сам — без наставників, без курсів. Витратив роки на помилки. А потім зрозумів систему — і все змінилось. Мій метод — це дистиляція всього, що я дізнався за ці роки. Стислий, чіткий і перевірений.
        </div>

        <div style="margin-bottom:12px;" class="reveal reveal-delay-2">
          <div class="about-achievement">
            <div class="about-achievement-icon">💰</div>
            <div class="about-achievement-text">
              <strong>₴3,000,000+ зароблено</strong>
              через систему контентного бізнесу
            </div>
          </div>
        </div>
        <div style="margin-bottom:12px;" class="reveal reveal-delay-3">
          <div class="about-achievement">
            <div class="about-achievement-icon">📱</div>
            <div class="about-achievement-text">
              <strong>2000+ учасників</strong>
              пройшли метод та запустили системи
            </div>
          </div>
        </div>
        <div style="margin-bottom:12px;" class="reveal reveal-delay-4">
          <div class="about-achievement">
            <div class="about-achievement-icon">🏆</div>
            <div class="about-achievement-text">
              <strong>Топ-500 у своїй ніші</strong>
              з органічним ростом без закупки реклами
            </div>
          </div>
        </div>
        <div class="reveal reveal-delay-5">
          <div class="about-achievement">
            <div class="about-achievement-icon">🌍</div>
            <div class="about-achievement-text">
              <strong>Країни: UA, PL, DE, CZ</strong>
              учасники з різних країн з однаковим результатом
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ============================================
     FEATURES / WHY
     ============================================ -->
<section id="features" class="section">
  <div class="container">
    <div class="section-header reveal">
      <div class="label" style="color:var(--gold);margin-bottom:16px;display:block;">Чому ти почнеш заробляти</div>
      <h2 class="display-lg">6 причин, чому<br><span class="gold">це працює</span></h2>
    </div>

    <div class="features-grid">
      <div class="feature-card reveal reveal-delay-1">
        <span class="feature-icon">🧲</span>
        <div class="feature-title">Магніт для клієнтів</div>
        <p class="feature-text">Правильне позиціонування перетворює твій профіль на магніт. Клієнти самі знаходять тебе — не навпаки.</p>
      </div>
      <div class="feature-card reveal reveal-delay-2">
        <span class="feature-icon">📦</span>
        <div class="feature-title">Упаковка «на мільйон»</div>
        <p class="feature-text">Збудуй профіль так, що з першого погляду зрозуміло: цьому треба довіряти. Перше враження — все.</p>
      </div>
      <div class="feature-card reveal reveal-delay-3">
        <span class="feature-icon">🎬</span>
        <div class="feature-title">Reels, що продають</div>
        <p class="feature-text">Не просто набирати перегляди, а конвертувати їх у покупців. Кожне відео — крок до продажу.</p>
      </div>
      <div class="feature-card reveal reveal-delay-1">
        <span class="feature-icon">🤖</span>
        <div class="feature-title">Автопілот в продажах</div>
        <p class="feature-text">Одного разу налаштована система продає без твоєї участі. Прокинувся — гроші вже є.</p>
      </div>
      <div class="feature-card reveal reveal-delay-2">
        <span class="feature-icon">💼</span>
        <div class="feature-title">Впевненість підприємця</div>
        <p class="feature-text">Ти більше не блогер — ти власник бізнесу. Це інший рівень мислення і доходу.</p>
      </div>
      <div class="feature-card reveal reveal-delay-3">
        <span class="feature-icon">✨</span>
        <div class="feature-title">Контент без мук</div>
        <p class="feature-text">Система, яка виробляє контент за лічені хвилини, а не години. Твій час — твій капітал.</p>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ============================================
     ACCESS / PRICING
     ============================================ -->
<section id="access" class="section">
  <div class="container">
    <div class="section-header reveal">
      <div class="label" style="color:var(--gold);margin-bottom:16px;display:block;">Доступність, що вражає</div>
      <h2 class="display-lg">Приєднатись до<br><span class="gold">THE CASH</span></h2>
    </div>

    <div class="price-hero reveal">
      <div class="badge badge-gold" style="margin-bottom:8px;">🔥 Обмежена пропозиція</div>
      <p class="body-sm dim">Ціна підвищиться після завершення набору</p>
      <div class="price-old">Вартість: 3 990 грн</div>
      <div class="price-amount">978 грн</div>
      <div class="price-save">Економія 75%</div>
      <p class="body-sm dim" style="margin-bottom:36px; max-width:400px; margin-left:auto; margin-right:auto;">
        Один раз оплатив — назавжди отримав систему. Плюс всі бонуси та AI-асистент.
      </p>
      <a href="#" class="btn btn-red btn-xl" style="font-size:1rem; padding:26px 72px;">
        Приєднатись до The Cash
        <svg class="btn-arrow" viewBox="0 0 20 20" fill="none">
          <path d="M4 10h12M11 5l5 5-5 5" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </a>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ============================================
     FAQ
     ============================================ -->
<section id="faq">
  <div class="container" style="padding-top:120px; padding-bottom:120px;">
    <div class="section-header reveal">
      <div class="label" style="color:var(--gold);margin-bottom:16px;display:block;">Питання та відповіді</div>
      <h2 class="display-lg">Твої запитання<br><span class="gold">та мої відповіді</span></h2>
    </div>

    <div class="faq-list reveal">
      <div class="faq-item">
        <button class="faq-question">
          Чи підійде мій метод, якщо в мене немає аудиторії?
          <div class="faq-icon">+</div>
        </button>
        <div class="faq-answer">
          <div class="faq-answer-inner">
            Так. Метод розроблений саме для тих, хто починає з нуля або має невелику аудиторію. Ти навчишся залучати правильних людей — тих, хто готовий платити.
          </div>
        </div>
      </div>
      <div class="faq-item">
        <button class="faq-question">
          Чи підійде мій метод, якщо в мене мало досвіду монетизації блогу?
          <div class="faq-icon">+</div>
        </button>
        <div class="faq-answer">
          <div class="faq-answer-inner">
            Абсолютно. Метод покриває все від основ до просунутих стратегій. Ти отримаєш покроковий план без пропущених кроків.
          </div>
        </div>
      </div>
      <div class="faq-item">
        <button class="faq-question">
          Що робити, якщо я не знаю, що продавати?
          <div class="faq-icon">+</div>
        </button>
        <div class="faq-answer">
          <div class="faq-answer-inner">
            Один з перших кроків методу — визначення твого продукту. Ти точно знайдеш, що продавати своїй аудиторії, виходячи з твоїх знань та навичок.
          </div>
        </div>
      </div>
      <div class="faq-item">
        <button class="faq-question">
          Куди мені звертатись, якщо в мене є питання?
          <div class="faq-icon">+</div>
        </button>
        <div class="faq-answer">
          <div class="faq-answer-inner">
            Після покупки ти отримаєш доступ до закритого чату учасників, де можеш ставити питання особисто мені та іншим членам спільноти. Ти не будеш сам.
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============================================
     FINAL CTA
     ============================================ -->
<section id="cta">
  <div class="cta-ghost-text">CASH</div>
  <div class="cta-content reveal">
    <div class="badge badge-gold" style="margin-bottom:24px;">Метод, який перетворює контент на прибуток</div>
    <h2 class="display-lg">Чого ти<br>ще <span class="gold">чекаєш?</span></h2>
    <p class="body-lg">Кожен день без системи — це день без доходу.<br>Зміни це прямо зараз.</p>
    <a href="#" class="btn btn-gold btn-xl" style="margin-top:8px;">
      Отримати метод зараз
      <svg class="btn-arrow" viewBox="0 0 20 20" fill="none">
        <path d="M4 10h12M11 5l5 5-5 5" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </a>
  </div>
</section>

<!-- ============================================
     FOOTER
     ============================================ -->
<footer>
  <div class="footer-inner">
    <div class="nav-logo" style="font-size:1rem;">THE <span style="color:var(--gold);">CASH</span> МЕТОД</div>
    <div class="footer-copy">© 2025 The Cash Method. Всі права захищено.</div>
    <div class="footer-copy">thecash.com.ua</div>
  </div>
</footer>

<!-- ============================================
     JAVASCRIPT
     ============================================ -->
<script>
// ---- Navbar scroll effect ----
const nav = document.getElementById('mainNav');
window.addEventListener('scroll', () => {
  nav.classList.toggle('scrolled', window.scrollY > 50);
});

// ---- Scroll reveal ----
const reveals = document.querySelectorAll('.reveal');
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');
    }
  });
}, { threshold: 0.1, rootMargin: '0px 0px -60px 0px' });

reveals.forEach(el => observer.observe(el));

// ---- FAQ accordion ----
document.querySelectorAll('.faq-question').forEach(btn => {
  btn.addEventListener('click', () => {
    const item = btn.closest('.faq-item');
    const answer = item.querySelector('.faq-answer');
    const isOpen = item.classList.contains('open');

    // Close all
    document.querySelectorAll('.faq-item.open').forEach(openItem => {
      openItem.classList.remove('open');
      openItem.querySelector('.faq-answer').style.maxHeight = '0';
    });

    // Open clicked
    if (!isOpen) {
      item.classList.add('open');
      answer.style.maxHeight = answer.scrollHeight + 'px';
    }
  });
});

// ---- Smooth number counter for stats ----
function animateCounter(el, target, suffix = '') {
  let start = 0;
  const duration = 1800;
  const step = (timestamp) => {
    if (!start) start = timestamp;
    const progress = Math.min((timestamp - start) / duration, 1);
    const eased = 1 - Math.pow(1 - progress, 3);
    const current = Math.floor(eased * target);
    el.textContent = current + suffix;
    if (progress < 1) requestAnimationFrame(step);
  };
  requestAnimationFrame(step);
}

const statsObserver = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      const statNums = e.target.querySelectorAll('.hero-stat-num');
      statsObserver.unobserve(e.target);
      // Just trigger animation class
    }
  });
}, { threshold: 0.5 });

const statsSection = document.querySelector('.hero-stats');
if (statsSection) statsObserver.observe(statsSection);

// ---- Ripple effect on buttons ----
document.querySelectorAll('.btn').forEach(btn => {
  btn.addEventListener('click', function(e) {
    const rect = btn.getBoundingClientRect();
    const x = e.clientX - rect.left;
    const y = e.clientY - rect.top;
    const ripple = document.createElement('span');
    ripple.style.cssText = `
      position:absolute; border-radius:50%;
      background:rgba(255,255,255,0.25);
      width:2px; height:2px;
      left:${x}px; top:${y}px;
      transform:translate(-50%,-50%) scale(0);
      animation: rippleAnim 0.6s ease-out forwards;
      pointer-events:none;
    `;
    btn.appendChild(ripple);
    setTimeout(() => ripple.remove(), 700);
  });
});

// Add ripple keyframes
const style = document.createElement('style');
style.textContent = `
  @keyframes rippleAnim {
    to { transform: translate(-50%,-50%) scale(200); opacity:0; }
  }
`;
document.head.appendChild(style);
</script>
</body>
</html>
