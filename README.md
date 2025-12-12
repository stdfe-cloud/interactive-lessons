<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Lessons Hub | Mission-Based Learning</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --navy: #0a1628;
            --navy-light: #1a2d4a;
            --blue: #3b82f6;
            --blue-light: #60a5fa;
            --green: #10b981;
            --green-light: #34d399;
            --orange: #f59e0b;
            --purple: #8b5cf6;
            --red: #ef4444;
            --cream: #f8fafc;
            --grey: #e2e8f0;
            --text: #1e293b;
            --text-light: #64748b;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background: var(--cream);
            color: var(--text);
            line-height: 1.6;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--navy) 0%, var(--navy-light) 50%, #234 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
        }

        /* Floating shapes */
        .shape {
            position: absolute;
            border-radius: 50%;
            opacity: 0.1;
            animation: float 20s ease-in-out infinite;
        }

        .shape-1 {
            width: 400px;
            height: 400px;
            background: var(--blue);
            top: -100px;
            right: -100px;
            animation-delay: 0s;
        }

        .shape-2 {
            width: 300px;
            height: 300px;
            background: var(--green);
            bottom: -50px;
            left: -50px;
            animation-delay: -5s;
        }

        .shape-3 {
            width: 200px;
            height: 200px;
            background: var(--orange);
            top: 50%;
            left: 10%;
            animation-delay: -10s;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            25% { transform: translate(20px, -20px) rotate(5deg); }
            50% { transform: translate(-10px, 20px) rotate(-5deg); }
            75% { transform: translate(15px, 10px) rotate(3deg); }
        }

        /* Navigation */
        nav {
            padding: 24px 48px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: relative;
            z-index: 10;
        }

        .logo {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.5rem;
            color: white;
            letter-spacing: 2px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo span {
            color: var(--orange);
        }

        .nav-links {
            display: flex;
            gap: 32px;
        }

        .nav-links a {
            color: rgba(255,255,255,0.8);
            text-decoration: none;
            font-weight: 500;
            font-size: 0.95rem;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: white;
        }

        /* Hero Content */
        .hero-content {
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 24px;
            position: relative;
            z-index: 10;
        }

        .badge {
            background: rgba(255,255,255,0.1);
            border: 1px solid rgba(255,255,255,0.2);
            padding: 8px 20px;
            border-radius: 50px;
            color: var(--orange);
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 24px;
            backdrop-filter: blur(10px);
        }

        .hero h1 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: clamp(3rem, 8vw, 6rem);
            color: white;
            letter-spacing: 3px;
            line-height: 1.1;
            margin-bottom: 20px;
        }

        .hero h1 span {
            background: linear-gradient(135deg, var(--orange), var(--orange));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero-subtitle {
            font-size: 1.25rem;
            color: rgba(255,255,255,0.7);
            max-width: 600px;
            margin-bottom: 40px;
        }

        .hero-buttons {
            display: flex;
            gap: 16px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn {
            padding: 16px 32px;
            border-radius: 12px;
            font-weight: 600;
            font-size: 1rem;
            text-decoration: none;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary {
            background: var(--green);
            color: white;
            box-shadow: 0 4px 20px rgba(16, 185, 129, 0.4);
        }

        .btn-primary:hover {
            background: var(--green-light);
            transform: translateY(-2px);
            box-shadow: 0 6px 30px rgba(16, 185, 129, 0.5);
        }

        .btn-secondary {
            background: rgba(255,255,255,0.1);
            color: white;
            border: 1px solid rgba(255,255,255,0.3);
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-2px);
        }

        /* Stats Bar */
        .stats-bar {
            display: flex;
            justify-content: center;
            gap: 60px;
            padding: 40px;
            position: relative;
            z-index: 10;
        }

        .stat {
            text-align: center;
        }

        .stat-number {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2.5rem;
            color: white;
            letter-spacing: 1px;
        }

        .stat-label {
            color: rgba(255,255,255,0.6);
            font-size: 0.9rem;
        }

        /* Features Section */
        .features {
            padding: 100px 24px;
            background: white;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-badge {
            background: var(--blue);
            color: white;
            padding: 6px 16px;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 600;
            display: inline-block;
            margin-bottom: 16px;
        }

        .section-title {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 3rem;
            color: var(--navy);
            letter-spacing: 2px;
            margin-bottom: 16px;
        }

        .section-subtitle {
            color: var(--text-light);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: var(--cream);
            padding: 32px;
            border-radius: 20px;
            transition: all 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.08);
        }

        .feature-icon {
            width: 56px;
            height: 56px;
            background: linear-gradient(135deg, var(--blue), var(--blue-light));
            border-radius: 14px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            margin-bottom: 20px;
        }

        .feature-card:nth-child(2) .feature-icon {
            background: linear-gradient(135deg, var(--green), var(--green-light));
        }

        .feature-card:nth-child(3) .feature-icon {
            background: linear-gradient(135deg, var(--orange), #fbbf24);
        }

        .feature-card:nth-child(4) .feature-icon {
            background: linear-gradient(135deg, var(--purple), #a78bfa);
        }

        .feature-card:nth-child(5) .feature-icon {
            background: linear-gradient(135deg, var(--red), #f87171);
        }

        .feature-card:nth-child(6) .feature-icon {
            background: linear-gradient(135deg, #06b6d4, #22d3ee);
        }

        .feature-card h3 {
            font-size: 1.25rem;
            color: var(--navy);
            margin-bottom: 12px;
            font-weight: 700;
        }

        .feature-card p {
            color: var(--text-light);
            font-size: 0.95rem;
            line-height: 1.7;
        }

        /* Lessons Section */
        .lessons {
            padding: 100px 24px;
            background: linear-gradient(180deg, var(--cream) 0%, white 100%);
        }

        .subject-section {
            margin-bottom: 60px;
        }

        .subject-header {
            display: flex;
            align-items: center;
            gap: 16px;
            margin-bottom: 30px;
        }

        .subject-icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }

        .subject-icon.geography {
            background: linear-gradient(135deg, var(--green), var(--green-light));
        }

        .subject-icon.history {
            background: linear-gradient(135deg, var(--orange), #fbbf24);
        }

        .subject-icon.english {
            background: linear-gradient(135deg, var(--blue), var(--blue-light));
        }

        .subject-title {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2rem;
            color: var(--navy);
            letter-spacing: 1px;
        }

        .lessons-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 24px;
        }

        .lesson-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 4px 20px rgba(0,0,0,0.06);
            transition: all 0.3s;
            text-decoration: none;
            color: inherit;
            display: block;
        }

        .lesson-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.12);
        }

        .lesson-card.coming-soon {
            opacity: 0.6;
            pointer-events: none;
        }

        .lesson-image {
            height: 160px;
            background: linear-gradient(135deg, var(--navy) 0%, var(--navy-light) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .lesson-image.geography {
            background: linear-gradient(135deg, #065f46 0%, #10b981 100%);
        }

        .lesson-image.history {
            background: linear-gradient(135deg, #92400e 0%, #f59e0b 100%);
        }

        .lesson-image.english {
            background: linear-gradient(135deg, #1e40af 0%, #3b82f6 100%);
        }

        .lesson-emoji {
            font-size: 4rem;
            opacity: 0.9;
        }

        .lesson-badge {
            position: absolute;
            top: 16px;
            right: 16px;
            background: var(--green);
            color: white;
            padding: 6px 14px;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 700;
        }

        .lesson-badge.coming {
            background: var(--text-light);
        }

        .lesson-content {
            padding: 28px;
        }

        .lesson-content h3 {
            font-size: 1.3rem;
            color: var(--navy);
            margin-bottom: 4px;
            font-weight: 700;
        }

        .lesson-role {
            color: var(--blue);
            font-weight: 600;
            font-size: 0.9rem;
            margin-bottom: 12px;
        }

        .lesson-content p {
            color: var(--text-light);
            font-size: 0.95rem;
            margin-bottom: 20px;
            line-height: 1.6;
        }

        .lesson-meta {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .meta-tag {
            background: var(--cream);
            padding: 6px 12px;
            border-radius: 8px;
            font-size: 0.85rem;
            color: var(--text-light);
            display: flex;
            align-items: center;
            gap: 6px;
        }

        /* Quote Section */
        .quote-section {
            padding: 100px 24px;
            background: var(--navy);
            text-align: center;
        }

        .quote {
            font-family: 'Bebas Neue', sans-serif;
            font-size: clamp(1.8rem, 4vw, 3rem);
            color: white;
            letter-spacing: 2px;
            max-width: 900px;
            margin: 0 auto 24px;
            line-height: 1.3;
        }

        .quote span {
            color: var(--orange);
        }

        .quote-author {
            color: rgba(255,255,255,0.6);
            font-size: 1rem;
        }

        /* How It Works */
        .how-it-works {
            padding: 100px 24px;
            background: white;
        }

        .steps-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .step {
            text-align: center;
        }

        .step-number {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--blue), var(--blue-light));
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.5rem;
            margin: 0 auto 20px;
        }

        .step h3 {
            font-size: 1.2rem;
            color: var(--navy);
            margin-bottom: 10px;
            font-weight: 700;
        }

        .step p {
            color: var(--text-light);
            font-size: 0.95rem;
        }

        /* CTA Section */
        .cta-section {
            padding: 80px 24px;
            background: linear-gradient(135deg, var(--green) 0%, var(--green-light) 100%);
            text-align: center;
        }

        .cta-section h2 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2.5rem;
            color: white;
            letter-spacing: 2px;
            margin-bottom: 16px;
        }

        .cta-section p {
            color: rgba(255,255,255,0.9);
            font-size: 1.1rem;
            margin-bottom: 30px;
        }

        .cta-section .btn {
            background: white;
            color: var(--green);
        }

        .cta-section .btn:hover {
            background: var(--cream);
        }

        /* Footer */
        footer {
            padding: 60px 24px;
            background: var(--navy);
            text-align: center;
        }

        .footer-logo {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.5rem;
            color: white;
            letter-spacing: 2px;
            margin-bottom: 20px;
        }

        .footer-logo span {
            color: var(--orange);
        }

        .footer-text {
            color: rgba(255,255,255,0.6);
            font-size: 0.9rem;
            max-width: 500px;
            margin: 0 auto 20px;
        }

        .footer-bottom {
            color: rgba(255,255,255,0.4);
            font-size: 0.85rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav {
                padding: 20px 24px;
            }

            .nav-links {
                display: none;
            }

            .stats-bar {
                flex-wrap: wrap;
                gap: 30px;
            }

            .hero-buttons {
                flex-direction: column;
                width: 100%;
                padding: 0 20px;
            }

            .btn {
                width: 100%;
                justify-content: center;
            }

            .lessons-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <!-- Hero Section -->
    <section class="hero">
        <div class="shape shape-1"></div>
        <div class="shape shape-2"></div>
        <div class="shape shape-3"></div>

        <nav>
            <div class="logo">
                🎓 INTERACTIVE <span>LESSONS</span>
            </div>
            <div class="nav-links">
                <a href="#lessons">Lessons</a>
                <a href="#features">Features</a>
                <a href="#how-it-works">How It Works</a>
            </div>
        </nav>

        <div class="hero-content">
            <div class="badge">🎮 Mission-Based Learning</div>
            <h1>LESSONS THAT MAKE<br>STUDENTS <span>CARE</span></h1>
            <p class="hero-subtitle">Gamified, interactive lessons designed for students who've switched off. Give them a role, a mission, and a reason to learn.</p>
            <div class="hero-buttons">
                <a href="#lessons" class="btn btn-primary">
                    🚀 Explore Lessons
                </a>
                <a href="#features" class="btn btn-secondary">
                    ✨ See Features
                </a>
            </div>
        </div>

        <div class="stats-bar">
            <div class="stat">
                <div class="stat-number">100%</div>
                <div class="stat-label">Chromebook Ready</div>
            </div>
            <div class="stat">
                <div class="stat-number">0</div>
                <div class="stat-label">Marking Required</div>
            </div>
            <div class="stat">
                <div class="stat-number">XP</div>
                <div class="stat-label">Gamified Learning</div>
            </div>
            <div class="stat">
                <div class="stat-number">∞</div>
                <div class="stat-label">Auto-Save</div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <div class="container">
            <div class="section-header">
                <div class="section-badge">Why It Works</div>
                <h2 class="section-title">TRADITIONAL WORKSHEETS DON'T WORK<br>FOR EVERY LEARNER</h2>
                <p class="section-subtitle">These lessons use mission-based learning — giving students a professional role, a purpose, and a reason to care.</p>
            </div>

            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">🎮</div>
                    <h3>Gamification</h3>
                    <p>Students earn XP, unlock achievement badges, and level up through ranks. Progress feels like playing a game.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📺</div>
                    <h3>Real Video Footage</h3>
                    <p>Embedded YouTube videos bring content to life. Real earthquake footage, real historical archives.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🧠</div>
                    <h3>Interactive Quizzes</h3>
                    <p>Built-in knowledge checks with instant feedback. Sound effects for correct answers. No marking needed.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">✍️</div>
                    <h3>Scaffolded Writing</h3>
                    <p>Sentence starters, structured tasks, and talk-before-write activities. Perfect for all learners.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">💾</div>
                    <h3>Auto-Save Progress</h3>
                    <p>Work saves automatically. Students can close the browser and come back — nothing lost.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📤</div>
                    <h3>Submit to Teacher</h3>
                    <p>One-click email sends all responses directly to you. Student name, answers, and XP earned.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Lessons Section -->
    <section class="lessons" id="lessons">
        <div class="container">
            <div class="section-header">
                <div class="section-badge">Available Now</div>
                <h2 class="section-title">EXPLORE LESSONS</h2>
                <p class="section-subtitle">Click any lesson to open it. Share the link with your class via Google Classroom.</p>
            </div>

            <!-- Geography -->
            <div class="subject-section">
                <div class="subject-header">
                    <div class="subject-icon geography">🌍</div>
                    <h3 class="subject-title">GEOGRAPHY</h3>
                </div>
                <div class="lessons-grid">
                    <!-- Tectonic Hazards - LIVE -->
                    <a href="geography/tectonic-hazards/" class="lesson-card">
                        <div class="lesson-image geography">
                            <span class="lesson-emoji">🌋</span>
                            <span class="lesson-badge">LIVE</span>
                        </div>
                        <div class="lesson-content">
                            <h3>Tectonic Hazards</h3>
                            <div class="lesson-role">Disaster Consultant Training</div>
                            <p>Students advise the fictional nation of Terrafirma on how to save lives. Covers plate tectonics, Sichuan 2008, and Sendai 2011.</p>
                            <div class="lesson-meta">
                                <span class="meta-tag">📚 Year 7</span>
                                <span class="meta-tag">⏱️ 4-5 lessons</span>
                                <span class="meta-tag">🎮 Gamified</span>
                            </div>
                        </div>
                    </a>

                    <!-- Coasts - Coming Soon -->
                    <div class="lesson-card coming-soon">
                        <div class="lesson-image geography">
                            <span class="lesson-emoji">🌊</span>
                            <span class="lesson-badge coming">COMING SOON</span>
                        </div>
                        <div class="lesson-content">
                            <h3>Coasts</h3>
                            <div class="lesson-role">Coastal Engineer Training</div>
                            <p>Design coastal defences for a vulnerable town. Erosion, deposition, and hard vs soft engineering.</p>
                            <div class="lesson-meta">
                                <span class="meta-tag">📚 Year 8</span>
                                <span class="meta-tag">⏱️ 3-4 lessons</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- History -->
            <div class="subject-section">
                <div class="subject-header">
                    <div class="subject-icon history">📜</div>
                    <h3 class="subject-title">HISTORY</h3>
                </div>
                <div class="lessons-grid">
                    <div class="lesson-card coming-soon">
                        <div class="lesson-image history">
                            <span class="lesson-emoji">⚔️</span>
                            <span class="lesson-badge coming">COMING SOON</span>
                        </div>
                        <div class="lesson-content">
                            <h3>WW1 Trenches</h3>
                            <div class="lesson-role">War Correspondent Training</div>
                            <p>Report from the Western Front. Investigate conditions, tactics, and the human experience of trench warfare.</p>
                            <div class="lesson-meta">
                                <span class="meta-tag">📚 Year 9</span>
                                <span class="meta-tag">⏱️ 4-5 lessons</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- English -->
            <div class="subject-section">
                <div class="subject-header">
                    <div class="subject-icon english">📖</div>
                    <h3 class="subject-title">ENGLISH LANGUAGE</h3>
                </div>
                <div class="lessons-grid">
                    <div class="lesson-card coming-soon">
                        <div class="lesson-image english">
                            <span class="lesson-emoji">✍️</span>
                            <span class="lesson-badge coming">COMING SOON</span>
                        </div>
                        <div class="lesson-content">
                            <h3>Descriptive Writing</h3>
                            <div class="lesson-role">Author's Workshop</div>
                            <p>Master sensory language, sentence variety, and structural techniques for IGCSE Paper 1.</p>
                            <div class="lesson-meta">
                                <span class="meta-tag">📚 Year 10-11</span>
                                <span class="meta-tag">⏱️ 3-4 lessons</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Quote Section -->
    <section class="quote-section">
        <div class="container">
            <p class="quote">"DISENGAGEMENT ISN'T A READING PROBLEM OR A WRITING PROBLEM — IT'S A <span>RELEVANCE</span> PROBLEM"</p>
            <p class="quote-author">These lessons give students a reason to care before asking them to learn.</p>
        </div>
    </section>

    <!-- How It Works -->
    <section class="how-it-works" id="how-it-works">
        <div class="container">
            <div class="section-header">
                <div class="section-badge">Simple Setup</div>
                <h2 class="section-title">HOW TO USE THESE LESSONS</h2>
                <p class="section-subtitle">No software to install. No accounts to create. Just click and teach.</p>
            </div>

            <div class="steps-grid">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3>Click a Lesson</h3>
                    <p>Choose from the available lessons above. It opens instantly in any browser.</p>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Share the Link</h3>
                    <p>Post the URL in Google Classroom. Students open it on their Chromebooks.</p>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Students Work</h3>
                    <p>They earn XP, complete tasks, and their progress saves automatically.</p>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>Receive Work</h3>
                    <p>Students click "Submit to Teacher" — their completed work arrives in your email.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
        <div class="container">
            <h2>READY TO ENGAGE YOUR CLASS?</h2>
            <p>Start with Tectonic Hazards — the first complete lesson is ready now.</p>
            <a href="geography/tectonic-hazards/" class="btn">
                🌋 Open Tectonic Hazards
            </a>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-logo">🎓 INTERACTIVE <span>LESSONS</span></div>
        <p class="footer-text">Built with ❤️ for teachers who refuse to accept "they just don't care."</p>
        <p class="footer-bottom">© 2026 Malden Oaks - Damian Fearon. Designed for GCSE & IGCSE students.</p>
    </footer>

</body>
</html>
