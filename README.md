<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Yalemzer Abraham — Learning &amp; Development</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,400;0,9..144,500;0,9..144,600;0,9..144,700;1,9..144,500&family=Inter:wght@400;500;600;700;800&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#1B2436;
    --ink-soft:#3A4358;
    --forest:#2B3A2F;
    --paper:#EFEAE0;
    --paper-2:#E6E0D2;
    --card:#F8F5EE;
    --amber:#D6A24A;
    --amber-deep:#B9812F;
    --rust:#A8452B;
    --cream:#F6F2E8;
    --line: rgba(27,36,54,0.14);
    --line-soft: rgba(27,36,54,0.08);
    --shadow: 0 18px 40px -22px rgba(27,36,54,0.35);
    --radius: 2px;
  }

  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  @media (prefers-reduced-motion: reduce){
    html{scroll-behavior:auto;}
    *{animation-duration:0.01ms !important; animation-iteration-count:1 !important; transition-duration:0.01ms !important; scroll-behavior:auto !important;}
  }

  body{
    margin:0;
    background:var(--paper);
    color:var(--ink);
    font-family:'Inter',sans-serif;
    font-size:16px;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }

  a{color:inherit;}
  ::selection{background:var(--amber); color:var(--ink);}

  .mono{
    font-family:'IBM Plex Mono',monospace;
    letter-spacing:0.06em;
  }

  .eyebrow{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.72rem;
    letter-spacing:0.18em;
    text-transform:uppercase;
    color:var(--amber-deep);
    display:flex;
    align-items:center;
    gap:0.6em;
    margin-bottom:1.1rem;
  }
  .eyebrow::before{
    content:"";
    width:28px;
    height:1px;
    background:var(--amber-deep);
    display:inline-block;
  }

  h1,h2,h3{
    font-family:'Fraunces',serif;
    margin:0;
    font-weight:600;
    letter-spacing:-0.01em;
  }

  /* ---------- Focus ---------- */
  a:focus-visible, button:focus-visible{
    outline:2px solid var(--amber-deep);
    outline-offset:3px;
  }

  /* ---------- NAV ---------- */
  header.nav{
    position:fixed;
    top:0; left:0; right:0;
    z-index:100;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:1.1rem clamp(1.25rem,4vw,3rem);
    background:transparent;
    transition:background 0.35s ease, box-shadow 0.35s ease, padding 0.35s ease;
  }
  header.nav.scrolled{
    background:rgba(27,36,54,0.94);
    backdrop-filter:blur(6px);
    box-shadow:0 6px 24px -12px rgba(0,0,0,0.4);
    padding:0.75rem clamp(1.25rem,4vw,3rem);
  }
  .nav-mark{
    display:flex;
    align-items:center;
    gap:0.6rem;
    text-decoration:none;
  }
  .nav-mark .box{
    width:34px; height:34px;
    background:var(--amber);
    color:var(--ink);
    display:flex; align-items:center; justify-content:center;
    font-family:'Fraunces',serif;
    font-weight:700;
    font-size:1.05rem;
    flex-shrink:0;
  }
  .nav-mark .label{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.72rem;
    letter-spacing:0.1em;
    color:var(--cream);
    line-height:1.3;
  }
  .nav-mark .label span{display:block; opacity:0.62; font-size:0.66rem;}

  nav.links{
    display:flex;
    gap:clamp(0.9rem,2vw,1.8rem);
    list-style:none;
    margin:0; padding:0;
  }
  nav.links a{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.72rem;
    letter-spacing:0.09em;
    text-transform:uppercase;
    color:var(--cream);
    text-decoration:none;
    opacity:0.75;
    transition:opacity 0.2s ease;
    position:relative;
  }
  nav.links a:hover{opacity:1;}
  @media (max-width:760px){
    nav.links{display:none;}
  }

  /* ---------- HERO ---------- */
  .hero{
    position:relative;
    min-height:100vh;
    background:
      radial-gradient(ellipse at 78% 12%, rgba(214,162,74,0.14), transparent 45%),
      var(--ink);
    color:var(--cream);
    overflow:hidden;
    display:flex;
    flex-direction:column;
    justify-content:center;
    padding:clamp(6rem,10vw,3rem) clamp(1.25rem,4vw,3rem) 0;
  }
  .hero::before{
    content:"";
    position:absolute; inset:0;
    background-image:
      repeating-linear-gradient(0deg, rgba(246,242,232,0.035) 0, rgba(246,242,232,0.035) 1px, transparent 1px, transparent 64px),
      repeating-linear-gradient(90deg, rgba(246,242,232,0.035) 0, rgba(246,242,232,0.035) 1px, transparent 1px, transparent 64px);
    pointer-events:none;
  }

  .hero-inner{
    position:relative;
    z-index:2;
    max-width:1280px;
    margin:0 auto;
    width:100%;
    display:grid;
    grid-template-columns:1.35fr 0.85fr;
    gap:clamp(2rem,5vw,4rem);
    align-items:center;
    padding-top:4.5rem;
    padding-bottom:3.5rem;
  }
  @media (max-width:860px){
    .hero-inner{grid-template-columns:1fr; text-align:left;}
  }

  .hero-eyebrow{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.74rem;
    letter-spacing:0.2em;
    text-transform:uppercase;
    color:var(--amber);
    margin-bottom:1.4rem;
  }

  .hero h1{
    font-size:clamp(2.6rem,6.4vw,5.2rem);
    line-height:0.98;
    color:var(--cream);
    font-weight:600;
  }

  .hero .role{
    font-family:'Fraunces',serif;
    font-style:italic;
    font-weight:500;
    font-size:clamp(1.05rem,2vw,1.45rem);
    color:var(--amber);
    margin-top:1.1rem;
    line-height:1.4;
  }

  .hero p.lead{
    max-width:44ch;
    margin-top:1.4rem;
    color:rgba(246,242,232,0.78);
    font-size:1.02rem;
  }

  .hero-photo-wrap{
    position:relative;
    justify-self:center;
    display:flex;
    flex-direction:column;
    align-items:center;
    gap:1rem;
  }
  .photo-frame{
    position:relative;
    width:min(280px, 62vw);
    aspect-ratio:1/1;
  }
  .photo-ring{
    position:absolute;
    inset:-14px;
    border:1.5px solid rgba(214,162,74,0.55);
    border-radius:50%;
  }
  .photo-frame img{
    width:100%; height:100%;
    object-fit:cover;
    border-radius:50%;
    display:block;
    box-shadow:0 24px 48px -18px rgba(0,0,0,0.55);
    background:var(--cream);
  }
  .badge-complete{
    position:absolute;
    bottom:2%;
    right:2%;
    width:52px; height:52px;
    background:var(--amber);
    color:var(--ink);
    border-radius:50%;
    display:flex;
    align-items:center;
    justify-content:center;
    border:3px solid var(--ink);
    font-size:1.3rem;
    font-weight:700;
    box-shadow:0 6px 16px -4px rgba(0,0,0,0.5);
  }
  .photo-caption{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.68rem;
    letter-spacing:0.1em;
    text-transform:uppercase;
    color:rgba(246,242,232,0.55);
    text-align:center;
  }

  .hero-stamp{
    position:absolute;
    top:clamp(5.2rem,9vw,6.5rem);
    right:clamp(1.25rem,4vw,3rem);
    z-index:3;
    width:98px; height:98px;
    border:1px solid rgba(214,162,74,0.55);
    border-radius:50%;
    display:none;
    align-items:center;
    justify-content:center;
    text-align:center;
    transform:rotate(-9deg);
    padding:0.6rem;
  }
  .hero-stamp span{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.6rem;
    letter-spacing:0.09em;
    color:var(--amber);
    text-transform:uppercase;
    line-height:1.35;
  }
  @media (min-width:1040px){
    .hero-stamp{display:flex;}
  }

  /* contact strip in hero */
  .hero-strip{
    position:relative;
    z-index:2;
    border-top:1px solid rgba(246,242,232,0.16);
    max-width:1280px;
    margin:0 auto;
    width:100%;
    padding:1.1rem clamp(0.25rem,0,0);
    display:flex;
    flex-wrap:wrap;
    gap:1.6rem 2.4rem;
  }
  .hero-strip a{
    display:flex;
    align-items:center;
    gap:0.55rem;
    text-decoration:none;
    color:rgba(246,242,232,0.85);
    font-family:'IBM Plex Mono',monospace;
    font-size:0.78rem;
    letter-spacing:0.03em;
    transition:color 0.2s ease;
  }
  .hero-strip a:hover{color:var(--amber);}
  .hero-strip svg{flex-shrink:0; opacity:0.85;}

  .scroll-cue{
    position:absolute;
    bottom:1.1rem; left:50%;
    transform:translateX(-50%);
    z-index:2;
    display:none;
  }

  /* ---------- SECTION SHARED ---------- */
  .section{
    padding:clamp(4rem,9vw,6.5rem) clamp(1.25rem,4vw,3rem);
  }
  .section-inner{
    max-width:1180px;
    margin:0 auto;
  }
  .section-head{
    max-width:640px;
    margin-bottom:clamp(2.2rem,5vw,3.2rem);
  }
  .section-head h2{
    font-size:clamp(1.7rem,3.4vw,2.5rem);
    color:var(--ink);
  }

  .reveal{
    opacity:0;
    transform:translateY(22px);
    transition:opacity 0.7s cubic-bezier(.2,.7,.3,1), transform 0.7s cubic-bezier(.2,.7,.3,1);
  }
  .reveal.is-visible{
    opacity:1;
    transform:translateY(0);
  }

  /* ---------- PROFILE / COURSE DESCRIPTION ---------- */
  .desc-card{
    background:var(--card);
    border:1px solid var(--line);
    box-shadow:var(--shadow);
    padding:clamp(2rem,4vw,3rem);
    position:relative;
    border-left:4px solid var(--amber);
  }
  .desc-card p{
    font-size:clamp(1.02rem,1.5vw,1.2rem);
    color:var(--ink-soft);
    max-width:74ch;
    margin:0;
  }
  .desc-card p::first-letter{
    font-family:'Fraunces',serif;
    font-size:3.4rem;
    font-weight:600;
    float:left;
    line-height:0.78;
    padding-right:0.12em;
    padding-top:0.05em;
    color:var(--ink);
  }

  .stat-row{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:1px;
    margin-top:2.4rem;
    background:var(--line);
    border:1px solid var(--line);
  }
  @media (max-width:700px){
    .stat-row{grid-template-columns:repeat(2,1fr);}
  }
  .stat{
    background:var(--card);
    padding:1.4rem 1.2rem;
  }
  .stat .num{
    font-family:'Fraunces',serif;
    font-size:clamp(1.7rem,3vw,2.3rem);
    font-weight:600;
    color:var(--rust);
    line-height:1;
  }
  .stat .label{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.66rem;
    letter-spacing:0.08em;
    text-transform:uppercase;
    color:var(--ink-soft);
    margin-top:0.5rem;
    display:block;
  }

  /* ---------- MODULES ---------- */
  .section-modules{
    background:var(--forest);
    color:var(--cream);
  }
  .section-modules .eyebrow{color:var(--amber);}
  .section-modules .eyebrow::before{background:var(--amber);}
  .section-modules .section-head h2{color:var(--cream);}
  .section-modules .section-head p{color:rgba(246,242,232,0.7);}

  .module-row{
    display:grid;
    grid-template-columns:36px 1fr;
    gap:0 1.6rem;
    position:relative;
  }
  @media (max-width:640px){
    .module-row{grid-template-columns:22px 1fr;}
  }

  .rail-col{
    position:relative;
    display:flex;
    flex-direction:column;
    align-items:center;
  }
  .rail-track{
    position:absolute;
    top:30px; bottom:0;
    width:1px;
    background:rgba(246,242,232,0.18);
    left:50%;
    transform:translateX(-50%);
    overflow:hidden;
  }
  .module-row:last-child .rail-track{display:none;}
  .rail-fill{
    position:absolute;
    top:0; left:0; right:0;
    height:0%;
    background:var(--amber);
    transition:height 0.9s cubic-bezier(.2,.7,.3,1);
  }
  .rail-node{
    position:relative;
    z-index:2;
    width:30px; height:30px;
    border-radius:50%;
    border:1.5px solid rgba(246,242,232,0.35);
    background:var(--forest);
    display:flex;
    align-items:center;
    justify-content:center;
    font-family:'IBM Plex Mono',monospace;
    font-size:0.72rem;
    color:rgba(246,242,232,0.6);
    transition:all 0.5s ease;
    flex-shrink:0;
  }
  @media (max-width:640px){
    .rail-node{width:20px;height:20px;font-size:0;}
  }
  .rail-node.is-visible{
    border-color:var(--amber);
    background:var(--amber);
    color:var(--ink);
  }

  .module{
    padding-bottom:clamp(2.6rem,5vw,3.6rem);
  }
  .module-row:last-child .module{padding-bottom:0.5rem;}

  .module-card{
    background:rgba(246,242,232,0.05);
    border:1px solid rgba(246,242,232,0.14);
    padding:clamp(1.6rem,3vw,2.4rem);
  }
  .module-top{
    display:flex;
    flex-wrap:wrap;
    justify-content:space-between;
    align-items:flex-start;
    gap:1rem;
    margin-bottom:1rem;
  }
  .module-tag{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.68rem;
    letter-spacing:0.12em;
    color:var(--amber);
    text-transform:uppercase;
  }
  .module-card h3{
    font-size:clamp(1.25rem,2.2vw,1.65rem);
    color:var(--cream);
    margin-top:0.35rem;
  }
  .module-role{
    font-family:'Fraunces',serif;
    font-style:italic;
    font-size:1.02rem;
    color:rgba(246,242,232,0.78);
    margin-top:0.2rem;
  }
  .module-dates{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.75rem;
    color:rgba(246,242,232,0.6);
    text-align:right;
    white-space:nowrap;
  }
  .module-stamp{
    display:inline-flex;
    align-items:center;
    gap:0.4rem;
    margin-top:0.5rem;
    font-family:'IBM Plex Mono',monospace;
    font-size:0.66rem;
    letter-spacing:0.08em;
    text-transform:uppercase;
    color:var(--amber);
    border:1px solid rgba(214,162,74,0.4);
    padding:0.28rem 0.6rem;
  }

  .duration-bar-wrap{
    margin:1.3rem 0 1.4rem;
  }
  .duration-bar-track{
    height:6px;
    background:rgba(246,242,232,0.12);
    width:100%;
    position:relative;
    overflow:hidden;
  }
  .duration-bar-fill{
    height:100%;
    width:0%;
    background:linear-gradient(90deg, var(--amber-deep), var(--amber));
    transition:width 1s cubic-bezier(.2,.7,.3,1);
  }
  .duration-label{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.68rem;
    color:rgba(246,242,232,0.55);
    margin-top:0.45rem;
    letter-spacing:0.05em;
  }

  .outcomes-label{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.66rem;
    letter-spacing:0.12em;
    text-transform:uppercase;
    color:rgba(246,242,232,0.45);
    margin-bottom:0.7rem;
  }
  .module-card ul{
    margin:0;
    padding:0;
    list-style:none;
  }
  .module-card li{
    position:relative;
    padding-left:1.3rem;
    margin-bottom:0.6rem;
    color:rgba(246,242,232,0.85);
    font-size:0.96rem;
  }
  .module-card li:last-child{margin-bottom:0;}
  .module-card li::before{
    content:"—";
    position:absolute;
    left:0;
    color:var(--amber);
  }

  /* ---------- COMPETENCIES ---------- */
  .comp-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:1.4rem;
  }
  @media (max-width:860px){
    .comp-grid{grid-template-columns:1fr;}
  }
  .comp-card{
    background:var(--card);
    border:1px solid var(--line);
    padding:1.8rem 1.7rem;
  }
  .comp-card .comp-num{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.68rem;
    color:var(--rust);
    letter-spacing:0.1em;
  }
  .comp-card h3{
    font-size:1.25rem;
    margin-top:0.5rem;
    margin-bottom:1.2rem;
    color:var(--ink);
  }
  .comp-card ul{list-style:none; margin:0; padding:0;}
  .comp-card li{
    display:flex;
    align-items:center;
    gap:0.6rem;
    padding:0.55rem 0;
    border-top:1px solid var(--line-soft);
    font-size:0.94rem;
    color:var(--ink-soft);
  }
  .comp-card li:first-child{border-top:none;}
  .comp-card li .check{
    width:16px; height:16px;
    border-radius:50%;
    background:var(--amber);
    color:var(--ink);
    flex-shrink:0;
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:0.6rem;
    font-weight:700;
  }

  /* ---------- CREDENTIALS ---------- */
  .cred-grid{
    display:grid;
    grid-template-columns:1.1fr 0.9fr;
    gap:2rem;
    align-items:start;
  }
  @media (max-width:900px){
    .cred-grid{grid-template-columns:1fr;}
  }
  .transcript{
    background:var(--card);
    border:1px solid var(--line);
  }
  .transcript-head{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:1.1rem 1.5rem;
    border-bottom:1px solid var(--line);
    font-family:'IBM Plex Mono',monospace;
    font-size:0.68rem;
    letter-spacing:0.1em;
    text-transform:uppercase;
    color:var(--ink-soft);
  }
  .transcript-row{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:1rem;
    padding:1.05rem 1.5rem;
    border-bottom:1px solid var(--line-soft);
  }
  .transcript-row:last-child{border-bottom:none;}
  .transcript-row .t-name{
    font-family:'Fraunces',serif;
    font-size:1.02rem;
    color:var(--ink);
  }
  .transcript-row .t-status{
    display:flex;
    align-items:center;
    gap:0.4rem;
    font-family:'IBM Plex Mono',monospace;
    font-size:0.66rem;
    letter-spacing:0.06em;
    text-transform:uppercase;
    color:var(--amber-deep);
    white-space:nowrap;
  }
  .t-status .dot{
    width:7px;height:7px;border-radius:50%;background:var(--amber-deep);
  }

  .diploma{
    background:var(--ink);
    color:var(--cream);
    padding:clamp(1.8rem,3vw,2.6rem);
    position:relative;
    border:1px solid rgba(214,162,74,0.3);
  }
  .diploma::before{
    content:"";
    position:absolute;
    inset:10px;
    border:1px solid rgba(214,162,74,0.25);
    pointer-events:none;
  }
  .diploma .d-label{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.66rem;
    letter-spacing:0.14em;
    text-transform:uppercase;
    color:var(--amber);
  }
  .diploma h3{
    font-size:clamp(1.3rem,2.4vw,1.6rem);
    margin-top:0.8rem;
    line-height:1.25;
    color:var(--cream);
  }
  .diploma .school{
    font-family:'Fraunces',serif;
    font-style:italic;
    color:rgba(246,242,232,0.8);
    margin-top:0.7rem;
    font-size:1rem;
  }
  .diploma .meta-row{
    display:flex;
    justify-content:space-between;
    margin-top:1.6rem;
    padding-top:1.2rem;
    border-top:1px solid rgba(246,242,232,0.18);
    font-family:'IBM Plex Mono',monospace;
    font-size:0.72rem;
    color:rgba(246,242,232,0.65);
  }
  .diploma .meta-row strong{color:var(--amber); font-weight:600;}

  /* ---------- CONTACT ---------- */
  .section-contact{
    background:var(--paper-2);
  }
  .contact-card{
    background:var(--ink);
    color:var(--cream);
    padding:clamp(2.2rem,5vw,3.6rem);
    display:grid;
    grid-template-columns:1.2fr 1fr;
    gap:2.5rem;
    position:relative;
    overflow:hidden;
  }
  .contact-card::after{
    content:"";
    position:absolute;
    right:-60px; top:-60px;
    width:220px; height:220px;
    border-radius:50%;
    border:1px solid rgba(214,162,74,0.2);
  }
  @media (max-width:800px){
    .contact-card{grid-template-columns:1fr;}
  }
  .contact-card h2{
    color:var(--cream);
    font-size:clamp(1.6rem,3vw,2.3rem);
    max-width:16ch;
  }
  .contact-card p{
    color:rgba(246,242,232,0.72);
    max-width:42ch;
    margin-top:1rem;
  }
  .contact-list{
    list-style:none;
    margin:0; padding:0;
    display:flex;
    flex-direction:column;
    gap:1.1rem;
    position:relative;
    z-index:1;
  }
  .contact-list li a{
    display:flex;
    align-items:center;
    gap:0.9rem;
    text-decoration:none;
    color:var(--cream);
    font-family:'IBM Plex Mono',monospace;
    font-size:0.92rem;
    padding-bottom:1.05rem;
    border-bottom:1px solid rgba(246,242,232,0.16);
    transition:color 0.2s ease, padding-left 0.2s ease;
  }
  .contact-list li a:hover{color:var(--amber); padding-left:0.3rem;}
  .contact-list li:last-child a{border-bottom:none;}
  .contact-list .ic{
    width:34px; height:34px;
    border:1px solid rgba(214,162,74,0.4);
    border-radius:50%;
    display:flex; align-items:center; justify-content:center;
    flex-shrink:0;
  }
  .ref-note{
    margin-top:0.4rem;
    font-family:'IBM Plex Mono',monospace;
    font-size:0.7rem;
    letter-spacing:0.05em;
    color:rgba(246,242,232,0.45);
  }

  /* ---------- FOOTER ---------- */
  footer{
    padding:2.2rem clamp(1.25rem,4vw,3rem) 2.6rem;
    display:flex;
    flex-wrap:wrap;
    gap:0.8rem 2rem;
    justify-content:space-between;
    align-items:center;
    font-family:'IBM Plex Mono',monospace;
    font-size:0.7rem;
    letter-spacing:0.04em;
    color:var(--ink-soft);
    background:var(--paper-2);
    border-top:1px solid var(--line);
  }
</style>
</head>
<body>

<header class="nav" id="siteNav">
  <a href="#top" class="nav-mark">
    <span class="box">Y</span>
    <span class="label">YALEMZER ABRAHAM<span>L&amp;D · TRAINING · ETHIOPIA</span></span>
  </a>
  <ul class="links">
    <li><a href="#profile">Overview</a></li>
    <li><a href="#modules">Modules</a></li>
    <li><a href="#competencies">Competencies</a></li>
    <li><a href="#credentials">Credentials</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</header>

<section class="hero" id="top">
  <div class="hero-stamp">
    <span>L&amp;D<br>PRACTITIONER<br>EST. 2019</span>
  </div>

  <div class="hero-inner">
    <div>
      <div class="hero-eyebrow">Professional Development Program &nbsp;·&nbsp; L&amp;D Track</div>
      <h1>Yalemzer<br>Abraham</h1>
      <div class="role">Training Manager — Learning &amp; Development Specialist — Training &amp; Dvt Officer</div>
      <p class="lead">Five-plus years building the systems that turn onboarding into capability: needs assessments, LMS platforms, and leadership pipelines designed for organizations across Ethiopia.</p>
    </div>

    <div class="hero-photo-wrap">
      <div class="photo-frame">
        <div class="photo-ring"></div>
        <img src="data:image/png;base64,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
A professional portfolio highlighting my work in Learning &amp; Development, including training programs, learning solutions, facilitation, projects, and continuous professional development.
