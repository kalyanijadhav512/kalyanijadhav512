
   <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kalyani Jadhav - Frontend Developer</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 25%, #16213e 50%, #0f3460 75%, #1a1a2e 100%);
            color: #e0e0e0;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* Animated Background Particles */
        .particles {
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
            width: 3px;
            height: 3px;
            background: rgba(0, 212, 255, 0.3);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0.3; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 1; }
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }

        .profile-container {
            position: relative;
            display: inline-block;
            margin-bottom: 30px;
        }

        .profile-image {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            background: linear-gradient(45deg, #00d4ff, #ff007f, #00ff88);
            padding: 4px;
            animation: rotate 10s linear infinite;
            position: relative;
        }

        .profile-image img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            background: #1a1a2e;
            border: 3px solid #1a1a2e;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .name {
            font-size: 3.5rem;
            font-weight: bold;
            background: linear-gradient(45deg, #00d4ff, #ff007f, #00ff88, #ffa500);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 3s ease-in-out infinite;
            margin-bottom: 15px;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .title {
            font-size: 1.8rem;
            color: #8892b0;
            margin-bottom: 20px;
            animation: fadeInUp 1s ease-out 0.5s both;
        }

        .wave {
            display: inline-block;
            animation: wave 2s ease-in-out infinite;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(20deg); }
            75% { transform: rotate(-20deg); }
        }

        /* Stats Section */
        .stats-section {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin: 40px 0;
            flex-wrap: wrap;
            animation: fadeInUp 1s ease-out 0.8s both;
        }

        .stat-card {
            background: rgba(30, 30, 46, 0.8);
            border: 1px solid rgba(0, 212, 255, 0.3);
            border-radius: 15px;
            padding: 20px 30px;
            text-align: center;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.1), transparent);
            transition: left 0.5s;
        }

        .stat-card:hover::before {
            left: 100%;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            border-color: #00d4ff;
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.2);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #00d4ff;
            display: block;
            margin-bottom: 5px;
        }

        .stat-label {
            color: #8892b0;
            font-size: 1rem;
        }

        /* About Section */
        .about-section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            animation: fadeInUp 1s ease-out 1s both;
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: start;
        }

        .about-content {
            background: rgba(30, 30, 46, 0.6);
            border-radius: 20px;
            padding: 30px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .section-title {
            font-size: 2rem;
            color: #00d4ff;
            margin-bottom: 20px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 60px;
            height: 3px;
            background: linear-gradient(90deg, #00d4ff, #ff007f);
            border-radius: 2px;
        }

        .about-list {
            list-style: none;
            padding: 0;
        }

        .about-list li {
            padding: 10px 0;
            color: #8892b0;
            display: flex;
            align-items: center;
        }

        .about-list li i {
            color: #00d4ff;
            margin-right: 15px;
            width: 20px;
        }

        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .skill-item {
            background: rgba(20, 20, 35, 0.8);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, #00d4ff, #ff007f, #00ff88);
            transform: translateX(-100%);
            transition: transform 0.5s ease;
        }

        .skill-item:hover::before {
            transform: translateX(0);
        }

        .skill-item:hover {
            transform: translateY(-10px);
            border-color: #00d4ff;
            box-shadow: 0 15px 30px rgba(0, 212, 255, 0.2);
        }

        .skill-icon {
            width: 50px;
            height: 50px;
            margin: 0 auto 10px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            background: linear-gradient(45deg, #00d4ff20, #ff007f20);
        }

        .skill-name {
            font-size: 0.9rem;
            color: #e0e0e0;
            font-weight: 500;
        }

        /* Social Links */
        .social-section {
            text-align: center;
            padding: 40px 20px;
            animation: fadeInUp 1s ease-out 1.2s both;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
        }

        .social-link {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: rgba(30, 30, 46, 0.8);
            border: 2px solid rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #8892b0;
            text-decoration: none;
            font-size: 24px;
            transition: all 0.3s ease;
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
            background: linear-gradient(45deg, #00d4ff, #ff007f);
            opacity: 0;
            transition: opacity 0.3s ease;
            z-index: -1;
        }

        .social-link:hover::before {
            opacity: 1;
        }

        .social-link:hover {
            color: white;
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 15px 30px rgba(0, 212, 255, 0.3);
        }

        /* GitHub Stats */
        .github-stats {
            max-width: 1000px;
            margin: 40px auto;
            padding: 0 20px;
            animation: fadeInUp 1s ease-out 1.4s both;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .stat-image {
            background: rgba(30, 30, 46, 0.6);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .stat-image:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.1);
        }

        .stat-image img {
            width: 100%;
            border-radius: 10px;
            filter: brightness(0.9) contrast(1.1);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Contact Section */
        .contact-section {
            text-align: center;
            padding: 40px 20px;
            animation: fadeInUp 1s ease-out 1.6s both;
        }

        .contact-btn {
            display: inline-block;
            padding: 15px 40px;
            background: linear-gradient(45deg, #00d4ff, #ff007f);
            color: white;
            text-decoration: none;
            border-radius: 30px;
            font-weight: bold;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .contact-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .contact-btn:hover::before {
            left: 100%;
        }

        .contact-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(0, 212, 255, 0.4);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .name {
                font-size: 2.5rem;
            }
            
            .title {
                font-size: 1.4rem;
            }
            
            .about-grid {
                grid-template-columns: 1fr;
            }
            
            .stats-section {
                gap: 20px;
            }
            
            .stat-card {
                padding: 15px 20px;
            }
            
            .social-links {
                gap: 20px;
            }
        }

        /* Scrollbar Styling */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #1a1a2e;
        }

        ::-webkit-scrollbar-thumb {
            background: linear-gradient(45deg, #00d4ff, #ff007f);
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <!-- Animated Particles Background -->
    <div class="particles" id="particles"></div>

    <!-- Header Section -->
    <header class="header">
        <div class="profile-container">
            <div class="profile-image">
                <img src="https://github.com/kalyanijadhav512.png" alt="Kalyani Jadhav" onerror="this.src='data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTgwIiBoZWlnaHQ9IjE4MCIgdmlld0JveD0iMCAwIDE4MCAxODAiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxjaXJjbGUgY3g9IjkwIiBjeT0iOTAiIHI9IjkwIiBmaWxsPSIjM
   
   
   
