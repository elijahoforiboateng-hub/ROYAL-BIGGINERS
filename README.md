<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Royal Beginners School | Premier Early Childhood Education in Accra</title>
    <meta name="description" content="Royal Beginners School — Accra's premier early childhood education institution. Playgroup, Nursery, and Kindergarten programmes designed to shape extraordinary futures.">

    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400&family=DM+Sans:wght@300;400;500;600&family=Cinzel:wght@400;600&display=swap" rel="stylesheet">
    <!-- Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css">

    <style>
    /* ============================================================
       DESIGN TOKENS
    ============================================================ */
    :root {
        --navy:   #0a1628;
        --navy2:  #112240;
        --gold:   #c9922a;
        --gold2:  #e8b84b;
        --cream:  #faf7f2;
        --sand:   #f0e8d8;
        --red:    #b5202e;
        --white:  #ffffff;
        --text:   #1e2d40;
        --muted:  #667085;
        --border: rgba(201,146,42,0.25);
        --radius: 4px;
        --shadow: 0 8px 40px rgba(10,22,40,0.12);
        --shadow-lg: 0 24px 80px rgba(10,22,40,0.18);
        --transition: 0.45s cubic-bezier(0.23, 1, 0.32, 1);
    }

    /* ============================================================
       RESET & BASE
    ============================================================ */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; font-size: 16px; }
    body {
        font-family: 'DM Sans', sans-serif;
        background: var(--cream);
        color: var(--text);
        overflow-x: hidden;
    }
    h1, h2, h3, h4 { font-family: 'Cormorant Garamond', serif; line-height: 1.15; }
    img { max-width: 100%; display: block; }
    a { text-decoration: none; color: inherit; }
    ul { list-style: none; }

    /* ============================================================
       SCROLL PROGRESS BAR
    ============================================================ */
    #progress-bar {
        position: fixed; top: 0; left: 0; height: 3px; width: 0%;
        background: linear-gradient(90deg, var(--gold), var(--gold2));
        z-index: 9999;
        transition: width 0.1s linear;
    }

    /* ============================================================
       NAVIGATION
    ============================================================ */
    .navbar {
        position: fixed; top: 3px; left: 0; right: 0; z-index: 1000;
        padding: 0 5vw;
        height: 72px;
        display: flex; align-items: center; justify-content: space-between;
        transition: background var(--transition), box-shadow var(--transition);
    }
    .navbar.scrolled {
        background: rgba(10,22,40,0.97);
        backdrop-filter: blur(16px);
        box-shadow: 0 4px 32px rgba(0,0,0,0.25);
    }
    .nav-logo {
        font-family: 'Cinzel', serif;
        font-size: 1.15rem;
        color: var(--white);
        display: flex; align-items: center; gap: 10px;
        letter-spacing: 0.08em;
    }
    .nav-logo .crown {
        width: 36px; height: 36px;
        background: linear-gradient(135deg, var(--gold), var(--gold2));
        border-radius: 50%;
        display: flex; align-items: center; justify-content: center;
        font-size: 0.9rem;
    }
    .nav-links { display: flex; align-items: center; gap: 36px; }
    .nav-links a {
        color: rgba(255,255,255,0.78);
        font-size: 0.82rem;
        font-weight: 500;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        position: relative;
        transition: color 0.3s;
    }
    .nav-links a::after {
        content: '';
        position: absolute; bottom: -4px; left: 0; right: 0;
        height: 1px;
        background: var(--gold);
        transform: scaleX(0);
        transition: transform 0.3s;
    }
    .nav-links a:hover { color: var(--gold2); }
    .nav-links a:hover::after { transform: scaleX(1); }
    .nav-cta {
        background: var(--red);
        color: var(--white) !important;
        padding: 10px 22px;
        border-radius: 2px;
        font-size: 0.78rem !important;
        letter-spacing: 0.12em;
        font-weight: 600 !important;
        transition: background 0.3s, transform 0.2s !important;
    }
    .nav-cta:hover { background: #8f1520 !important; transform: translateY(-1px); }
    .nav-cta::after { display: none !important; }

    .hamburger {
        display: none;
        flex-direction: column; gap: 5px; cursor: pointer; padding: 6px;
    }
    .hamburger span {
        display: block; width: 24px; height: 2px;
        background: var(--white);
        transition: all 0.3s;
    }

    /* ============================================================
       HERO
    ============================================================ */
    .hero {
        min-height: 100vh;
        background: var(--navy);
        position: relative;
        display: flex; align-items: center;
        overflow: hidden;
    }
    .hero-bg {
        position: absolute; inset: 0;
        background: url('https://images.unsplash.com/photo-1503676260728-1c00da094a0b?w=1800&q=80') center/cover no-repeat;
        opacity: 0.22;
        transform: scale(1.05);
        animation: heroZoom 18s ease-in-out infinite alternate;
    }
    @keyframes heroZoom { from { transform: scale(1.05); } to { transform: scale(1.12); } }

    .hero-overlay {
        position: absolute; inset: 0;
        background: linear-gradient(135deg,
            rgba(10,22,40,0.92) 0%,
            rgba(10,22,40,0.65) 60%,
            rgba(181,32,46,0.15) 100%);
    }
    .hero-content {
        position: relative; z-index: 2;
        max-width: 1200px; margin: 0 auto;
        padding: 0 5vw;
        display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: center;
    }
    .hero-text { padding-top: 80px; }
    .hero-eyebrow {
        display: inline-flex; align-items: center; gap: 12px;
        color: var(--gold);
        font-size: 0.75rem;
        letter-spacing: 0.22em;
        text-transform: uppercase;
        font-weight: 600;
        margin-bottom: 24px;
    }
    .hero-eyebrow::before, .hero-eyebrow::after {
        content: ''; display: block; width: 32px; height: 1px; background: var(--gold);
    }
    .hero-title {
        font-size: clamp(3rem, 5.5vw, 5rem);
        color: var(--white);
        line-height: 1.08;
        font-weight: 300;
        margin-bottom: 28px;
    }
    .hero-title em { font-style: italic; color: var(--gold2); }
    .hero-subtitle {
        font-family: 'DM Sans', sans-serif;
        color: rgba(255,255,255,0.65);
        font-size: 1.05rem;
        line-height: 1.7;
        margin-bottom: 44px;
        font-weight: 300;
    }
    .hero-actions { display: flex; gap: 16px; flex-wrap: wrap; }
    .btn-primary-hero {
        background: linear-gradient(135deg, var(--red), #8f1520);
        color: var(--white);
        padding: 16px 36px;
        font-size: 0.82rem;
        font-weight: 600;
        letter-spacing: 0.12em;
        text-transform: uppercase;
        border-radius: 2px;
        transition: var(--transition);
        box-shadow: 0 8px 32px rgba(181,32,46,0.4);
    }
    .btn-primary-hero:hover {
        transform: translateY(-3px);
        box-shadow: 0 16px 48px rgba(181,32,46,0.5);
        color: var(--white);
    }
    .btn-outline-hero {
        border: 1px solid rgba(255,255,255,0.35);
        color: rgba(255,255,255,0.8);
        padding: 16px 36px;
        font-size: 0.82rem;
        font-weight: 500;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        border-radius: 2px;
        transition: var(--transition);
    }
    .btn-outline-hero:hover {
        border-color: var(--gold);
        color: var(--gold);
        background: rgba(201,146,42,0.08);
    }
    .hero-card {
        position: relative;
        background: rgba(255,255,255,0.06);
        border: 1px solid rgba(255,255,255,0.12);
        backdrop-filter: blur(12px);
        border-radius: 8px;
        padding: 36px;
        margin-top: 80px;
    }
    .hero-stats {
        display: grid; grid-template-columns: repeat(3, 1fr);
        gap: 24px;
    }
    .hero-stat { text-align: center; }
    .hero-stat .num {
        font-family: 'Cormorant Garamond', serif;
        font-size: 2.8rem;
        font-weight: 700;
        color: var(--gold2);
        line-height: 1;
        display: block;
    }
    .hero-stat .label {
        font-size: 0.72rem;
        color: rgba(255,255,255,0.5);
        letter-spacing: 0.1em;
        text-transform: uppercase;
        margin-top: 6px;
    }
    .hero-badge {
        position: absolute; top: -16px; left: 50%; transform: translateX(-50%);
        background: linear-gradient(135deg, var(--gold), var(--gold2));
        color: var(--navy);
        font-size: 0.68rem;
        font-weight: 700;
        letter-spacing: 0.18em;
        text-transform: uppercase;
        padding: 6px 20px;
        border-radius: 20px;
        white-space: nowrap;
    }
    .hero-scroll {
        position: absolute; bottom: 36px; left: 50%; transform: translateX(-50%);
        z-index: 2;
        display: flex; flex-direction: column; align-items: center; gap: 8px;
        color: rgba(255,255,255,0.4);
        font-size: 0.68rem;
        letter-spacing: 0.2em;
        text-transform: uppercase;
    }
    .hero-scroll .arrow {
        width: 1px; height: 40px;
        background: linear-gradient(to bottom, transparent, rgba(255,255,255,0.35));
        animation: scrollPulse 2s ease-in-out infinite;
    }
    @keyframes scrollPulse { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }

    /* ============================================================
       SECTION BASE
    ============================================================ */
    section { position: relative; }
    .section-pad { padding: 100px 5vw; }
    .container-narrow { max-width: 1100px; margin: 0 auto; }
    .container-wide { max-width: 1300px; margin: 0 auto; }

    .section-label {
        display: inline-flex; align-items: center; gap: 12px;
        color: var(--gold);
        font-size: 0.7rem;
        letter-spacing: 0.25em;
        text-transform: uppercase;
        font-weight: 600;
        margin-bottom: 16px;
    }
    .section-label::before {
        content: ''; display: block; width: 28px; height: 1px; background: var(--gold);
    }
    .section-title {
        font-size: clamp(2.2rem, 4vw, 3.4rem);
        color: var(--navy);
        font-weight: 300;
        line-height: 1.12;
        margin-bottom: 20px;
    }
    .section-title em { font-style: italic; color: var(--gold); }
    .section-desc {
        color: var(--muted);
        font-size: 1.05rem;
        line-height: 1.75;
        font-weight: 300;
        max-width: 560px;
    }
    .divider {
        width: 48px; height: 3px;
        background: linear-gradient(90deg, var(--gold), var(--gold2));
        margin: 20px 0 32px;
        border-radius: 2px;
    }

    /* ============================================================
       ABOUT
    ============================================================ */
    .about-section { background: var(--white); }
    .about-grid {
        display: grid; grid-template-columns: 1fr 1fr;
        gap: 80px; align-items: center;
    }
    .about-image-wrap { position: relative; }
    .about-img-main {
        width: 100%; aspect-ratio: 4/5;
        object-fit: cover;
        border-radius: 4px;
        box-shadow: var(--shadow-lg);
    }
    .about-img-accent {
        position: absolute;
        width: 48%; aspect-ratio: 1;
        object-fit: cover;
        border-radius: 4px;
        border: 6px solid var(--white);
        box-shadow: var(--shadow);
        bottom: -28px; right: -28px;
    }
    .about-badge-float {
        position: absolute; top: 32px; left: -24px;
        background: linear-gradient(135deg, var(--navy), var(--navy2));
        color: var(--white);
        padding: 20px 24px;
        border-radius: 4px;
        text-align: center;
        box-shadow: var(--shadow);
    }
    .about-badge-float .big { font-family: 'Cormorant Garamond', serif; font-size: 2.4rem; color: var(--gold2); line-height: 1; display: block; }
    .about-badge-float .small { font-size: 0.68rem; letter-spacing: 0.15em; text-transform: uppercase; color: rgba(255,255,255,0.6); margin-top: 4px; }

    .about-features { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; margin-top: 40px; }
    .feature-item {
        display: flex; gap: 14px; align-items: flex-start;
        padding: 20px;
        background: var(--cream);
        border-radius: 4px;
        border-left: 3px solid var(--gold);
        transition: var(--transition);
    }
    .feature-item:hover { transform: translateX(4px); background: var(--sand); }
    .feature-item .icon { color: var(--gold); font-size: 1.2rem; margin-top: 2px; flex-shrink: 0; }
    .feature-item h5 { font-family: 'DM Sans', sans-serif; font-size: 0.9rem; font-weight: 600; margin-bottom: 4px; }
    .feature-item p { font-size: 0.82rem; color: var(--muted); line-height: 1.5; }

    /* ============================================================
       PROGRAMS
    ============================================================ */
    .programs-section { background: var(--navy); overflow: hidden; }
    .programs-section .section-title { color: var(--white); }
    .programs-section .section-desc { color: rgba(255,255,255,0.55); }
    .programs-grid {
        display: grid; grid-template-columns: repeat(3, 1fr);
        gap: 2px;
        margin-top: 56px;
        border-radius: 4px; overflow: hidden;
        box-shadow: var(--shadow-lg);
    }
    .program-card {
        background: rgba(255,255,255,0.05);
        padding: 48px 36px;
        position: relative;
        overflow: hidden;
        transition: var(--transition);
        cursor: pointer;
    }
    .program-card::before {
        content: '';
        position: absolute; inset: 0;
        background: linear-gradient(135deg, rgba(201,146,42,0.12), transparent);
        opacity: 0;
        transition: opacity 0.4s;
    }
    .program-card:hover { background: rgba(255,255,255,0.09); }
    .program-card:hover::before { opacity: 1; }
    .program-card:hover .prog-icon { transform: scale(1.12) rotate(-5deg); }

    .prog-number {
        font-family: 'Cormorant Garamond', serif;
        font-size: 5rem; font-weight: 700;
        color: rgba(255,255,255,0.04);
        position: absolute; top: 16px; right: 20px;
        line-height: 1;
    }
    .prog-icon {
        width: 60px; height: 60px;
        background: linear-gradient(135deg, var(--gold), var(--gold2));
        border-radius: 50%;
        display: flex; align-items: center; justify-content: center;
        font-size: 1.4rem; color: var(--navy);
        margin-bottom: 24px;
        transition: transform 0.4s;
        flex-shrink: 0;
    }
    .prog-age {
        display: inline-block;
        background: rgba(201,146,42,0.18);
        color: var(--gold2);
        font-size: 0.68rem;
        letter-spacing: 0.15em;
        text-transform: uppercase;
        padding: 4px 12px;
        border-radius: 20px;
        margin-bottom: 14px;
    }
    .prog-title {
        font-size: 1.6rem;
        color: var(--white);
        margin-bottom: 14px;
        font-weight: 400;
    }
    .prog-desc {
        font-size: 0.88rem;
        color: rgba(255,255,255,0.5);
        line-height: 1.7;
        margin-bottom: 24px;
    }
    .prog-features { display: flex; flex-direction: column; gap: 8px; }
    .prog-features li {
        font-size: 0.8rem;
        color: rgba(255,255,255,0.45);
        display: flex; align-items: center; gap: 8px;
    }
    .prog-features li::before {
        content: ''; display: block; width: 16px; height: 1px; background: var(--gold); flex-shrink: 0;
    }

    /* ============================================================
       ADMISSIONS
    ============================================================ */
    .admissions-section { background: var(--cream); }
    .admissions-grid {
        display: grid; grid-template-columns: 1fr 1.5fr;
        gap: 60px; align-items: start;
    }
    .admission-info { position: sticky; top: 100px; }
    .timeline { margin-top: 40px; position: relative; }
    .timeline::before {
        content: ''; position: absolute; left: 20px; top: 0; bottom: 0;
        width: 1px; background: var(--border);
    }
    .timeline-item {
        display: flex; gap: 24px;
        margin-bottom: 36px;
        position: relative;
    }
    .timeline-dot {
        width: 40px; height: 40px; flex-shrink: 0;
        border-radius: 50%;
        background: var(--white);
        border: 2px solid var(--gold);
        display: flex; align-items: center; justify-content: center;
        font-size: 0.8rem;
        font-weight: 700;
        color: var(--gold);
        z-index: 1;
    }
    .timeline-text h5 {
        font-family: 'DM Sans', sans-serif;
        font-size: 0.9rem;
        font-weight: 600;
        margin-bottom: 4px;
    }
    .timeline-text p { font-size: 0.82rem; color: var(--muted); line-height: 1.5; }

    .form-card {
        background: var(--white);
        border-radius: 8px;
        box-shadow: var(--shadow-lg);
        overflow: hidden;
    }
    .form-header {
        background: linear-gradient(135deg, var(--navy), var(--navy2));
        padding: 36px 40px;
        position: relative; overflow: hidden;
    }
    .form-header::after {
        content: '';
        position: absolute; top: -40px; right: -40px;
        width: 160px; height: 160px;
        border-radius: 50%;
        background: rgba(201,146,42,0.12);
    }
    .form-header h3 {
        color: var(--white);
        font-size: 1.8rem;
        font-weight: 400;
        margin-bottom: 6px;
    }
    .form-header p { color: rgba(255,255,255,0.55); font-size: 0.88rem; }
    .form-body { padding: 40px; }

    .form-group { margin-bottom: 22px; }
    .form-label {
        display: block;
        font-size: 0.75rem;
        font-weight: 600;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        color: var(--navy);
        margin-bottom: 8px;
    }
    .form-control, .form-select {
        width: 100%;
        padding: 14px 16px;
        border: 1.5px solid #e5e7eb;
        border-radius: 4px;
        font-family: 'DM Sans', sans-serif;
        font-size: 0.95rem;
        color: var(--text);
        background: var(--cream);
        transition: border-color 0.3s, box-shadow 0.3s;
        outline: none;
        appearance: none;
    }
    .form-control:focus, .form-select:focus {
        border-color: var(--gold);
        box-shadow: 0 0 0 3px rgba(201,146,42,0.12);
        background: var(--white);
    }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
    .form-select-wrap { position: relative; }
    .form-select-wrap::after {
        content: '\f107';
        font-family: 'Font Awesome 6 Free'; font-weight: 900;
        position: absolute; right: 16px; top: 50%; transform: translateY(-50%);
        color: var(--muted); pointer-events: none;
    }
    .btn-submit {
        width: 100%; padding: 16px;
        background: linear-gradient(135deg, var(--red), #8f1520);
        color: var(--white);
        border: none; border-radius: 4px;
        font-family: 'DM Sans', sans-serif;
        font-size: 0.88rem;
        font-weight: 700;
        letter-spacing: 0.14em;
        text-transform: uppercase;
        cursor: pointer;
        transition: var(--transition);
        box-shadow: 0 8px 32px rgba(181,32,46,0.3);
        margin-top: 8px;
    }
    .btn-submit:hover {
        transform: translateY(-2px);
        box-shadow: 0 16px 48px rgba(181,32,46,0.45);
    }

    .alert-box {
        padding: 16px 20px;
        border-radius: 4px;
        font-size: 0.9rem;
        margin-bottom: 24px;
        display: flex; align-items: center; gap: 12px;
    }
    .alert-success { background: #ecfdf5; border-left: 4px solid #22c55e; color: #166534; }
    .alert-error { background: #fef2f2; border-left: 4px solid #ef4444; color: #991b1b; }

    /* ============================================================
       NEWS
    ============================================================ */
    .news-section { background: var(--white); }
    .news-grid {
        display: grid; grid-template-columns: repeat(3, 1fr);
        gap: 28px; margin-top: 56px;
    }
    .news-card {
        border-radius: 4px; overflow: hidden;
        box-shadow: var(--shadow);
        background: var(--cream);
        transition: var(--transition);
    }
    .news-card:hover { transform: translateY(-8px); box-shadow: var(--shadow-lg); }
    .news-card:hover .news-img { transform: scale(1.05); }
    .news-img-wrap { overflow: hidden; height: 220px; }
    .news-img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.6s ease; }
    .news-body { padding: 28px; }
    .news-cat {
        font-size: 0.68rem;
        letter-spacing: 0.18em;
        text-transform: uppercase;
        color: var(--gold);
        font-weight: 600;
        margin-bottom: 10px;
    }
    .news-title {
        font-size: 1.25rem;
        color: var(--navy);
        margin-bottom: 12px;
        line-height: 1.3;
    }
    .news-excerpt { font-size: 0.85rem; color: var(--muted); line-height: 1.65; margin-bottom: 20px; }
    .news-date {
        font-size: 0.72rem;
        color: var(--muted);
        display: flex; align-items: center; gap: 6px;
    }
    .news-placeholder {
        text-align: center; padding: 60px;
        color: var(--muted);
        grid-column: 1/-1;
    }
    .news-placeholder i { font-size: 3rem; color: var(--sand); margin-bottom: 16px; display: block; }

    /* ============================================================
       GALLERY
    ============================================================ */
    .gallery-section { background: var(--navy); }
    .gallery-section .section-title { color: var(--white); }
    .gallery-section .section-desc { color: rgba(255,255,255,0.5); }
    .gallery-grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-template-rows: auto auto;
        gap: 8px;
        margin-top: 48px;
        border-radius: 6px; overflow: hidden;
    }
    .gallery-item {
        overflow: hidden;
        cursor: pointer;
        position: relative;
    }
    .gallery-item:first-child {
        grid-column: span 2; grid-row: span 2;
    }
    .gallery-item img {
        width: 100%; height: 100%; object-fit: cover;
        min-height: 180px;
        transition: transform 0.6s ease;
    }
    .gallery-item:first-child img { min-height: 380px; }
    .gallery-item:hover img { transform: scale(1.08); }
    .gallery-overlay {
        position: absolute; inset: 0;
        background: linear-gradient(to top, rgba(10,22,40,0.7), transparent);
        opacity: 0;
        transition: opacity 0.4s;
        display: flex; align-items: flex-end; padding: 16px;
    }
    .gallery-item:hover .gallery-overlay { opacity: 1; }
    .gallery-overlay span {
        color: var(--white); font-size: 0.78rem;
        letter-spacing: 0.1em; text-transform: uppercase;
    }

    /* ============================================================
       CONTACT
    ============================================================ */
    .contact-section { background: var(--cream); }
    .contact-grid {
        display: grid; grid-template-columns: 1.2fr 1fr;
        gap: 60px;
    }
    .contact-info { padding-top: 20px; }
    .contact-detail {
        display: flex; gap: 18px; align-items: flex-start;
        padding: 24px 0;
        border-bottom: 1px solid var(--border);
    }
    .contact-detail:last-of-type { border-bottom: none; }
    .contact-icon {
        width: 44px; height: 44px; flex-shrink: 0;
        background: linear-gradient(135deg, var(--navy), var(--navy2));
        border-radius: 4px;
        display: flex; align-items: center; justify-content: center;
        color: var(--gold);
        font-size: 1rem;
    }
    .contact-detail h5 {
        font-family: 'DM Sans', sans-serif;
        font-size: 0.75rem;
        font-weight: 700;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        color: var(--muted);
        margin-bottom: 4px;
    }
    .contact-detail p { font-size: 0.95rem; color: var(--text); line-height: 1.55; }
    .contact-detail a { color: var(--text); transition: color 0.3s; }
    .contact-detail a:hover { color: var(--gold); }

    .map-wrap {
        border-radius: 4px; overflow: hidden;
        height: 220px; margin-top: 32px;
        box-shadow: var(--shadow);
    }
    .map-wrap iframe { width: 100%; height: 100%; border: none; }

    .social-links { display: flex; gap: 12px; margin-top: 32px; }
    .social-link {
        width: 40px; height: 40px;
        border: 1.5px solid var(--border);
        border-radius: 4px;
        display: flex; align-items: center; justify-content: center;
        color: var(--muted);
        font-size: 0.9rem;
        transition: var(--transition);
    }
    .social-link:hover {
        background: var(--navy);
        border-color: var(--navy);
        color: var(--gold);
        transform: translateY(-2px);
    }

    /* ============================================================
       FOOTER
    ============================================================ */
    footer {
        background: linear-gradient(135deg, #060f1e, var(--navy));
        color: rgba(255,255,255,0.5);
        padding: 72px 5vw 40px;
    }
    .footer-grid {
        display: grid; grid-template-columns: 2fr 1fr 1fr 1.5fr;
        gap: 48px;
        max-width: 1200px; margin: 0 auto;
        padding-bottom: 56px;
        border-bottom: 1px solid rgba(255,255,255,0.08);
    }
    .footer-brand { }
    .footer-logo {
        font-family: 'Cinzel', serif;
        font-size: 1.1rem;
        color: var(--white);
        display: flex; align-items: center; gap: 10px;
        margin-bottom: 18px;
    }
    .footer-logo .crown {
        width: 32px; height: 32px;
        background: linear-gradient(135deg, var(--gold), var(--gold2));
        border-radius: 50%;
        display: flex; align-items: center; justify-content: center;
        font-size: 0.8rem; color: var(--navy);
    }
    .footer-desc { font-size: 0.85rem; line-height: 1.7; max-width: 280px; }
    .footer-col h5 {
        font-family: 'DM Sans', sans-serif;
        font-size: 0.72rem;
        font-weight: 700;
        letter-spacing: 0.18em;
        text-transform: uppercase;
        color: var(--white);
        margin-bottom: 20px;
    }
    .footer-col ul { display: flex; flex-direction: column; gap: 10px; }
    .footer-col ul a {
        font-size: 0.85rem;
        color: rgba(255,255,255,0.45);
        transition: color 0.3s;
    }
    .footer-col ul a:hover { color: var(--gold2); }
    .footer-bottom {
        max-width: 1200px; margin: 0 auto; padding-top: 32px;
        display: flex; justify-content: space-between; align-items: center;
        font-size: 0.78rem;
    }
    .footer-bottom a { color: var(--gold); }

    /* ============================================================
       BACK TO TOP
    ============================================================ */
    #backToTop {
        position: fixed; bottom: 32px; right: 32px;
        width: 48px; height: 48px;
        background: linear-gradient(135deg, var(--navy), var(--navy2));
        color: var(--gold);
        border-radius: 4px;
        display: flex; align-items: center; justify-content: center;
        font-size: 1rem;
        box-shadow: var(--shadow);
        cursor: pointer;
        opacity: 0; pointer-events: none;
        transition: var(--transition);
        z-index: 500;
        border: 1px solid var(--border);
    }
    #backToTop.visible { opacity: 1; pointer-events: all; }
    #backToTop:hover { background: var(--gold); color: var(--navy); transform: translateY(-3px); }

    /* ============================================================
       LIGHTBOX
    ============================================================ */
    .lightbox {
        display: none; position: fixed; inset: 0;
        background: rgba(6,15,30,0.95);
        z-index: 9998;
        align-items: center; justify-content: center;
    }
    .lightbox.open { display: flex; }
    .lightbox img { max-width: 90vw; max-height: 88vh; object-fit: contain; border-radius: 4px; box-shadow: var(--shadow-lg); }
    .lightbox-close {
        position: absolute; top: 24px; right: 28px;
        color: rgba(255,255,255,0.6); font-size: 1.8rem;
        cursor: pointer; transition: color 0.3s;
        background: none; border: none;
        line-height: 1;
    }
    .lightbox-close:hover { color: var(--gold); }

    /* ============================================================
       ANIMATIONS
    ============================================================ */
    .fade-up {
        opacity: 0; transform: translateY(32px);
        transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .fade-up.visible { opacity: 1; transform: translateY(0); }
    .fade-up:nth-child(2) { transition-delay: 0.12s; }
    .fade-up:nth-child(3) { transition-delay: 0.22s; }
    .fade-up:nth-child(4) { transition-delay: 0.32s; }

    /* ============================================================
       RESPONSIVE
    ============================================================ */
    @media (max-width: 1024px) {
        .hero-content { grid-template-columns: 1fr; gap: 40px; }
        .hero-card { margin-top: 0; }
        .about-grid, .admissions-grid, .contact-grid { grid-template-columns: 1fr; }
        .about-image-wrap { max-width: 560px; margin: 0 auto; }
        .admission-info { position: static; }
        .programs-grid { grid-template-columns: 1fr; gap: 0; }
        .testimonials-grid { grid-template-columns: 1fr; }
        .news-grid { grid-template-columns: 1fr 1fr; }
        .gallery-grid { grid-template-columns: 1fr 1fr; }
        .gallery-item:first-child { grid-column: span 1; grid-row: span 1; }
        .gallery-item:first-child img { min-height: 180px; }
        .footer-grid { grid-template-columns: 1fr 1fr; }
    }
    @media (max-width: 768px) {
        .section-pad { padding: 72px 5vw; }
        .nav-links { display: none; position: absolute; top: 72px; left: 0; right: 0; background: rgba(10,22,40,0.98); flex-direction: column; padding: 24px 5vw; gap: 20px; }
        .nav-links.open { display: flex; }
        .hamburger { display: flex; }
        .hero-stats { grid-template-columns: repeat(3, 1fr); }
        .news-grid { grid-template-columns: 1fr; }
        .gallery-grid { grid-template-columns: 1fr 1fr; }
        .about-features { grid-template-columns: 1fr; }
        .form-row { grid-template-columns: 1fr; }
        .footer-grid { grid-template-columns: 1fr; gap: 32px; }
        .footer-bottom { flex-direction: column; gap: 12px; text-align: center; }
    }
    </style>
</head>
<body>

<!-- Scroll Progress -->
<div id="progress-bar"></div>

<!-- ============================================================
     NAVBAR
============================================================ -->
<nav class="navbar" id="navbar">
    <a href="#home" class="nav-logo">
        <div class="crown"><i class="fas fa-crown"></i></div>
        Royal Beginners
    </a>
    <ul class="nav-links" id="navLinks">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#programs">Programmes</a></li>
        <li><a href="#admissions">Admissions</a></li>
        <li><a href="#news">News</a></li>
        <li><a href="#gallery">Gallery</a></li>
        <li><a href="#contact">Contact</a></li>
        <li><a href="#admissions" class="nav-cta">Apply Now</a></li>
    </ul>
    <div class="hamburger" id="hamburger">
        <span></span><span></span><span></span>
    </div>
</nav>

<!-- ============================================================
     HERO
============================================================ -->
<section id="home" class="hero">
    <div class="hero-bg"></div>
    <div class="hero-overlay"></div>
    <div class="hero-content">
        <div class="hero-text">
            <div class="hero-eyebrow">Est. 2015 &nbsp;·&nbsp; Spintex, Accra</div>
            <h1 class="hero-title">
                Where <em>Little Minds</em><br>Grow Into<br>Big Dreams
            </h1>
            <p class="hero-subtitle">
                Accra's premier early childhood school offering a Cambridge-inspired curriculum,
                expert teachers, and an environment where every child truly thrives.
            </p>
            <div class="hero-actions">
                <a href="#admissions" class="btn-primary-hero">Apply for 2026/27</a>
                <a href="#about" class="btn-outline-hero">Discover More</a>
            </div>
        </div>
        <div class="hero-card">
            <div class="hero-badge">Our School in Numbers</div>
            <div class="hero-stats">
                <div class="hero-stat">
                    <span class="num" data-target="300">0</span>
                    <div class="label">Happy Students</div>
                </div>
                <div class="hero-stat">
                    <span class="num" data-target="25">0</span>
                    <div class="label">Expert Staff</div>
                </div>
                <div class="hero-stat">
                    <span class="num" data-target="98" data-suffix="%">0</span>
                    <div class="label">Parent Satisfaction</div>
                </div>
            </div>
        </div>
    </div>
    <div class="hero-scroll">
        <div class="arrow"></div>
        Scroll
    </div>
</section>

<!-- ============================================================
     ABOUT
============================================================ -->
<section id="about" class="about-section section-pad">
    <div class="container-narrow">
        <div class="about-grid">
            <div class="about-image-wrap fade-up">
                <img src="https://images.unsplash.com/photo-1564429238817-393bd4286b2d?w=800&q=80"
                     class="about-img-main" alt="Children learning at Royal Beginners">
                <img src="https://images.unsplash.com/photo-1607453998774-d533f65dac99?w=400&q=80"
                     class="about-img-accent" alt="Classroom activities">
                <div class="about-badge-float">
                    <span class="big">10</span>
                    <div class="small">Years of<br>Excellence</div>
                </div>
            </div>
            <div class="fade-up">
                <div class="section-label">About Our School</div>
                <h2 class="section-title">A Community Built on<br><em>Care & Excellence</em></h2>
                <div class="divider"></div>
                <p class="section-desc">
                    Since 2015, Royal Beginners School has been shaping the brightest futures in
                    Accra. Our philosophy is simple: every child deserves an environment where
                    curiosity is celebrated, creativity is nurtured, and character is built.
                </p>
                <p class="section-desc" style="margin-top: 16px;">
                    With a 1:12 teacher-student ratio and a Cambridge-inspired curriculum, we
                    deliver personalised attention that unlocks each child's unique potential.
                </p>
                <div class="about-features">
                    <div class="feature-item">
                        <i class="fas fa-school-circle-check icon"></i>
                        <div>
                            <h5>Smart Classrooms</h5>
                            <p>Modern learning spaces with interactive technology.</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-book-open-reader icon"></i>
                        <div>
                            <h5>Cambridge-Inspired</h5>
                            <p>World-class curriculum adapted for Ghanaian learners.</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-leaf icon"></i>
                        <div>
                            <h5>Safe Environment</h5>
                            <p>Fully secured campus with 24-hour CCTV.</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-utensils icon"></i>
                        <div>
                            <h5>Healthy Nutrition</h5>
                            <p>Freshly prepared nutritious meals daily.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ============================================================
     PROGRAMMES
============================================================ -->
<section id="programs" class="programs-section section-pad">
    <div class="container-narrow">
        <div class="section-label" style="color: var(--gold);">What We Offer</div>
        <h2 class="section-title">Our <em>Programmes</em></h2>
        <p class="section-desc">Tailored learning journeys for every stage of early childhood development.</p>
    </div>
    <div class="container-narrow">
        <div class="programs-grid">
            <div class="program-card fade-up">
                <div class="prog-number">01</div>
                <div class="prog-icon"><i class="fas fa-baby"></i></div>
                <div class="prog-age">Ages 2 – 3 Years</div>
                <h3 class="prog-title">Playgroup</h3>
                <p class="prog-desc">A gentle, loving introduction to structured learning through play, exploration, and discovery.</p>
                <ul class="prog-features">
                    <li>Sensory & tactile exploration</li>
                    <li>Music, movement & rhythm</li>
                    <li>Social & emotional development</li>
                    <li>Language & communication</li>
                </ul>
            </div>
            <div class="program-card fade-up">
                <div class="prog-number">02</div>
                <div class="prog-icon"><i class="fas fa-child"></i></div>
                <div class="prog-age">Ages 3 – 4 Years</div>
                <h3 class="prog-title">Nursery</h3>
                <p class="prog-desc">Building foundational skills through structured activities that spark imagination and early literacy.</p>
                <ul class="prog-features">
                    <li>Phonics & letter recognition</li>
                    <li>Early numeracy concepts</li>
                    <li>Arts, crafts & creativity</li>
                    <li>Collaborative play</li>
                </ul>
            </div>
            <div class="program-card fade-up">
                <div class="prog-number">03</div>
                <div class="prog-icon"><i class="fas fa-graduation-cap"></i></div>
                <div class="prog-age">Ages 4 – 6 Years</div>
                <h3 class="prog-title">Kindergarten</h3>
                <p class="prog-desc">Comprehensive school readiness through advanced reading, writing, mathematics, and critical thinking.</p>
                <ul class="prog-features">
                    <li>Reading & writing fluency</li>
                    <li>Mathematical foundations</li>
                    <li>Science exploration</li>
                    <li>Problem-solving & logic</li>
                </ul>
            </div>
        </div>
    </div>
</section>

<!-- ============================================================
     ADMISSIONS
============================================================ -->
<section id="admissions" class="admissions-section section-pad">
    <div class="container-narrow">
        <div class="admissions-grid">
            <!-- Left Info Panel -->
            <div class="admission-info fade-up">
                <div class="section-label">Join Our Family</div>
                <h2 class="section-title">Admissions<br><em>2026 / 2027</em></h2>
                <div class="divider"></div>
                <p class="section-desc">
                    We welcome applications on a rolling basis. Limited places are available — 
                    secure your child's future today.
                </p>
                <div class="timeline">
                    <div class="timeline-item">
                        <div class="timeline-dot">1</div>
                        <div class="timeline-text">
                            <h5>Submit Application</h5>
                            <p>Complete the online form with your child's details.</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-dot">2</div>
                        <div class="timeline-text">
                            <h5>Confirmation Call</h5>
                            <p>Our admissions team will contact you within 48 hours.</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-dot">3</div>
                        <div class="timeline-text">
                            <h5>School Visit</h5>
                            <p>Tour our campus and meet the team at your convenience.</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-dot">4</div>
                        <div class="timeline-text">
                            <h5>Enrolment</h5>
                            <p>Complete registration documents and secure your place.</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Right Form -->
            <div class="fade-up">
                <div class="form-card">
                    <div class="form-header">
                        <h3>Application Form</h3>
                        <p>All fields are required. We'll be in touch shortly.</p>
                    </div>
                    <div class="form-body">
                        <?php if ($message === 'success'): ?>
                        <div class="alert-box alert-success">
                            <i class="fas fa-circle-check"></i>
                            Application submitted successfully! We will contact you within 48 hours.
                        </div>
                        <?php elseif ($message === 'error'): ?>
                        <div class="alert-box alert-error">
                            <i class="fas fa-circle-exclamation"></i>
                            Something went wrong. Please try again.
                        </div>
                        <?php endif; ?>

                        <form method="POST" novalidate>
                            <input type="hidden" name="admission_submit" value="1">
                            <div class="form-row">
                                <div class="form-group">
                                    <label class="form-label">Child's Full Name</label>
                                    <input type="text" name="child_name" class="form-control" placeholder="e.g. Ama Asante" required>
                                </div>
                                <div class="form-group">
                                    <label class="form-label">Date of Birth</label>
                                    <input type="date" name="dob" class="form-control" required>
                                </div>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Parent / Guardian Name</label>
                                <input type="text" name="parent_name" class="form-control" placeholder="e.g. Kofi Asante" required>
                            </div>
                            <div class="form-row">
                                <div class="form-group">
                                    <label class="form-label">Phone Number</label>
                                    <input type="tel" name="phone" class="form-control" placeholder="+233 24 000 0000" required>
                                </div>
                                <div class="form-group">
                                    <label class="form-label">Email Address</label>
                                    <input type="email" name="email" class="form-control" placeholder="you@example.com" required>
                                </div>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Desired Programme</label>
                                <div class="form-select-wrap">
                                    <select name="class" class="form-select" required>
                                        <option value="">Select a programme</option>
                                        <option value="Playgroup">Playgroup (2–3 years)</option>
                                        <option value="Nursery">Nursery (3–4 years)</option>
                                        <option value="KG1">Kindergarten 1 (4–5 years)</option>
                                        <option value="KG2">Kindergarten 2 (5–6 years)</option>
                                    </select>
                                </div>
                            </div>
                            <button type="submit" class="btn-submit">
                                <i class="fas fa-paper-plane" style="margin-right: 8px;"></i>
                                Submit Application
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ============================================================
     NEWS
============================================================ -->
<section id="news" class="news-section section-pad">
    <div class="container-narrow">
        <div class="section-label">Stay Informed</div>
        <h2 class="section-title">Latest <em>News & Events</em></h2>
        <div class="divider"></div>
        <div class="news-grid">
            <?php
            $n_result = $conn->query("SELECT * FROM news ORDER BY created_at DESC LIMIT 3");
            if ($n_result && $n_result->num_rows > 0):
                $count = 0;
                $unsplash_seeds = [1001, 1002, 1003];
                while ($row = $n_result->fetch_assoc()):
                    $img = !empty($row['image']) ? htmlspecialchars($row['image'])
                         : "https://images.unsplash.com/photo-" . $unsplash_seeds[$count] . "?w=600&q=75";
                    $count++;
            ?>
            <div class="news-card fade-up">
                <div class="news-img-wrap">
                    <img src="<?= $img ?>" class="news-img" alt="<?= htmlspecialchars($row['title']) ?>">
                </div>
                <div class="news-body">
                    <div class="news-cat">School News</div>
                    <h3 class="news-title"><?= htmlspecialchars($row['title']) ?></h3>
                    <p class="news-excerpt"><?= substr(htmlspecialchars($row['content']), 0, 120) ?>...</p>
                    <div class="news-date">
                        <i class="far fa-calendar"></i>
                        <?= date('d F Y', strtotime($row['created_at'])) ?>
                    </div>
                </div>
            </div>
            <?php endwhile; else: ?>
            <div class="news-placeholder">
                <i class="far fa-newspaper"></i>
                <p>No news articles yet. Check back soon for updates!</p>
            </div>
            <?php endif; ?>
        </div>
    </div>
</section>

<!-- ============================================================
     GALLERY
============================================================ -->
<section id="gallery" class="gallery-section section-pad">
    <div class="container-narrow">
        <div class="section-label" style="color: var(--gold);">Our School Life</div>
        <h2 class="section-title">Campus <em>Gallery</em></h2>
        <p class="section-desc">Glimpses into the joy, learning, and vibrant community at Royal Beginners.</p>
    </div>
    <div class="container-wide" style="margin-top: 0;">
        <div class="gallery-grid">
            <?php
            $gallery_images = [
                ['https://images.unsplash.com/photo-1503676260728-1c00da094a0b?w=800&q=80', 'Children in class'],
                ['https://images.unsplash.com/photo-1560785496-3c9d27877182?w=600&q=80', 'Creative arts'],
                ['https://images.unsplash.com/photo-1567057419565-4349c49d8a04?w=600&q=80', 'Outdoor play'],
                ['https://images.unsplash.com/photo-1548248823-ce16a73b6d49?w=600&q=80', 'Reading time'],
                ['https://images.unsplash.com/photo-1580582932707-520aed937b7b?w=600&q=80', 'Science fun'],
            ];

            // Check DB gallery first
            $g_result = $conn->query("SELECT * FROM gallery ORDER BY created_at DESC LIMIT 5");
            $db_gallery = [];
            if ($g_result && $g_result->num_rows > 0) {
                while ($g = $g_result->fetch_assoc()) $db_gallery[] = [$g['image_url'], $g['caption']];
            }
            $final_gallery = count($db_gallery) > 0 ? $db_gallery : $gallery_images;

            foreach ($final_gallery as $gitem):
            ?>
            <div class="gallery-item" onclick="openLightbox('<?= htmlspecialchars($gitem[0]) ?>')">
                <img src="<?= htmlspecialchars($gitem[0]) ?>" alt="<?= htmlspecialchars($gitem[1]) ?>" loading="lazy">
                <div class="gallery-overlay">
                    <span><i class="fas fa-expand-alt" style="margin-right: 6px;"></i><?= htmlspecialchars($gitem[1]) ?></span>
                </div>
            </div>
            <?php endforeach; ?>
        </div>
    </div>
</section>

<!-- ============================================================
     CONTACT
============================================================ -->
<section id="contact" class="contact-section section-pad">
    <div class="container-narrow">
        <div class="section-label">Reach Us</div>
        <h2 class="section-title">Get In <em>Touch</em></h2>
        <div class="divider"></div>
        <div class="contact-grid">
            <!-- Form -->
            <div class="fade-up">
                <?php if ($contact_message === 'success'): ?>
                <div class="alert-box alert-success" style="margin-bottom: 28px;">
                    <i class="fas fa-circle-check"></i>
                    Thank you! Your message has been received. We'll respond within 24 hours.
                </div>
                <?php elseif ($contact_message === 'error'): ?>
                <div class="alert-box alert-error" style="margin-bottom: 28px;">
                    <i class="fas fa-circle-exclamation"></i>
                    Something went wrong. Please try again.
                </div>
                <?php endif; ?>

                <form method="POST">
                    <input type="hidden" name="contact_submit" value="1">
                    <div class="form-group">
                        <label class="form-label">Your Full Name</label>
                        <input type="text" name="name" class="form-control" placeholder="e.g. Kwame Mensah" required>
                    </div>
                    <div class="form-group">
                        <label class="form-label">Email Address</label>
                        <input type="email" name="email" class="form-control" placeholder="you@example.com" required>
                    </div>
                    <div class="form-group">
                        <label class="form-label">Your Message</label>
                        <textarea name="message" class="form-control" rows="6" placeholder="How can we help you?" required style="resize: vertical;"></textarea>
                    </div>
                    <button type="submit" class="btn-submit" style="max-width: 260px;">
                        <i class="fas fa-paper-plane" style="margin-right: 8px;"></i>
                        Send Message
                    </button>
                </form>
            </div>

            <!-- Info -->
            <div class="contact-info fade-up">
                <div class="contact-detail">
                    <div class="contact-icon"><i class="fas fa-location-dot"></i></div>
                    <div>
                        <h5>Location</h5>
                        <p>North Kaneshie, Community 18<br>Accra, Greater Accra, Ghana</p>
                    </div>
                </div>
                <div class="contact-detail">
                    <div class="contact-icon"><i class="fas fa-phone"></i></div>
                    <div>
                        <h5>Phone</h5>
                        <p>
                            <a href="tel:+233241234567">+233 24 123 4567</a><br>
                            <a href="tel:+233301234567">+233 30 123 4567</a>
                        </p>
                    </div>
                </div>
                <div class="contact-detail">
                    <div class="contact-icon"><i class="fas fa-envelope"></i></div>
                    <div>
                        <h5>Email</h5>
                        <p><a href="mailto:info@royalbeginners.edu.gh">info@royalbeginners.edu.gh</a></p>
                    </div>
                </div>
                <div class="contact-detail">
                    <div class="contact-icon"><i class="fas fa-clock"></i></div>
                    <div>
                        <h5>School Hours</h5>
                        <p>Monday – Friday: 7:00 AM – 4:00 PM<br>
                        <span style="font-size: 0.82rem; color: var(--muted);">Office: 7:30 AM – 5:00 PM</span></p>
                    </div>
                </div>

                <div class="map-wrap">
                    <iframe
                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3970.716714869878!2d-0.0899!3d5.6176!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zNcKwMzcnMDMuNCJOIDDCsDA1JzIzLjYiVw!5e0!3m2!1sen!2sgh!4v1234567890"
                        allowfullscreen loading="lazy" referrerpolicy="no-referrer-when-downgrade">
                    </iframe>
                </div>

                <div class="social-links">
                    <a href="#" class="social-link" title="Facebook"><i class="fab fa-facebook-f"></i></a>
                    <a href="#" class="social-link" title="Instagram"><i class="fab fa-instagram"></i></a>
                    <a href="#" class="social-link" title="Twitter/X"><i class="fab fa-x-twitter"></i></a>
                    <a href="#" class="social-link" title="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                    <a href="#" class="social-link" title="YouTube"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ============================================================
     FOOTER
============================================================ -->
<footer>
    <div class="footer-grid">
        <div class="footer-brand">
            <div class="footer-logo">
                <div class="crown"><i class="fas fa-crown"></i></div>
                Royal Beginners School
            </div>
            <p class="footer-desc">Nurturing excellence, building character, and shaping extraordinary futures — one child at a time since 2015.</p>
        </div>
        <div class="footer-col">
            <h5>Navigation</h5>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About Us</a></li>
                <li><a href="#programs">Programmes</a></li>
                <li><a href="#admissions">Admissions</a></li>
                <li><a href="#gallery">Gallery</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
        <div class="footer-col">
            <h5>Programmes</h5>
            <ul>
                <li><a href="#programs">Playgroup (2–3 yrs)</a></li>
                <li><a href="#programs">Nursery (3–4 yrs)</a></li>
                <li><a href="#programs">KG1 (4–5 yrs)</a></li>
                <li><a href="#programs">KG2 (5–6 yrs)</a></li>
                <li><a href="#admissions">Apply Now</a></li>
            </ul>
        </div>
        <div class="footer-col">
            <h5>Contact</h5>
            <ul>
                <li><a href="tel:+233241234567">+233 24 123 4567</a></li>
                <li><a href="mailto:info@royalbeginners.edu.gh">info@royalbeginners.edu.gh</a></li>
                <li><a href="#">Spintex Rd, Accra, Ghana</a></li>
                <li><a href="#">Mon – Fri: 7:00 AM – 4:00 PM</a></li>
            </ul>
        </div>
    </div>
    <div class="footer-bottom">
        <p>&copy; <?= date("Y") ?> Royal Beginners School. All Rights Reserved.</p>
        <p>Designed with <span style="color: var(--gold);">♥</span> for excellence in education &nbsp;·&nbsp; <a href="#admissions">Enrol Today</a></p>
    </div>
</footer>

<!-- Back to Top -->
<div id="backToTop" title="Back to top"><i class="fas fa-chevron-up"></i></div>

<!-- Lightbox -->
<div class="lightbox" id="lightbox">
    <button class="lightbox-close" onclick="closeLightbox()">&times;</button>
    <img id="lightbox-img" src="" alt="Gallery image">
</div>

<!-- ============================================================
     JAVASCRIPT
============================================================ -->
<script>
// --- Scroll Progress & Navbar ---
const progressBar = document.getElementById('progress-bar');
const navbar = document.getElementById('navbar');
const backToTop = document.getElementById('backToTop');

window.addEventListener('scroll', () => {
    const scrollTop = window.scrollY;
    const docHeight = document.documentElement.scrollHeight - window.innerHeight;
    progressBar.style.width = (scrollTop / docHeight * 100) + '%';

    navbar.classList.toggle('scrolled', scrollTop > 60);
    backToTop.classList.toggle('visible', scrollTop > 400);
});

// --- Back to Top ---
backToTop.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));

// --- Hamburger ---
const hamburger = document.getElementById('hamburger');
const navLinks  = document.getElementById('navLinks');
hamburger.addEventListener('click', () => navLinks.classList.toggle('open'));
navLinks.querySelectorAll('a').forEach(a => a.addEventListener('click', () => navLinks.classList.remove('open')));

// --- Smooth Scroll ---
document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
        const target = document.querySelector(a.getAttribute('href'));
        if (target) { e.preventDefault(); target.scrollIntoView({ behavior: 'smooth', block: 'start' }); }
    });
});

// --- Counter Animation ---
function animateCounter(el) {
    const target  = parseInt(el.dataset.target);
    const suffix  = el.dataset.suffix || '';
    const duration = 1600;
    const step = target / (duration / 16);
    let current = 0;
    const timer = setInterval(() => {
        current = Math.min(current + step, target);
        el.textContent = Math.round(current) + suffix;
        if (current >= target) clearInterval(timer);
    }, 16);
}

// --- Intersection Observer ---
const fadeEls = document.querySelectorAll('.fade-up');
const counters = document.querySelectorAll('.num[data-target]');
let countersDone = false;

const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) entry.target.classList.add('visible');
    });
}, { threshold: 0.12 });
fadeEls.forEach(el => observer.observe(el));

const counterObserver = new IntersectionObserver((entries) => {
    if (entries[0].isIntersecting && !countersDone) {
        countersDone = true;
        counters.forEach(animateCounter);
    }
}, { threshold: 0.5 });
const heroCard = document.querySelector('.hero-card');
if (heroCard) counterObserver.observe(heroCard);

// --- Lightbox ---
function openLightbox(src) {
    document.getElementById('lightbox-img').src = src;
    document.getElementById('lightbox').classList.add('open');
    document.body.style.overflow = 'hidden';
}
function closeLightbox() {
    document.getElementById('lightbox').classList.remove('open');
    document.body.style.overflow = '';
}
document.getElementById('lightbox').addEventListener('click', e => {
    if (e.target === e.currentTarget) closeLightbox();
});
document.addEventListener('keydown', e => { if (e.key === 'Escape') closeLightbox(); });

// --- Navbar active state ---
const sections = document.querySelectorAll('section[id]');
const navAnchors = document.querySelectorAll('.nav-links a[href^="#"]');
const activateNav = () => {
    let current = '';
    sections.forEach(s => {
        if (window.scrollY >= s.offsetTop - 100) current = s.id;
    });
    navAnchors.forEach(a => {
        a.style.color = a.getAttribute('href') === '#' + current
            ? 'var(--gold2)' : '';
    });
};
window.addEventListener('scroll', activateNav);
</script>
</body>
</html>
