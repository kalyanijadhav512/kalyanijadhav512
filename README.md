
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kalyani Jadhav - Pro GitHub Profile</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'SF Pro Display', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            background: #0a0a0a;
            color: #ffffff;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* Dynamic Background with Multiple Layers */
        .bg-layer-1 {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 80%, rgba(120, 119, 198, 0.3) 0%, transparent 50%),
                        radial-gradient(circle at 80% 20%, rgba(255, 119, 198, 0.3) 0%, transparent 50%),
                        radial-gradient(circle at 40% 40%, rgba(120, 219, 255, 0.3) 0%, transparent 50%);
            animation: bgShift 20s ease-in-out infinite;
            z-index: -3;
        }

        .bg-layer-2 {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #0a0a0a 0%, #1a1a2e 25%, #16213e 50%, #0f3460 75%, #1a1a2e 100%);
            background-size: 400% 400%;
            animation: gradientFlow 15s ease infinite;
            z-index: -2;
        }

        @keyframes bgShift {
            0%, 100% { transform: scale(1) rotate(0deg); }
            50% { transform: scale(1.1) rotate(180deg); }
        }

        @keyframes gradientFlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Advanced Particle System */
        .particle-system {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            border-radius: 50%;
            background: linear-gradient(45deg, #00d4ff, #ff007f, #00ff88);
            animation: particleFloat 8s linear infinite;
        }

        .particle:nth-child(odd) {
            background: linear-gradient(45deg, #ff007f, #ffa500, #00d4ff);
        }

        @keyframes particleFloat {
            0% {
                transform: translateY(100vh) scale(0);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-10vh) scale(1);
                opacity: 0;
            }
        }

        /* Matrix Code Rain */
        .matrix-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            overflow: hidden;
        }

        .matrix-column {
            position: absolute;
            top: -100%;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            color: #00ff41;
            opacity: 0.7;
            animation: matrixFall linear infinite;
        }

        @keyframes matrixFall {
            0% {
                top: -100%;
                opacity: 0;
            }
            10% {
                opacity: 0.7;
            }
            90% {
                opacity: 0.7;
            }
            100% {
                top: 100%;
                opacity: 0;
            }
        }

        /* Main Container */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
            z-index: 1;
        }

        /* Header Section with Advanced Animations */
        .profile-header {
            text-align: center;
            margin-bottom: 80px;
            position: relative;
        }

        .avatar-wrapper {
            position: relative;
            display: inline-block;
            margin-bottom: 40px;
        }

        .avatar-container {
            width: 220px;
            height: 220px;
            position: relative;
            margin: 0 auto;
        }

        .avatar-ring {
            position: absolute;
            border-radius: 50%;
            border: 2px solid transparent;
            background: conic-gradient(from 0deg, #00d4ff, #ff007f, #00ff88, #ffa500, #8b5cf6, #00d4ff);
            background-size: 400% 400%;
            animation: ringRotate 4s linear infinite, ringPulse 2s ease-in-out infinite alternate;
        }

        .avatar-ring:nth-child(1) {
            width: 100%;
            height: 100%;
            animation-delay: 0s;
        }

        .avatar-ring:nth-child(2) {
            width: 110%;
            height: 110%;
            top: -5%;
            left: -5%;
            opacity: 0.7;
            animation-delay: -0.5s;
        }

        .avatar-ring:nth-child(3) {
            width: 120%;
            height: 120%;
            top: -10%;
            left: -10%;
            opacity: 0.4;
            animation-delay: -1s;
        }

        @keyframes ringRotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        @keyframes ringPulse {
            0% { box-shadow: 0 0 20px rgba(0, 212, 255, 0.5); }
            100% { box-shadow: 0 0 40px rgba(255, 0, 127, 0.8), 0 0 60px rgba(0, 255, 136, 0.3); }
        }

        .avatar-image {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            position: absolute;
            top: 10px;
            left: 10px;
            z-index: 5;
            object-fit: cover;
            background: #1a1a2e;
            border: 3px solid #0a0a0a;
        }

        /* Advanced Typography */
        .profile-title {
            font-size: 4rem;
            font-weight: 900;
            background: linear-gradient(45deg, #00d4ff, #ff007f, #00ff88, #ffa500, #8b5cf6);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: titleGlow 3s ease-in-out infinite, titleFloat 6s ease-in-out infinite;
            margin-bottom: 20px;
            position: relative;
        }

        @keyframes titleGlow {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @keyframes titleFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .typing-effect {
            font-size: 1.8rem;
            color: #8892b0;
            margin-bottom: 30px;
            min-height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .typing-text {
            border-right: 3px solid #00d4ff;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 50% { border-color: #00d4ff; }
            51%, 100% { border-color: transparent; }
        }

        /* Holographic Profile Views Badge */
        .profile-views {
            display: inline-block;
            background: rgba(0, 212, 255, 0.1);
            border: 1px solid rgba(0, 212, 255, 0.3);
            backdrop-filter: blur(10px);
            padding: 12px 24px;
            border-radius: 30px;
            font-weight: 600;
            position: relative;
            overflow: hidden;
            margin-bottom: 40px;
        }

        .profile-views::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(0, 212, 255, 0.3), transparent);
            animation: holographicScan 3s linear infinite;
        }

        @keyframes holographicScan {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Advanced Stats Grid */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 80px;
        }

        .stat-card {
            background: rgba(26, 26, 46, 0.4);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 40px 30px;
            text-align: center;
            position: relative;
            overflow: hidden;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            cursor: pointer;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.1), transparent);
            transition: left 0.6s ease;
        }

        .stat-card:hover::before {
            left: 100%;
        }

        .stat-card:hover {
            transform: translateY(-15px) scale(1.02);
            border-color: rgba(0, 212, 255, 0.5);
            box-shadow: 0 25px 50px rgba(0, 212, 255, 0.2),
                        0 0 0 1px rgba(0, 212, 255, 0.1);
        }

        .stat-icon {
            font-size: 4rem;
            margin-bottom: 20px;
            display: block;
            background: linear-gradient(45deg, #00d4ff, #ff007f);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: iconPulse 2s ease-in-out infinite;
        }

        @keyframes iconPulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 900;
            color: #ffffff;
            margin-bottom: 10px;
            display: block;
        }

        .stat-label {
            font-size: 1.2rem;
            color: #8892b0;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        /* Advanced About Section */
        .about-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            margin-bottom: 80px;
        }

        .about-card {
            background: rgba(26, 26, 46, 0.4);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 40px;
            position: relative;
            overflow: hidden;
        }

        .about-card::after {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: conic-gradient(from 0deg, #00d4ff, #ff007f, #00ff88, #ffa500, #00d4ff);
            border-radius: 20px;
            z-index: -1;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .about-card:hover::after {
            opacity: 0.7;
        }

        .section-title {
            font-size: 2.2rem;
            color: #ffffff;
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .section-title i {
            color: #00d4ff;
            animation: titleIconSpin 3s linear infinite;
        }

        @keyframes titleIconSpin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .activity-list {
            list-style: none;
        }

        .activity-item {
            padding: 20px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            gap: 20px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .activity-item:hover {
            padding-left: 20px;
            color: #00d4ff;
            transform: translateX(10px);
        }

        .activity-icon {
            font-size: 1.5rem;
            width: 40px;
            color: #00d4ff;
            animation: activityIconFloat 3s ease-in-out infinite;
        }

        @keyframes activityIconFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-5px); }
        }

        /* Advanced Skills Section */
        .skills-section {
            margin-bottom: 80px;
        }

        .skills-title {
            text-align: center;
            font-size: 3rem;
            color: #ffffff;
            margin-bottom: 50px;
            position: relative;
        }

        .skills-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #00d4ff, #ff007f);
            border-radius: 2px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .skill-card {
            background: rgba(26, 26, 46, 0.4);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 30px 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            cursor: pointer;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(0, 212, 255, 0.1), transparent);
            transform: translateY(-100%);
            transition: transform 0.6s ease;
        }

        .skill-card:hover::before {
            transform: translateY(0);
        }

        .skill-card:hover {
            transform: translateY(-15px) rotateY(5deg);
            border-color: rgba(0, 212, 255, 0.5);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.2);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 15px;
            display: block;
            transition: all 0.3s ease;
        }

        .skill-card:hover .skill-icon {
            transform: scale(1.2) rotateY(180deg);
        }

        .skill-name {
            font-size: 1rem;
            font-weight: 600;
            color: #ffffff;
        }

        /* GitHub Stats with Advanced Styling */
        .github-stats {
            margin-bottom: 80px;
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .github-stat-card {
            background: rgba(26, 26, 46, 0.4);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 25px;
            text-align: center;
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
        }

        .github-stat-card:hover {
            transform: scale(1.02);
            border-color: rgba(0, 212, 255, 0.5);
            box-shadow: 0 15px 30px rgba(0, 212, 255, 0.1);
        }

        .github-stat-card img {
            width: 100%;
            border-radius: 15px;
        }

        .trophies-container {
            text-align: center;
            background: rgba(26, 26, 46, 0.4);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 30px;
        }

        /* Social Links with Advanced Effects */
        .social-section {
            text-align: center;
            margin-bottom: 80px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 25px;
            flex-wrap: wrap;
        }

        .social-link {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: rgba(26, 26, 46, 0.4);
            backdrop-filter: blur(15px);
            border: 2px solid rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #8892b0;
            text-decoration: none;
            font-size: 1.8rem;
            position: relative;
            overflow: hidden;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: conic-gradient(from 0deg, #00d4ff, #ff007f, #00ff88, #ffa500, #00d4ff);
            opacity: 0;
            transition: opacity 0.3s ease;
            z-index: -1;
        }

        .social-link:hover::before {
            opacity: 1;
        }

        .social-link:hover {
            color: #ffffff;
            transform: translateY(-10px) scale(1.1);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.3);
        }

        /* Support Section */
        .support-section {
            text-align: center;
            padding: 50px;
            background: rgba(26, 26, 46, 0.4);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
        }

        .support-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(0, 212, 255, 0.1), transparent);
            animation: supportGlow 4s linear infinite;
        }

        @keyframes supportGlow {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .support-title {
            font-size: 2.5rem;
            color: #ffffff;
            margin-bottom: 20px;
            z-index: 1;
            relative;
        }

        .support-text {
            font-size: 1.2rem;
            color: #8892b0;
            z-index: 1;
            relative;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .profile-title {
                font-size: 2.8rem;
            }
            
            .about-section {
                grid-template-columns: 1fr;
            }
            
            .stats-container {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            }
            
            .avatar-container {
                width: 180px;
                height: 180px;
            }
            
            .avatar-image {
                width: 160px;
                height: 160px;
            }
        }

        /* Scroll Animations */
        .fade-in-up {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in-up.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Background Layers -->
    <div class="bg-layer-1"></div>
    <div class="bg-layer-2"></div>

    <!-- Particle System -->
    <div class="particle-system" id="particleSystem"></div>

    <!-- Matrix Rain -->
    <div class="matrix-container" id="matrixContainer"></div>

    <!-- Main Container -->
    <div class="container">
        <!-- Header Section -->
        <header class="profile-header fade-in-up">
            <div class="avatar-wrapper">
                <div class="avatar-container">
                    <div class="avatar-ring"></div>
                    <div class="avatar-ring"></div>
                    <div class="avatar-ring"></div>
                    <img src="https://github.com/kalyanijadhav512.png" alt="Kalyani Jadhav" class="avatar-image" onerror="this.src='data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgdmlld0JveD0iMCAwIDIwMCAyMDAiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxjaXJjbGUgY3g9IjEwMCIgY3k9IjEwMCIgcj0iMTAwIiBmaWxsPSIjMUExQTJFIi8+Cjx0ZXh0IHg9IjEwMCIgeT0iMTIwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iNjAiIGZpbGw9IiMwMEQ0RkYiIHRleHQtYW5jaG9yPSJtaWRkbGUiPks8L3RleHQ+Cjwvc3ZnPg=='">
                </div>
            </div>
            
            <h1 class="profile-title">Hi 👋, I'm Kalyani Jadhav</h1>
            
            <div class="typing-effect">
                <span class="typing-text" id="typingText"></span>
            </div>

            <div class="profile-views">
                <i class="fas fa-eye"></i>
                <span id="viewCounter">2,847</span> Profile Views
            </div>
        </header>

        <!-- Stats Section -->
        <section class="stats-grid fade-in-up">
            <div class="stat-card">
                <i class="stat-icon fas fa-code"></i>
                <span class="stat-number" data-count="25">0</span>
                <div class="stat-label">Projects</div>
            </div>
            <div class="stat-card">
                <i class="stat-icon fas fa-star"></i>
                <span class="stat-number" data-count="185">0</span>
                <div class="stat-label">Stars Earned</div>
            </div>
            <div class="stat-card">
                <i class="stat-icon fas fa-users"></i>
                <span class="stat-number" data-count="50">0</span>
                <div class="stat-label">Followers</div>
            </div>
            <div class="stat-card">
                <i class="stat-icon fas fa-fire"></i>
                <span class="stat-number" data-count="3">0</span>
                <div class="stat-label">Years Experience</div>
            </div>
        </section>

        <!-- About Section -->
        <section class="about-section fade-in-up">
            <div class="about-card">
                <h2 class="section-title">
                    <i class="fas fa-user-astronaut"></i>
                    About Me
                </h2>
                <ul class="activity-list">
                    <li class="activity-item">
                        <i class="activity-icon fas fa-rocket"></i>
                        <span>🔭 Currently working on <strong>portfolio</strong></span>
                    </li>
                    <li class="activity-item">
                        <i class="activity-icon fas fa-seedling"></i>
                        <span>🌱 Learning <strong>GitOps</strong></span>
                    </li>
                    <li class="activity-item">
                        <i class="activity-icon fas fa-gamepad"></i>
                        <span>👯 Looking to collaborate on <strong>game</strong></span>
                    </li>
                    <li class="activity-item">
                        <i class="activity-icon fas fa-hands-helping"></i>
                        <span>🤝 Need help with <strong>form application</strong></span>
                    </li>
                    <li class="activity-item">
                        <i class="activity-icon fas fa-comments"></i>
                        <span>💬 Ask me about <strong>git, github</strong></span>
                    </li>
                    <li class="activity-item">
