<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Harshita Upreti - Developer Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Courier New', monospace;
            background: linear-gradient(135deg, #0a0e27 0%, #1a1a2e 50%, #16213e 100%);
            color: #00ff88;
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
            overflow: hidden;
            z-index: 0;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: rgba(0, 255, 136, 0.5);
            animation: float 15s infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) translateX(0); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) translateX(50px); opacity: 0; }
        }

        /* Main Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
            z-index: 1;
        }

        /* Holographic Header */
        .header {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.1) 0%, rgba(0, 200, 255, 0.1) 100%);
            border: 2px solid #00ff88;
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 0 40px rgba(0, 255, 136, 0.3),
                        inset 0 0 40px rgba(0, 255, 136, 0.1);
            animation: glowPulse 3s ease-in-out infinite;
        }

        @keyframes glowPulse {
            0%, 100% { box-shadow: 0 0 40px rgba(0, 255, 136, 0.3), inset 0 0 40px rgba(0, 255, 136, 0.1); }
            50% { box-shadow: 0 0 60px rgba(0, 255, 136, 0.5), inset 0 0 60px rgba(0, 255, 136, 0.2); }
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(0, 255, 136, 0.1), transparent);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .header-content {
            position: relative;
            z-index: 1;
            text-align: center;
        }

        .status-bar {
            background: rgba(0, 0, 0, 0.5);
            border: 1px solid #00ff88;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 30px;
            font-size: 14px;
            backdrop-filter: blur(10px);
        }

        .status-bar span {
            display: inline-block;
            margin: 0 15px;
            animation: blink 2s infinite;
        }

        @keyframes blink {
            0%, 50%, 100% { opacity: 1; }
            25%, 75% { opacity: 0.5; }
        }

        h1 {
            font-size: 48px;
            margin: 20px 0;
            text-shadow: 0 0 20px rgba(0, 255, 136, 0.8);
            animation: textGlow 2s ease-in-out infinite;
        }

        @keyframes textGlow {
            0%, 100% { text-shadow: 0 0 20px rgba(0, 255, 136, 0.8); }
            50% { text-shadow: 0 0 40px rgba(0, 255, 136, 1); }
        }

        .role-tags {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .tag {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.2), rgba(0, 200, 255, 0.2));
            border: 1px solid #00ff88;
            padding: 10px 20px;
            border-radius: 25px;
            font-size: 14px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tag:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.5);
        }

        /* Glass Cards */
        .cards-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .glass-card {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0.02));
            border: 1px solid rgba(0, 255, 136, 0.3);
            border-radius: 20px;
            padding: 30px;
            backdrop-filter: blur(20px);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            transition: all 0.3s ease;
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
            background: linear-gradient(90deg, transparent, rgba(0, 255, 136, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .glass-card:hover::before {
            left: 100%;
        }

        .glass-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 50px rgba(0, 255, 136, 0.4);
            border-color: #00ff88;
        }

        .card-title {
            font-size: 24px;
            margin-bottom: 20px;
            color: #00ccff;
            text-shadow: 0 0 10px rgba(0, 204, 255, 0.8);
        }

        .code-block {
            background: rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(0, 255, 136, 0.3);
            border-radius: 10px;
            padding: 20px;
            font-size: 13px;
            line-height: 1.8;
            overflow-x: auto;
            margin: 15px 0;
        }

        /* Social Links with Lamination Effect */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 40px 0;
            flex-wrap: wrap;
        }

        .social-btn {
            position: relative;
            padding: 15px 40px;
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.2), rgba(0, 200, 255, 0.2));
            border: 2px solid #00ff88;
            border-radius: 50px;
            color: #00ff88;
            text-decoration: none;
            font-size: 16px;
            font-weight: bold;
            transition: all 0.3s ease;
            overflow: hidden;
            box-shadow: 0 0 20px rgba(0, 255, 136, 0.3);
        }

        .social-btn::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transform: rotate(45deg);
            transition: all 0.5s ease;
        }

        .social-btn:hover::before {
            left: 100%;
        }

        .social-btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 40px rgba(0, 255, 136, 0.6);
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.3), rgba(0, 200, 255, 0.3));
        }

        /* Metrics Dashboard */
        .metrics {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .metric {
            background: rgba(0, 0, 0, 0.5);
            border: 1px solid #00ff88;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .metric::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, #00ff88, #00ccff);
            animation: loadBar 2s ease-in-out infinite;
        }

        @keyframes loadBar {
            0%, 100% { transform: translateX(-100%); }
            50% { transform: translateX(100%); }
        }

        .metric-value {
            font-size: 32px;
            font-weight: bold;
            color: #00ccff;
            text-shadow: 0 0 15px rgba(0, 204, 255, 0.8);
        }

        .metric-label {
            font-size: 14px;
            margin-top: 10px;
            opacity: 0.8;
        }

        /* Footer with Wave Animation */
        .footer {
            text-align: center;
            margin-top: 60px;
            padding: 30px;
            position: relative;
        }

        .wave {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 100px;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 100"><path d="M0,50 Q300,0 600,50 T1200,50 L1200,100 L0,100 Z" fill="rgba(0,255,136,0.1)"/></svg>');
            animation: wave 3s linear infinite;
        }

        @keyframes wave {
            0% { background-position: 0 0; }
            100% { background-position: 1200px 0; }
        }

        .cta {
            font-size: 20px;
            margin-bottom: 20px;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            h1 { font-size: 32px; }
            .cards-container { grid-template-columns: 1fr; }
            .social-links { flex-direction: column; align-items: center; }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>
    
    <div class="container">
        <div class="header">
            <div class="header-content">
                <div class="status-bar">
                    <span>⚡ SYSTEM ONLINE</span> | 
                    <span>⟳ LATENCY: 0ms</span> | 
                    <span>∞ UPTIME: 99.99%</span>
                </div>
                
                <h1>HARSHITA UPRETI</h1>
                
                <div class="role-tags">
                    <div class="tag">💻 Software Engineer</div>
                    <div class="tag">⚛️ React Architect</div>
                    <div class="tag">🚀 System Optimizer</div>
                    <div class="tag">✨ Innovation Driver</div>
                </div>
            </div>
        </div>

        <div class="social-links">
            <a href="https://linkedin.com/in/harshitaupr12" class="social-btn">
                <span>🔗 LinkedIn</span>
            </a>
            <a href="mailto:harshitaupreti07@gmail.com" class="social-btn">
                <span>📧 Email</span>
            </a>
            <a href="https://my-portfolio-two-gamma-81.vercel.app" class="social-btn">
                <span>🌐 Portfolio</span>
            </a>
        </div>

        <div class="cards-container">
            <div class="glass-card">
                <div class="card-title">// DEVELOPER PROFILE</div>
                <div class="code-block">
const developer = {<br>
&nbsp;&nbsp;name: "Harshita Upreti",<br>
&nbsp;&nbsp;expertise: [<br>
&nbsp;&nbsp;&nbsp;&nbsp;"Frontend Architecture",<br>
&nbsp;&nbsp;&nbsp;&nbsp;"Performance Optimization",<br>
&nbsp;&nbsp;&nbsp;&nbsp;"System Design"<br>
&nbsp;&nbsp;],<br>
&nbsp;&nbsp;philosophy: "Build elegant,<br>
&nbsp;&nbsp;&nbsp;&nbsp;scalable solutions",<br>
&nbsp;&nbsp;status: "∞ INNOVATING"<br>
};
                </div>
            </div>

            <div class="glass-card">
                <div class="card-title">// CORE SYSTEMS</div>
                <div class="metrics">
                    <div class="metric">
                        <div class="metric-value">∞</div>
                        <div class="metric-label">CREATIVITY</div>
                    </div>
                    <div class="metric">
                        <div class="metric-value">9.8</div>
                        <div class="metric-label">INNOVATION</div>
                    </div>
                </div>
                <div class="code-block">
class Engineer:<br>
&nbsp;&nbsp;def __init__(self):<br>
&nbsp;&nbsp;&nbsp;&nbsp;self.passion = True<br>
&nbsp;&nbsp;&nbsp;&nbsp;self.learning = "continuous"<br>
&nbsp;&nbsp;&nbsp;&nbsp;self.impact = "maximum"
                </div>
            </div>

            <div class="glass-card">
                <div class="card-title">// CURRENT MISSION</div>
                <div class="code-block">
>>> mission = "Transform ideas<br>
&nbsp;&nbsp;&nbsp;&nbsp;into reality"<br>
>>> status = "ACTIVE"<br>
>>> commitment = "BUILDING<br>
&nbsp;&nbsp;&nbsp;&nbsp;THE FUTURE"<br><br>
[✓] Code Quality: EXCEPTIONAL<br>
[✓] Innovation: BLEEDING_EDGE<br>
[✓] Collaboration: SYNCHRONOUS<br>
[⟳] Growth: EXPONENTIAL
                </div>
            </div>
        </div>

        <div class="footer">
            <div class="wave"></div>
            <div class="cta">
                >> Ready to create something extraordinary? Let's connect. <<
            </div>
            <div style="font-size: 12px; opacity: 0.6; margin-top: 20px;">
                🌟 Crafted with passion | © 2024 Harshita Upreti
            </div>
        </div>
    </div>

    <script>
        // Generate animated particles
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 15 + 's';
            particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
            particlesContainer.appendChild(particle);
        }
    </script>
</body>
</html>
