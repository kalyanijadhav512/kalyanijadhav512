
  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kalyani Jadhav - Animated GitHub Profile</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'SF Pro Display', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            background: #0d1117;
            color: #f0f6fc;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            background: linear-gradient(45deg, #0d1117, #161b22, #21262d);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Matrix Rain Effect */
        .matrix-rain {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            opacity: 0.1;
        }

        .matrix-column {
            position: absolute;
            top: -100px;
            font-family: 'Courier New', monospace;
            font-size: 18px;
            color: #00d4aa;
            animation: matrixFall linear infinite;
        }

        @keyframes matrixFall {
            to { transform: translateY(100vh); }
        }

        /* Main Container */
        .profile-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
        }

        /* Header Section */
        .profile-header {
            text-align: center;
            margin-bottom: 60px;
            animation: fadeInUp 1s ease-out;
        }

        .avatar-container {
            position: relative;
            display: inline-block;
            margin-bottom: 30px;
        }

        .avatar {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border: 4px solid transparent;
            background: linear-gradient(45deg, #f78166, #ffa726, #00d4aa, #4fc3f7);
            background-size: 400% 400%;
            animation: glowPulse 4s ease-in-out infinite, avatarRotate 20s linear infinite;
            position: relative;
            overflow: hidden;
        }

        .avatar img {
            width: calc(100% - 8px);
            height: calc(100% - 8px);
            border-radius: 50%;
            position: absolute;
            top: 4px;
            left: 4px;
            object-fit: cover;
            background: #21262d;
        }

        @keyframes glowPulse {
            0%, 100% { 
                background-position: 0% 50%;
                box-shadow: 0 0 30px rgba(0, 212, 170, 0.3);
            }
            50% { 
                background-position: 100% 50%;
                box-shadow: 0 0 50px rgba(255, 167, 38, 0.5);
            }
        }

        @keyframes avatarRotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .typing-container {
            height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
        }

        .profile-title {
            font-size: 3.5rem;
            font-weight: 800;
            background: linear-gradient(90deg, #f78166, #ffa726, #00d4aa, #4fc3f7, #8b5cf6);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: textGlow 3s ease-in-out infinite;
            text-align: center;
        }

        @keyframes textGlow {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .subtitle {
            font-size: 1.5rem;
            color: #8b949e;
            margin-top: 20px;
            position: relative;
            overflow: hidden;
        }

        .subtitle::after {
            content: '|';
            animation: blink 1s infinite;
            margin-left: 2px;
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }

        /* Stats Cards */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .stat-card {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid #30363d;
            border-radius: 12px;
            padding: 30px;
            text-align: center;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #00d4aa, transparent);
            animation: scan 3s linear infinite;
        }

        @keyframes scan {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .stat-card:hover {
            transform: translateY(-10px);
            border-color: #00d4aa;
            box-shadow: 0 20px 40px rgba(0, 212, 170, 0.2);
        }

        .stat-icon {
            font-size: 3rem;
            margin-bottom: 15px;
            background: linear-gradient(45deg, #f78166, #00d4aa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #f0f6fc;
            margin-bottom: 10px;
            counter-reset: number;
            animation: countUp 2s ease-out;
        }

        @keyframes countUp {
            from { transform: scale(0); }
            to { transform: scale(1); }
        }

        .stat-label {
            color: #8b949e;
            font-size: 1.1rem;
        }

        /* About Section */
        .about-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-bottom: 60px;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        .about-card {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid #30363d;
            border-radius: 12px;
            padding: 30px;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }

        .about-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(0, 212, 170, 0.1), transparent);
            animation: rotate 4s linear infinite;
            z-index: -1;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .section-title {
            font-size: 1.8rem;
            color: #00d4aa;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .activity-list {
            list-style: none;
        }

        .activity-item {
            padding: 15px 0;
            border-bottom: 1px solid #30363d;
            display: flex;
            align-items: center;
            gap: 15px;
            transition: all 0.3s ease;
        }

        .activity-item:hover {
            padding-left: 10px;
            color: #00d4aa;
        }

        .activity-icon {
            font-size: 1.2rem;
            width: 30px;
            color: #00d4aa;
        }

        /* Skills Section */
        .skills-section {
            animation: fadeInUp 1s ease-out 0.9s both;
            margin-bottom: 60px;
        }

        .skills-title {
            text-align: center;
            font-size: 2.5rem;
            color: #f0f6fc;
            margin-bottom: 40px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
            max-width: 1000px;
            margin: 0 auto;
        }

        .skill-card {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid #30363d;
            border-radius: 12px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(0, 212, 170, 0.1), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s ease;
        }

        .skill-card:hover::before {
            transform: translateX(100%);
        }

        .skill-card:hover {
            transform: translateY(-10px) scale(1.05);
            border-color: #00d4aa;
            box-shadow: 0 15px 30px rgba(0, 212, 170, 0.2);
        }

        .skill-icon {
            font-size: 2.5rem;
            margin-bottom: 10px;
            display: block;
        }

        .skill-name {
            font-size: 0.9rem;
            font-weight: 600;
            color: #f0f6fc;
        }

        /* GitHub Stats */
        .github-stats {
            animation: fadeInUp 1s ease-out 1.2s both;
            margin-bottom: 60px;
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .github-stat-card {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid #30363d;
            border-radius: 12px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .github-stat-card:hover {
            transform: scale(1.02);
            border-c
