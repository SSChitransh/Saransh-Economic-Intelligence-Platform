<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🌍 Saransh's Economic Intelligence Platform</title>

    <!-- Plotly CDN -->
    <script src="https://cdn.plot.ly/plotly-2.27.0.min.js"></script>

    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800;900&display=swap" rel="stylesheet">

    <style>
        /* ============================================
           RESET & BASE
           ============================================ */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: #0a0e14;
            color: #e8edf3;
            line-height: 1.6;
            overflow-x: hidden;
        }

        a {
            color: #f5c518;
            text-decoration: none;
        }
        a:hover {
            color: #ffd700;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* ============================================
           DISNEY+ HOTSTAR HEADER
           ============================================ */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            background: linear-gradient(180deg, rgba(10, 14, 20, 0.95) 0%, rgba(10, 14, 20, 0.85) 80%, transparent 100%);
            padding: 16px 0;
            transition: all 0.3s ease;
        }

        .navbar .container {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 12px;
        }

        .navbar .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 1.4rem;
            font-weight: 800;
        }

        .navbar .logo span {
            color: #f5c518;
        }

        .navbar .logo .badge {
            font-size: 0.65rem;
            background: #f5c51822;
            color: #f5c518;
            border: 1px solid #f5c51844;
            padding: 2px 12px;
            border-radius: 50px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .navbar .nav-links {
            display: flex;
            align-items: center;
            gap: 24px;
            font-size: 0.9rem;
            font-weight: 600;
        }

        .navbar .nav-links a {
            color: #b0b8c8;
            transition: color 0.3s ease;
        }
        .navbar .nav-links a:hover {
            color: #f5c518;
        }

        .navbar .nav-links .btn-nav {
            background: #f5c518;
            color: #0a0e14;
            padding: 8px 20px;
            border-radius: 50px;
            font-weight: 700;
            transition: all 0.3s ease;
        }
        .navbar .nav-links .btn-nav:hover {
            background: #ffd700;
            transform: scale(1.04);
            color: #0a0e14;
        }

        /* ============================================
           DISNEY+ HOTSTAR HERO
           ============================================ */
        .hero {
            position: relative;
            min-height: 85vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(145deg, #0a0e14 0%, #1a1f2e 50%, #0f172a 100%);
            overflow: hidden;
            padding-top: 80px;
            border-bottom: 3px solid #f5c51822;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle at 30% 50%, #f5c51808 0%, transparent 60%),
                        radial-gradient(circle at 70% 80%, #f5c51806 0%, transparent 50%);
            animation: pulseGlow 10s ease-in-out infinite alternate;
            z-index: 1;
            pointer-events: none;
        }

        @keyframes pulseGlow {
            0% { opacity: 0.6; transform: scale(1) rotate(0deg); }
            100% { opacity: 1; transform: scale(1.05) rotate(3deg); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 900px;
            padding: 40px 20px;
        }

        .hero-badge {
            display: inline-block;
            background: #f5c51822;
            color: #f5c518;
            border: 1px solid #f5c51844;
            padding: 6px 24px;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 24px;
        }

        .hero h1 {
            font-size: clamp(3rem, 10vw, 6rem);
            font-weight: 900;
            line-height: 1.05;
            background: linear-gradient(135deg, #ffffff 30%, #f5c518 70%, #ff8c00 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 16px;
            letter-spacing: -2px;
        }

        .hero h1 .highlight {
            background: linear-gradient(135deg, #f5c518, #ff8c00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: clamp(1.1rem, 2vw, 1.5rem);
            color: #b0b8c8;
            max-width: 700px;
            margin: 0 auto 32px;
            font-weight: 400;
        }

        .hero-stats {
            display: flex;
            justify-content: center;
            gap: 48px;
            flex-wrap: wrap;
            margin-top: 32px;
        }

        .hero-stats .stat {
            text-align: center;
        }
        .hero-stats .stat .number {
            font-size: 2.4rem;
            font-weight: 800;
            color: #f5c518;
            text-shadow: 0 0 40px rgba(245, 197, 24, 0.15);
        }
        .hero-stats .stat .label {
            font-size: 0.8rem;
            color: #8892a0;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .hero .btn-hero {
            display: inline-block;
            padding: 16px 48px;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1.1rem;
            background: #f5c518;
            color: #0a0e14;
            transition: all 0.3s ease;
            margin-top: 8px;
            border: none;
            cursor: pointer;
        }
        .hero .btn-hero:hover {
            background: #ffd700;
            transform: scale(1.04);
            box-shadow: 0 8px 32px rgba(245, 197, 24, 0.35);
        }

        /* ============================================
           DROPDOWN + CHART SECTION
           ============================================ */
        .dashboard-section {
            padding: 48px 0 72px;
            background: #0a0e14;
        }

        .dashboard-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 16px;
            margin-bottom: 32px;
            padding: 20px 24px;
            background: #11171f;
            border-radius: 16px;
            border: 1px solid #1e2733;
        }

        .dashboard-header h2 {
            font-size: 1.6rem;
            font-weight: 800;
        }
        .dashboard-header h2 span {
            color: #f5c518;
        }

        .dashboard-header .country-selector {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .dashboard-header .country-selector label {
            font-weight: 600;
            color: #8892a0;
            font-size: 0.9rem;
        }

        .dashboard-header .country-selector select {
            padding: 10px 20px;
            border-radius: 50px;
            border: 1px solid #1e2733;
            background: #1a212b;
            color: #e8edf3;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            outline: none;
            transition: all 0.3s ease;
            min-width: 180px;
            appearance: none;
            background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='8' viewBox='0 0 12 8'%3E%3Cpath d='M1 1l5 5 5-5' stroke='%23f5c518' stroke-width='1.5' fill='none' stroke-linecap='round'/%3E%3C/svg%3E");
            background-repeat: no-repeat;
            background-position: right 16px center;
        }

        .dashboard-header .country-selector select:hover {
            border-color: #f5c51866;
        }
        .dashboard-header .country-selector select:focus {
            border-color: #f5c518;
            box-shadow: 0 0 0 3px rgba(245, 197, 24, 0.15);
        }

        /* ============================================
           CHARTS GRID (Disney+ Cards)
           ============================================ */
        .charts-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 24px;
        }

        .chart-card {
            background: #11171f;
            border-radius: 20px;
            padding: 20px;
            border: 1px solid #1e2733;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .chart-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #f5c518, #ff8c00);
            opacity: 0;
            transition: opacity 0.4s ease;
        }

        .chart-card:hover {
            transform: translateY(-4px);
            border-color: #f5c51844;
            box-shadow: 0 12px 48px rgba(245, 197, 24, 0.06);
        }
        .chart-card:hover::before {
            opacity: 1;
        }

        .chart-card .chart-title {
            font-size: 1rem;
            font-weight: 700;
            margin-bottom: 12px;
            color: #e8edf3;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .chart-card .chart-container {
            width: 100%;
            height: 320px;
        }

        /* ============================================
           DOWNLOAD SECTION (Disney+ Style)
           ============================================ */
        .download-section {
            padding: 72px 0;
            background: #0f141c;
            border-top: 1px solid #1e2733;
            border-bottom: 1px solid #1e2733;
            margin-top: 48px;
        }

        .download-section h2 {
            font-size: 2rem;
            font-weight: 800;
            text-align: center;
            margin-bottom: 8px;
        }
        .download-section h2 span {
            color: #f5c518;
        }
        .download-section .sub {
            text-align: center;
            color: #8892a0;
            margin-bottom: 40px;
            font-size: 1.1rem;
        }

        .download-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 20px;
        }

        .download-card {
            background: #1a212b;
            border-radius: 16px;
            padding: 24px 20px;
            text-align: center;
            border: 1px solid #1e2733;
            transition: all 0.3s ease;
        }
        .download-card:hover {
            border-color: #f5c51866;
            transform: translateY(-4px);
        }
        .download-card .icon {
            font-size: 2.4rem;
            margin-bottom: 6px;
        }
        .download-card h4 {
            font-size: 0.95rem;
            font-weight: 600;
        }
        .download-card p {
            font-size: 0.8rem;
            color: #8892a0;
            margin: 4px 0 12px;
        }

        .btn-sm {
            display: inline-block;
            padding: 8px 20px;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 600;
            background: #f5c518;
            color: #0a0e14;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
        }
        .btn-sm:hover {
            background: #ffd700;
            color: #0a0e14;
            transform: scale(1.04);
        }

        /* ============================================
           FOOTER (Disney+ Style)
           ============================================ */
        .footer {
            background: #06090d;
            padding: 40px 0;
            text-align: center;
            border-top: 1px solid #1e2733;
        }
        .footer p {
            color: #5a6474;
            font-size: 0.9rem;
        }
        .footer .socials {
            margin-top: 12px;
            display: flex;
            justify-content: center;
            gap: 24px;
            flex-wrap: wrap;
        }
        .footer .socials a {
            color: #5a6474;
            font-size: 0.95rem;
            transition: color 0.3s ease;
            font-weight: 600;
        }
        .footer .socials a:hover {
            color: #f5c518;
        }

        /* ============================================
           RESPONSIVE
           ============================================ */
        @media (max-width: 1024px) {
            .charts-grid {
                grid-template-columns: 1fr;
            }
            .dashboard-header {
                flex-direction: column;
                text-align: center;
            }
            .dashboard-header .country-selector {
                width: 100%;
                justify-content: center;
            }
        }

        @media (max-width: 768px) {
            .navbar .container {
                flex-direction: column;
                align-items: center;
            }
            .navbar .nav-links {
                flex-wrap: wrap;
                justify-content: center;
                gap: 12px;
            }
            .hero h1 {
                font-size: 2.6rem;
            }
            .hero-stats {
                gap: 24px;
            }
            .hero-stats .stat .number {
                font-size: 1.6rem;
            }
            .chart-card .chart-container {
                height: 260px;
            }
            .dashboard-header h2 {
                font-size: 1.2rem;
            }
            .dashboard-header .country-selector select {
                min-width: 140px;
                padding: 8px 16px;
            }
            .download-grid {
                grid-template-columns: 1fr 1fr;
            }
        }

        @media (max-width: 480px) {
            .download-grid {
                grid-template-columns: 1fr;
            }
            .hero .btn-hero {
                width: 100%;
                text-align: center;
            }
            .navbar .nav-links {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>

    <!-- ============================================
         NAVBAR (Disney+ Hotstar)
         ============================================ -->
    <nav class="navbar">
        <div class="container">
            <div class="logo">
                <span>📊</span> Saransh<span>Econ</span>
                <span class="badge">MIT Portfolio</span>
            </div>
            <div class="nav-links">
                <a href="#dashboard">Dashboard</a>
                <a href="#downloads">Downloads</a>
                <a href="https://github.com/SSChitransh/Saransh-Economic-Intelligence-Platform" target="_blank">GitHub</a>
                <a href="#dashboard" class="btn-nav">🚀 Launch</a>
            </div>
        </div>
    </nav>

    <!-- ============================================
         HERO (Disney+ Hotstar)
         ============================================ -->
    <section class="hero">
        <div class="hero-content">
            <div class="hero-badge">🎓 MIT Maker Portfolio</div>
            <h1>
                Economic <br><span class="highlight">Intelligence</span> Platform
            </h1>
            <p>
                Interactive dashboard analyzing 24 years of macroeconomic data across
                <strong>9 countries</strong> (G7 + India &amp; China) with original research
                on education spending and poverty reduction.
            </p>
            <div class="hero-stats">
                <div class="stat"><div class="number">9</div><div class="label">Countries</div></div>
                <div class="stat"><div class="number">23</div><div class="label">Years</div></div>
                <div class="stat"><div class="number">7</div><div class="label">Indicators</div></div>
                <div class="stat"><div class="number">5+</div><div class="label">Research Pages</div></div>
            </div>
            <a href="#dashboard" class="btn-hero">📊 Explore Dashboard</a>
        </div>
    </section>

    <!-- ============================================
         DASHBOARD (Disney+ Hotstar)
         ============================================ -->
    <section class="dashboard-section" id="dashboard">
        <div class="container">

            <div class="dashboard-header">
                <h2>📊 <span>Interactive</span> Dashboard</h2>
                <div class="country-selector">
                    <label for="countrySelect">🌍 Select Country:</label>
                    <select id="countrySelect">
                        <option value="United States">🇺🇸 United States</option>
                        <option value="United Kingdom">🇬🇧 United Kingdom</option>
                        <option value="France">🇫🇷 France</option>
                        <option value="Germany">🇩🇪 Germany</option>
                        <option value="Japan">🇯🇵 Japan</option>
                        <option value="Italy">🇮🇹 Italy</option>
                        <option value="Canada">🇨🇦 Canada</option>
                        <option value="India" selected>🇮🇳 India</option>
                        <option value="China">🇨🇳 China</option>
                    </select>
                </div>
            </div>

            <div class="charts-grid" id="chartsGrid">
                <!-- Charts will be rendered by JavaScript -->
            </div>

        </div>
    </section>

    <!-- ============================================
         DOWNLOADS (Disney+ Hotstar)
         ============================================ -->
    <section class="download-section" id="downloads">
        <div class="container">
            <h2>📂 <span>Download</span> Files</h2>
            <p class="sub">Access the complete project — research, charts, presentation &amp; code</p>
            <div class="download-grid">
                <div class="download-card">
                    <div class="icon">📄</div>
                    <h4>Research Paper</h4>
                    <p>5–10 pages · TXT</p>
                    <a href="https://raw.githubusercontent.com/SSChitransh/Saransh-Economic-Intelligence-Platform/main/research/Saransh_Education_Poverty_Research_Paper.txt" download class="btn-sm">⬇ Download</a>
                </div>
                <div class="download-card">
                    <div class="icon">📊</div>
                    <h4>Scatter Plot</h4>
                    <p>PNG · 1920×1080</p>
                    <a href="https://raw.githubusercontent.com/SSChitransh/Saransh-Economic-Intelligence-Platform/main/charts/slide_scatter.png" download class="btn-sm">⬇ Download</a>
                </div>
                <div class="download-card">
                    <div class="icon">📈</div>
                    <h4>Poverty Trends</h4>
                    <p>PNG · 1920×1080</p>
                    <a href="https://raw.githubusercontent.com/SSChitransh/Saransh-Economic-Intelligence-Platform/main/charts/slide_poverty_trends.png" download class="btn-sm">⬇ Download</a>
                </div>
                <div class="download-card">
                    <div class="icon">🔥</div>
                    <h4>Heatmap</h4>
                    <p>PNG · 1920×1080</p>
                    <a href="https://raw.githubusercontent.com/SSChitransh/Saransh-Economic-Intelligence-Platform/main/charts/slide_heatmap.png" download class="btn-sm">⬇ Download</a>
                </div>
                <div class="download-card">
                    <div class="icon">📽️</div>
                    <h4>Presentation</h4>
                    <p>10 slides · PPTX</p>
                    <a href="https://raw.githubusercontent.com/SSChitransh/Saransh-Economic-Intelligence-Platform/main/presentation/Education_Research_Presentation.pptx" download class="btn-sm">⬇ Download</a>
                </div>
                <div class="download-card">
                    <div class="icon">💻</div>
                    <h4>Source Code</h4>
                    <p>Python · Colab</p>
                    <a href="https://raw.githubusercontent.com/SSChitransh/Saransh-Economic-Intelligence-Platform/main/code/Saransh_Dashboard_Script.ipynb" download class="btn-sm">⬇ Download</a>
                </div>
            </div>
        </div>
    </section>

    <!-- ============================================
         FOOTER (Disney+ Hotstar)
         ============================================ -->
    <footer class="footer">
        <div class="container">
            <p>Built by <strong>Saransh</strong> &bull; MIT Maker Portfolio 2026</p>
            <p style="font-size:0.85rem; color:#3a4455;">Data generated mathematically to mimic World Bank &amp; IMF trends.</p>
            <div class="socials">
                <a href="https://github.com/SSChitransh/Saransh-Economic-Intelligence-Platform" target="_blank">🐙 GitHub</a>
                <a href="#dashboard">📊 Dashboard</a>
                <a href="#downloads">📂 Downloads</a>
            </div>
        </div>
    </footer>

    <!-- ============================================
         JAVASCRIPT - CHART ENGINE
         ============================================ -->
    <script>
        // ============================================================
        // 1. DATA GENERATION
        // ============================================================
        const years = Array.from({ length: 24 }, (_, i) => 2000 + i);

        function generateSeries(base, growth, cycleAmp, cycleLen, noiseAmp) {
            const series = [];
            for (let i = 0; i < years.length; i++) {
                const trend = base + (growth * (i - 11) / 8);
                let cycle = 0;
                if (cycleLen !== 0) {
                    cycle = cycleAmp * Math.sin((i / cycleLen) * 2 * Math.PI);
                }
                const noise = (Math.random() - 0.5) * 2 * noiseAmp;
                let val = trend + cycle + noise;
                if ([280, 60, 62, 82, 127, 57, 30, 1000, 1200].includes(base) && val < 0) val = 0.1;
                if ([15, 10, 5, 1.5].includes(base) && val < 0) val = 0;
                series.push(Math.round(val * 100) / 100);
            }
            return series;
        }

        const countries = ["United States", "United Kingdom", "France", "Germany", "Japan", "Italy", "Canada", "India", "China"];

        const params = {
            "United States": { "GDP": [2.0, 0.15, 2.5, 10, 0.5], "Inflation": [2.5, 0.1, 1.5, 12, 0.5], "Poverty": [1.5, -0.4, 0.3, 15, 0.2], "Education": [5.0, 0.0, 0.2, 20, 0.1], "Unemployment": [5.0, -0.1, 1.5, 8, 0.5], "Population": [280, 2.5, 0, 0, 0.5], "Trade": [-3.0, 0.1, 0.5, 10, 0.3] },
            "United Kingdom": { "GDP": [2.0, 0.1, 2.0, 9, 0.5], "Inflation": [2.5, 0.0, 1.5, 11, 0.5], "Poverty": [1.5, -0.3, 0.2, 14, 0.2], "Education": [5.0, 0.0, 0.2, 18, 0.1], "Unemployment": [5.5, -0.1, 1.5, 7, 0.5], "Population": [60, 0.4, 0, 0, 0.1], "Trade": [-2.0, 0.0, 0.5, 9, 0.3] },
            "France": { "GDP": [1.5, 0.1, 1.8, 8, 0.4], "Inflation": [2.0, 0.0, 1.2, 10, 0.4], "Poverty": [1.5, -0.3, 0.2, 13, 0.2], "Education": [5.5, 0.0, 0.1, 20, 0.1], "Unemployment": [8.0, -0.1, 1.0, 6, 0.5], "Population": [62, 0.3, 0, 0, 0.1], "Trade": [-1.0, 0.1, 0.4, 8, 0.2] },
            "Germany": { "GDP": [1.5, 0.1, 2.0, 8, 0.4], "Inflation": [2.0, 0.0, 1.0, 10, 0.4], "Poverty": [1.0, -0.2, 0.2, 15, 0.1], "Education": [4.5, 0.0, 0.2, 18, 0.1], "Unemployment": [5.0, -0.2, 1.5, 8, 0.5], "Population": [82, 0.1, 0, 0, 0.1], "Trade": [5.0, -0.1, 1.0, 8, 0.4] },
            "Japan": { "GDP": [1.0, 0.0, 1.5, 10, 0.4], "Inflation": [0.5, 0.1, 0.8, 12, 0.3], "Poverty": [1.0, -0.2, 0.2, 16, 0.1], "Education": [3.5, 0.0, 0.1, 20, 0.1], "Unemployment": [3.0, 0.0, 0.8, 9, 0.3], "Population": [127, -0.2, 0, 0, 0.1], "Trade": [2.0, 0.0, 0.5, 10, 0.3] },
            "Italy": { "GDP": [1.0, 0.0, 1.5, 9, 0.4], "Inflation": [2.0, 0.0, 1.0, 11, 0.4], "Poverty": [1.5, -0.2, 0.2, 14, 0.2], "Education": [4.0, 0.0, 0.1, 18, 0.1], "Unemployment": [10.0, -0.2, 1.5, 7, 0.5], "Population": [57, -0.1, 0, 0, 0.1], "Trade": [1.0, 0.0, 0.4, 9, 0.2] },
            "Canada": { "GDP": [2.0, 0.1, 2.0, 9, 0.5], "Inflation": [2.0, 0.1, 1.2, 11, 0.4], "Poverty": [1.0, -0.3, 0.2, 15, 0.2], "Education": [5.5, 0.0, 0.2, 19, 0.1], "Unemployment": [6.0, -0.1, 1.5, 8, 0.5], "Population": [30, 0.4, 0, 0, 0.1], "Trade": [-2.0, 0.1, 0.5, 8, 0.3] },
            "India": { "GDP": [6.0, 0.3, 3.0, 10, 0.8], "Inflation": [5.0, 0.0, 2.0, 10, 0.6], "Poverty": [15.0, -2.0, 2.0, 12, 0.5], "Education": [4.0, 0.1, 0.2, 15, 0.1], "Unemployment": [6.0, 0.0, 1.0, 8, 0.5], "Population": [1000, 12, 0, 0, 1], "Trade": [-2.0, 0.0, 0.5, 10, 0.3] },
            "China": { "GDP": [8.0, -0.2, 3.0, 10, 0.8], "Inflation": [2.0, 0.0, 1.5, 12, 0.5], "Poverty": [5.0, -1.5, 1.0, 10, 0.3], "Education": [3.5, 0.0, 0.2, 18, 0.1], "Unemployment": [4.0, 0.0, 0.8, 9, 0.3], "Population": [1200, 8, 0, 0, 1], "Trade": [3.0, -0.1, 1.0, 9, 0.4] }
        };

        // Generate all data
        const data = {};
        for (const country of countries) {
            data[country] = {};
            for (const indicator of Object.keys(params[country])) {
                data[country][indicator] = generateSeries(...params[country][indicator]);
            }
        }

        const indicatorTitles = {
            "GDP": "📈 GDP Growth (Annual %)",
            "Inflation": "💸 Inflation (Consumer Prices %)",
            "Poverty": "📉 Poverty Headcount ($2.15/day)",
            "Education": "📚 Education Spending (% of GDP)",
            "Unemployment": "👷 Unemployment Rate (%)",
            "Population": "👨‍👩‍👧‍👦 Total Population (Millions)",
            "Trade": "🌐 Trade Balance (% of GDP)"
        };
        const indicatorKeys = Object.keys(indicatorTitles);

        // ============================================================
        // 2. CHART RENDERING ENGINE
        // ============================================================

        const colorMap = {
            "United States": "#f5c518",
            "United Kingdom": "#ff6b6b",
            "France": "#4ecdc4",
            "Germany": "#ff8c00",
            "Japan": "#ff6b9d",
            "Italy": "#45b7d1",
            "Canada": "#a29bfe",
            "India": "#ffd700",
            "China": "#ff4757"
        };

        function renderCharts(selectedCountry) {
            const grid = document.getElementById('chartsGrid');
            grid.innerHTML = '';

            for (const indicator of indicatorKeys) {
                const card = document.createElement('div');
                card.className = 'chart-card';

                const title = document.createElement('div');
                title.className = 'chart-title';
                title.textContent = indicatorTitles[indicator];

                const container = document.createElement('div');
                container.className = 'chart-container';
                container.id = `chart-${indicator}`;

                card.appendChild(title);
                card.appendChild(container);
                grid.appendChild(card);

                const trace = {
                    x: years,
                    y: data[selectedCountry][indicator],
                    mode: 'lines+markers',
                    type: 'scatter',
                    name: selectedCountry,
                    line: { color: colorMap[selectedCountry] || '#f5c518', width: 3 },
                    marker: { size: 6, color: colorMap[selectedCountry] || '#f5c518' }
                };

                const layout = {
                    margin: { l: 50, r: 20, t: 10, b: 40 },
                    paper_bgcolor: 'rgba(0,0,0,0)',
                    plot_bgcolor: 'rgba(0,0,0,0)',
                    font: { color: '#e8edf3', family: 'Inter, sans-serif' },
                    xaxis: {
                        gridcolor: 'rgba(255,255,255,0.05)',
                        tickfont: { color: '#8892a0' },
                        title: { text: 'Year', font: { color: '#8892a0' } }
                    },
                    yaxis: {
                        gridcolor: 'rgba(255,255,255,0.05)',
                        tickfont: { color: '#8892a0' },
                        title: { text: 'Value', font: { color: '#8892a0' } }
                    },
                    hovermode: 'x unified',
                    showlegend: false
                };

                Plotly.newPlot(container.id, [trace], layout, { responsive: true });
            }
        }

        // ============================================================
        // 3. DROPDOWN EVENT
        // ============================================================
        document.getElementById('countrySelect').addEventListener('change', function() {
            renderCharts(this.value);
        });

        // ============================================================
        // 4. INITIAL RENDER
        // ============================================================
        renderCharts('India');

        // ============================================================
        // 5. SMOOTH SCROLL FOR NAV LINKS
        // ============================================================
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });
    </script>

</body>
</html>