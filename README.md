<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Akshay Jha - iOS Developer</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&display=swap');
        
        :root {
            --primary: #6366f1;
            --secondary: #8b5cf6;
            --accent: #06b6d4;
            --dark: #0f172a;
            --light: #f8fafc;
            --glass: rgba(255, 255, 255, 0.1);
            --glass-border: rgba(255, 255, 255, 0.2);
            --shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
            --gradient-1: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-2: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            --gradient-3: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            --gradient-4: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Space Grotesk', sans-serif;
            background: var(--dark);
            color: white;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(ellipse at top, #1e293b 0%, #0f172a 70%);
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 20%, rgba(99, 102, 241, 0.3) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(139, 92, 246, 0.3) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(6, 182, 212, 0.2) 0%, transparent 50%);
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            33% { transform: translate(30px, -30px) rotate(120deg); }
            66% { transform: translate(-20px, 20px) rotate(240deg); }
        }

        /* Floating Particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            background: rgba(99, 102, 241, 0.6);
            border-radius: 50%;
            animation: float-particles 15s infinite linear;
        }

        @keyframes float-particles {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
        }

        /* Glass Card */
        .glass-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 2rem;
            box-shadow: var(--shadow);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }

        .glass-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.8s ease;
        }

        .glass-card:hover::before {
            left: 100%;
        }

        .glass-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 35px 70px -12px rgba(99, 102, 241, 0.3);
        }

        /* Hero Section */
        .hero {
            padding: 4rem 3rem;
            text-align: center;
            position: relative;
            background: var(--gradient-1);
            margin-bottom: 2rem;
        }

        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.1'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
            opacity: 0.1;
            animation: slide 20s linear infinite;
        }

        @keyframes slide {
            0% { transform: translateX(0); }
            100% { transform: translateX(-60px); }
        }

        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: var(--gradient-3);
            margin: 0 auto 2rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            animation: pulse 2s ease-in-out infinite;
            box-shadow: 0 20px 40px rgba(99, 102, 241, 0.3);
            position: relative;
            z-index: 2;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .hero-title {
            font-size: clamp(2.5rem, 8vw, 4.5rem);
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #ffffff 0%, #e2e8f0 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            position: relative;
            z-index: 2;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            opacity: 0.9;
            margin-bottom: 2rem;
            font-weight: 300;
            position: relative;
            z-index: 2;
        }

        .typing-text {
            border-right: 3px solid #ffffff;
            animation: typing 4s steps(40) infinite, blink 1s infinite;
        }

        @keyframes typing {
            0%, 50% { width: 0; }
            100% { width: 100%; }
        }

        @keyframes blink {
            0%, 50% { border-color: transparent; }
            51%, 100% { border-color: #ffffff; }
        }

        /* Social Links */
        .social-grid {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 2rem;
            position: relative;
            z-index: 2;
        }

        .social-link {
            width: 60px;
            height: 60px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            color: white;
            font-size: 1.5rem;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient-3);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .social-link:hover::before {
            opacity: 1;
        }

        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 20px 40px rgba(99, 102, 241, 0.4);
        }

        .social-link span {
            position: relative;
            z-index: 1;
        }

        /* Content Section */
        .content {
            padding: 3rem;
            display: grid;
            gap: 3rem;
        }

        .section {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 2rem;
            background: var(--gradient-3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .section-title::before {
            content: '';
            width: 6px;
            height: 40px;
            background: var(--gradient-3);
            border-radius: 3px;
        }

        /* Focus Cards */
        .focus-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .focus-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 1.5rem;
            padding: 2.5rem;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }

        .focus-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: var(--gradient-3);
            transform: scaleX(0);
            transition: transform 0.4s ease;
        }

        .focus-card:hover::before {
            transform: scaleX(1);
        }

        .focus-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 50px rgba(99, 102, 241, 0.2);
            border-color: rgba(99, 102, 241, 0.3);
        }

        .focus-icon {
            font-size: 3rem;
            margin-bottom: 1.5rem;
            display: block;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .focus-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 1rem;
            color: #e2e8f0;
        }

        .focus-description {
            color: #94a3b8;
            line-height: 1.6;
        }

        /* Tech Stack */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 1.5rem;
        }

        .tech-item {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 1.5rem;
            padding: 2rem 1rem;
            text-align: center;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .tech-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(99, 102, 241, 0.1), transparent);
            transition: left 0.6s ease;
        }

        .tech-item:hover::before {
            left: 100%;
        }

        .tech-item:hover {
            transform: translateY(-8px) scale(1.05);
            border-color: rgba(99, 102, 241, 0.4);
            box-shadow: 0 20px 40px rgba(99, 102, 241, 0.2);
        }

        .tech-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            animation: rotate 10s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .tech-item:hover .tech-icon {
            animation-duration: 0.5s;
        }

        .tech-name {
            font-weight: 600;
            color: #e2e8f0;
            font-size: 0.9rem;
        }

        /* Stats Section */
        .stats-container {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 2rem;
            padding: 3rem;
            margin: 2rem 0;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
        }

        .stat-item {
            text-align: center;
            padding: 2rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 1.5rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.4s ease;
        }

        .stat-item:hover {
            transform: scale(1.05);
            background: rgba(99, 102, 241, 0.1);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 800;
            background: var(--gradient-4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
            animation: countUp 2s ease-out;
        }

        @keyframes countUp {
            from { transform: scale(0); }
            to { transform: scale(1); }
        }

        .stat-label {
            color: #94a3b8;
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Learning Section */
        .learning-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .learning-item {
            background: var(--gradient-1);
            padding: 2.5rem;
            border-radius: 2rem;
            text-align: center;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }

        .learning-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient-2);
            opacity: 0;
            transition: opacity 0.4s ease;
        }

        .learning-item:hover::before {
            opacity: 1;
        }

        .learning-item:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 30px 60px rgba(99, 102, 241, 0.3);
        }

        .learning-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            position: relative;
            z-index: 1;
            animation: float 3s ease-in-out infinite;
        }

        .learning-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 1rem;
            position: relative;
            z-index: 1;
        }

        .learning-desc {
            opacity: 0.9;
            position: relative;
            z-index: 1;
        }

        /* CTA Section */
        .cta {
            background: var(--gradient-1);
            padding: 4rem 3rem;
            text-align: center;
            border-radius: 2rem;
            margin-top: 3rem;
            position: relative;
            overflow: hidden;
        }

        .cta::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent 30%, rgba(255, 255, 255, 0.1) 50%, transparent 70%);
            animation: shine 3s linear infinite;
        }

        @keyframes shine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .cta-title {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 1rem;
            position: relative;
            z-index: 1;
        }

        .cta-subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
            margin-bottom: 2rem;
            position: relative;
            z-index: 1;
        }

        .cta-button {
            display: inline-block;
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            color: white;
            padding: 1rem 3rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            border: 2px solid rgba(255, 255, 255, 0.3);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            z-index: 1;
            overflow: hidden;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.2);
            transition: left 0.4s ease;
        }

        .cta-button:hover::before {
            left: 0;
        }

        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            border-color: rgba(255, 255, 255, 0.6);
        }

        /* Scroll Indicator */
        .scroll-indicator {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: rgba(255, 255, 255, 0.1);
            z-index: 1000;
        }

        .scroll-progress {
            height: 100%;
            background: var(--gradient-3);
            transition: width 0.3s ease;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 1rem;
            }
            
            .hero {
                padding: 3rem 2rem;
            }
            
            .content {
                padding: 2rem;
            }
            
            .focus-grid,
            .tech-grid,
            .learning-grid {
                grid-template-columns: 1fr;
            }
            
            .social-grid {
                flex-wrap: wrap;
                gap: 1rem;
            }
        }

        /* Accessibility */
        @media (prefers-reduced-motion: reduce) {
            *,
            *::before,
            *::after {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
            }
        }
    </style>
</head>
<body>
    <div class="bg-animation"></div>
    <div class="particles" id="particles"></div>
    
    <div class="scroll-indicator">
        <div class="scroll-progress" id="scrollProgress"></div>
    </div>

    <div class="container">
        <!-- Hero Section -->
        <div class="glass-card hero">
            <div class="hero-bg"></div>
            <div class="avatar">👋</div>
            <h1 class="hero-title">Akshay Jha</h1>
            <p class="hero-subtitle typing-text">iOS Developer & Tech Innovator</p>
            
            <div class="social-grid">
                <a href="https://youtube.com/AKBROS" class="social-link">
                    <span>🎥</span>
                </a>
                <a href="https://www.linkedin.com/in/akshay-jha-a95486238/" class="social-link">
                    <span>💼</span>
                </a>
                <a href="https://www.instagram.com/overlord.akshay/" class="social-link">
                    <span>📷</span>
                </a>
                <a href="https://akshay-alpha.vercel.app/" class="social-link">
                    <span>🌐</span>
                </a>
            </div>
        </div>

        <!-- Content -->
        <div class="glass-card">
            <div class="content">
                <!-- Current Focus -->
                <div class="section">
                    <h2 class="section-title">🎯 Current Focus</h2>
                    <div class="focus-grid">
                        <div class="focus-card">
                            <span class="focus-icon">🌱</span>
                            <h3 class="focus-title">iOS Development Mastery</h3>
                            <p class="focus-description">Deepening expertise in Swift, SwiftUI, and cutting-edge iOS architecture patterns to create exceptional mobile experiences that delight users.</p>
                        </div>
                        <div class="focus-card">
                            <span class="focus-icon">🚀</span>
                            <h3 class="focus-title">Innovation & Exploration</h3>
                            <p class="focus-description">Excited to explore emerging technologies, AI integration, and innovative solutions that push the boundaries of mobile app development.</p>
                        </div>
                        <div class="focus-card">
                            <span class="focus-icon">🏆</span>
                            <h3 class="focus-title">2024 Objectives</h3>
                            <p class="focus-description">Mastering Data Structures & Algorithms while advancing iOS development skills to build world-class, scalable applications.</p>
                        </div>
                    </div>
                </div>

                <!-- Tech Stack -->
                <div class="section">
                    <h2 class="section-title">🛠️ Technology Arsenal</h2>
                    <div class="tech-grid">
                        <div class="tech-item">
                            <div class="tech-icon">🔶</div>
                            <div class="tech-name">Swift</div>
                        </div>
                        <div class="tech-item">
                            <div class="tech-icon">📱</div>
                            <div class="tech-name">Xcode</div>
                        </div>
                        <div class="tech-item">
                            <div class="tech-icon">☕</div>
                            <div class="tech-name">Java</div>
                        </div>
                        <div class="tech-item">
                            <div class="tech-icon">📜</div>
                            <div class="tech-name">JavaScript</div>
                        </div>
                        <div class="tech-item">
                            <div class="tech-icon">🤖</div>
                            <div class="tech-name">Android</div>
                        </div>
                        <div class="tech-item">
                            <div class="tech-icon">🎨</div>
                            <div class="tech-name">Bootstrap</div>
                        </div>
                        <div class="tech-item">
                            <div class="tech-icon">🐍</div>
                            <div class="tech-name">Python</div>
                        </div>
                        <div class="tech-item">
                            <div class="tech-icon">🗄️</div>
                            <div class="tech-name">MySQL</div>
                        </div>
                        <div class="tech-item">
                            <div class="tech-icon">📂</div>
                            <div class="tech-name">Git</div>
                        </div>
                        <div class="tech-item">
                            <div class="tech-icon">⚡</div>
                            <div class="tech-name">C++</div>
                        </div>
                    </div>
                </div>

                <!-- GitHub Stats -->
                <div class="section">
                    <h2 class="section-title">📊 Impact Metrics</h2>
                    <div class="stats-container">
                        <div class="stats-grid">
                            <div class="stat-item">
                                <div class="stat-number">50+</div>
                                <div class="stat-label">Projects</div>
                            </div>
                            <div class="stat-item">
                                <div class="stat-number">1000+</div>
                                <div class="stat-label">Commits</div>
                            </div>
                            <div class="stat-item">
                                <div class="stat-number">10+</div>
                                <div class="stat-label">Languages</div>
                            </div>
                            <div class="stat-item">
                                <div class="stat-number">2024</div>
                                <div class="stat-label">Active Since</div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Learning Path -->
                <div class="section">
                    <h2 class="section-title">📈 Growth Journey</h2>
                    <div class="learning-grid">
                        <div class="learning-item">
                            <div class="learning-icon">📱</div>
                            <h3 class="learning-title">Advanced iOS Development</h3>
                            <p class="learning-desc">SwiftUI, Combine, Core Data & Advanced Architecture</p>
                        </div>
                        <div class="learning-item">
                            <div class="learning-icon">🧠</div>
                            <h3 class="learning-title">Algorithms & Data Structures</h3>
                            <p class="learning-desc">Optimizing Performance & Problem-Solving Skills</p>
                        </div>
                        <div class="learning-item">
                            <div class="learning-icon">🎨</div>
                            <h3 class="learning-title">UI/UX Excellence</h3>
                            <p class="learning-desc">Human-Centered Design & Interface Innovation</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- CTA Section -->
        <div class="glass-card cta">
            <h2 class="cta-title">Let's Create Magic Together! ✨</h2>
            <p class="cta-subtitle">Ready to build innovative solutions and push the boundaries of technology?</p>
            <a href="https://www.linkedin.com/in/akshay-jha-a95486238/" class="cta-button">Start Collaborating</a>
        </div>
    </div>

    <script>
        // Particle Animation
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 50;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.width = Math.random() * 4 + 1 + 'px';
                particle.style.height = particle.style.width;
                particle.style.animationDelay = Math.random() * 15 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                
                // Random colors for particles
                const colors = ['#6366f1', '#8b5cf6', '#06b6d4', '#10b981'];
                particle.style.background = colors[Math.floor(Math.random() * colors.length)];
                
                particlesContainer.appendChild(particle);
            }
        }

        // Scroll Progress Indicator
        function updateScrollProgress() {
            const scrollTop = window.pageYOffset;
            const docHeight = document.body.offsetHeight - window.innerHeight;
            const scrollPercent = (scrollTop / docHeight) * 100;
            document.getElementById('scrollProgress').style.width = scrollPercent + '%';
        }

        // Intersection Observer for Animations
        function initializeObserver() {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        
                        // Animate stats numbers
                        if (entry.target.classList.contains('stats-container')) {
                            animateStats();
                        }
                    }
                });
            }, {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            });

            // Observe all sections
            document.querySelectorAll('.section').forEach(section => {
                observer.observe(section);
            });
        }

        // Animate Statistics Numbers
        function animateStats() {
            const statNumbers = document.querySelectorAll('.stat-number');
            const targets = ['50+', '1000+', '10+', '2024'];
            
            statNumbers.forEach((stat, index) => {
                const target = targets[index];
                let current = 0;
                const isPlus = target.includes('+');
                const targetNum = parseInt(target);
                
                const increment = targetNum / 50;
                const timer = setInterval(() => {
                    current += increment;
                    if (current >= targetNum) {
                        stat.textContent = target;
                        clearInterval(timer);
                    } else {
                        stat.textContent = Math.floor(current) + (isPlus ? '+' : '');
                    }
                }, 40);
            });
        }

        // Typewriter Effect
        function typeWriter() {
            const text = "iOS Developer & Tech Innovator";
            const element = document.querySelector('.typing-text');
            let i = 0;
            
            element.textContent = '';
            element.style.borderRight = '3px solid #ffffff';
            
            function type() {
                if (i < text.length) {
                    element.textContent += text.charAt(i);
                    i++;
                    setTimeout(type, 100);
                } else {
                    // Restart after a pause
                    setTimeout(() => {
                        i = 0;
                        element.textContent = '';
                        type();
                    }, 3000);
                }
            }
            
            type();
        }

        // Mouse Trail Effect
        function createMouseTrail() {
            let mouseX = 0, mouseY = 0;
            let trailElements = [];
            
            // Create trail elements
            for (let i = 0; i < 10; i++) {
                const trail = document.createElement('div');
                trail.style.position = 'fixed';
                trail.style.width = '6px';
                trail.style.height = '6px';
                trail.style.borderRadius = '50%';
                trail.style.background = `rgba(99, 102, 241, ${0.8 - i * 0.08})`;
                trail.style.pointerEvents = 'none';
                trail.style.zIndex = '9999';
                trail.style.transition = 'all 0.1s ease';
                document.body.appendChild(trail);
                trailElements.push({ element: trail, x: 0, y: 0 });
            }
            
            document.addEventListener('mousemove', (e) => {
                mouseX = e.clientX;
                mouseY = e.clientY;
            });
            
            function animateTrail() {
                let x = mouseX;
                let y = mouseY;
                
                trailElements.forEach((trail, index) => {
                    trail.x += (x - trail.x) * 0.3;
                    trail.y += (y - trail.y) * 0.3;
                    trail.element.style.left = trail.x - 3 + 'px';
                    trail.element.style.top = trail.y - 3 + 'px';
                    x = trail.x;
                    y = trail.y;
                });
                
                requestAnimationFrame(animateTrail);
            }
            
            animateTrail();
        }

        // Enhanced Hover Effects
        function initializeHoverEffects() {
            // Tech items rotation on hover
            document.querySelectorAll('.tech-item').forEach(item => {
                item.addEventListener('mouseenter', () => {
                    const icon = item.querySelector('.tech-icon');
                    icon.style.animation = 'rotate 0.5s linear infinite';
                });
                
                item.addEventListener('mouseleave', () => {
                    const icon = item.querySelector('.tech-icon');
                    icon.style.animation = 'rotate 10s linear infinite';
                });
                
                // Click effect
                item.addEventListener('click', () => {
                    item.style.transform = 'scale(0.95)';
                    setTimeout(() => {
                        item.style.transform = '';
                    }, 150);
                });
            });

            // Focus cards enhanced hover
            document.querySelectorAll('.focus-card').forEach(card => {
                card.addEventListener('mouseenter', () => {
                    const icon = card.querySelector('.focus-icon');
                    icon.style.transform = 'scale(1.2) rotate(10deg)';
                });
                
                card.addEventListener('mouseleave', () => {
                    const icon = card.querySelector('.focus-icon');
                    icon.style.transform = 'scale(1) rotate(0deg)';
                });
            });

            // Learning items parallax effect
            document.querySelectorAll('.learning-item').forEach(item => {
                item.addEventListener('mousemove', (e) => {
                    const rect = item.getBoundingClientRect();
                    const x = e.clientX - rect.left;
                    const y = e.clientY - rect.top;
                    const centerX = rect.width / 2;
                    const centerY = rect.height / 2;
                    const rotateX = (y - centerY) / 10;
                    const rotateY = (centerX - x) / 10;
                    
                    item.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) translateY(-10px) scale(1.02)`;
                });
                
                item.addEventListener('mouseleave', () => {
                    item.style.transform = '';
                });
            });
        }

        // Magnetic Button Effect
        function initializeMagneticButtons() {
            document.querySelectorAll('.cta-button, .social-link').forEach(button => {
                button.addEventListener('mousemove', (e) => {
                    const rect = button.getBoundingClientRect();
                    const x = e.clientX - rect.left - rect.width / 2;
                    const y = e.clientY - rect.top - rect.height / 2;
                    
                    button.style.transform = `translate(${x * 0.2}px, ${y * 0.2}px)`;
                });
                
                button.addEventListener('mouseleave', () => {
                    button.style.transform = '';
                });
            });
        }

        // Smooth Scrolling
        function initializeSmoothScrolling() {
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth',
                            block: 'start'
                        });
                    }
                });
            });
        }

        // Performance optimized scroll listener
        let ticking = false;
        function handleScroll() {
            if (!ticking) {
                requestAnimationFrame(() => {
                    updateScrollProgress();
                    ticking = false;
                });
                ticking = true;
            }
        }

        // Initialize everything when DOM is ready
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
            initializeObserver();
            typeWriter();
            createMouseTrail();
            initializeHoverEffects();
            initializeMagneticButtons();
            initializeSmoothScrolling();
            
            // Add scroll listener
            window.addEventListener('scroll', handleScroll, { passive: true });
            
            // Add loading animation
            document.body.style.opacity = '0';
            setTimeout(() => {
                document.body.style.transition = 'opacity 1s ease';
                document.body.style.opacity = '1';
            }, 100);
        });

        // Preload optimization
        window.addEventListener('load', () => {
            // Remove any loading states
            document.body.classList.add('loaded');
        });

        // Keyboard navigation
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Tab') {
                document.body.classList.add('keyboard-navigation');
            }
        });

        document.addEventListener('mousedown', () => {
            document.body.classList.remove('keyboard-navigation');
        });
    </script>
</body>
</html>
