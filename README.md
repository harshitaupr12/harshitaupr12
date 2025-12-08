<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Harshita Upreti - Developer Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0a0e27 0%, #1a1a2e 100%);
            color: #fff;
            font-family: 'Courier New', monospace;
            overflow-x: hidden;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Animated Header */
        .header {
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 200%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 136, 0.1), transparent);
            animation: scan 3s infinite;
        }

        @keyframes scan {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .glitch {
            font-size: 3em;
            font-weight: bold;
            position: relative;
            animation: glitch 1s infinite;
        }

        @keyframes glitch {
            0%, 100% { text-shadow: 0 0 10px #00ff88, 0 0 20px #00ff88; }
            50% { text-shadow: 0 0 10px #ff0080, 0 0 20px #ff0080; }
        }

        .typing-text {
            font-size: 1.2em;
            color: #00ff88;
            margin-top: 20px;
            min-height: 30px;
        }

        /* DNA Helix Animation */
        .dna-container {
            position: relative;
            height: 200px;
            margin: 40px 0;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .dna-strand {
            position: absolute;
            width: 600px;
            height: 200px;
        }

        .dna-point {
            position: absolute;
            width: 15px;
            height: 15px;
            border-radius: 50%;
            animation: rotate 4s infinite linear;
        }

        .frontend { background: #00ff88; }
        .backend { background: #ff0080; }
        .aiml { background: #00d4ff; }

        @keyframes rotate {
            0% { transform: translate(0, 0) rotate(0deg); }
            100% { transform: translate(0, 0) rotate(360deg); }
        }

        /* Tech Stack Cards */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }

        .tech-card {
            background: rgba(255, 255, 255, 0.05);
            border: 2px solid transparent;
            border-radius: 15px;
            padding: 30px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .tech-card::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #00ff88, #00d4ff, #ff0080, #00ff88);
            border-radius: 15px;
            z-index: -1;
            opacity: 0;
            transition: opacity 0.3s;
            animation: borderRotate 3s linear infinite;
            background-size: 300% 300%;
        }

        @keyframes borderRotate {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .tech-card:hover::before {
            opacity: 1;
        }

        .tech-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 255, 136, 0.3);
        }

        .tech-icon {
            font-size: 2.5em;
            margin-bottom: 15px;
            display: inline-block;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .tech-title {
            font-size: 1.5em;
            color: #00ff88;
            margin-bottom: 15px;
        }

        .tech-items {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 15px;
        }

        .tech-tag {
            background: rgba(0, 255, 136, 0.1);
            border: 1px solid #00ff88;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.9em;
            transition: all 0.3s;
        }

        .tech-tag:hover {
            background: #00ff88;
            color: #0a0e27;
            transform: scale(1.1);
        }

        /* Project Cards */
        .project-card {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.1) 0%, rgba(0, 212, 255, 0.1) 100%);
            border-left: 4px solid #00ff88;
            padding: 30px;
            margin: 30px 0;
            border-radius: 10px;
            transition: all 0.3s;
            position: relative;
        }

        .project-card::after {
            content: '';
            position: absolute;
            right: 20px;
            top: 20px;
            width: 100px;
            height: 100px;
            background: radial-gradient(circle, rgba(0, 255, 136, 0.2), transparent);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.2); opacity: 0.8; }
        }

        .project-card:hover {
            transform: translateX(10px);
            border-left-width: 8px;
        }

        .project-title {
            font-size: 1.8em;
            color: #00ff88;
            margin-bottom: 10px;
        }

        .project-subtitle {
            color: #00d4ff;
            font-style: italic;
            margin-bottom: 15px;
        }

        .project-tech {
            color: #ff0080;
            margin: 15px 0;
            font-weight: bold;
        }

        .project-link {
            display: inline-block;
            margin-top: 15px;
            padding: 10px 25px;
            background: linear-gradient(45deg, #00ff88, #00d4ff);
            color: #0a0e27;
            text-decoration: none;
            border-radius: 25px;
            font-weight: bold;
            transition: all 0.3s;
        }

        .project-link:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 20px rgba(0, 255, 136, 0.5);
        }

        /* Stats Bar */
        .stats-container {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 20px;
            margin: 50px 0;
        }

        .stat-box {
            text-align: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            min-width: 150px;
            position: relative;
            overflow: hidden;
        }

        .stat-box::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 136, 0.3), transparent);
            transition: left 0.5s;
        }

        .stat-box:hover::before {
            left: 100%;
        }

        .stat-number {
            font-size: 2.5em;
            color: #00ff88;
            font-weight: bold;
            display: block;
        }

        .stat-label {
            color: #00d4ff;
            margin-top: 5px;
        }

        /* Experience Timeline */
        .timeline {
            position: relative;
            padding: 40px 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(180deg, #00ff88, #00d4ff, #ff0080);
            animation: timelineGlow 2s infinite;
        }

        @keyframes timelineGlow {
            0%, 100% { box-shadow: 0 0 10px #00ff88; }
            50% { box-shadow: 0 0 20px #00d4ff; }
        }

        .timeline-item {
            margin: 30px 0;
            position: relative;
        }

        .timeline-content {
            background: rgba(255, 255, 255, 0.05);
            padding: 25px;
            border-radius: 10px;
            width: 45%;
            position: relative;
        }

        .timeline-item:nth-child(odd) .timeline-content {
            margin-left: 55%;
        }

        .timeline-content::before {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background: #00ff88;
            border-radius: 50%;
            top: 25px;
            animation: dotPulse 1.5s infinite;
        }

        @keyframes dotPulse {
            0%, 100% { box-shadow: 0 0 0 0 rgba(0, 255, 136, 0.7); }
            50% { box-shadow: 0 0 0 15px rgba(0, 255, 136, 0); }
        }

        .timeline-item:nth-child(odd) .timeline-content::before {
            left: -35px;
        }

        .timeline-item:nth-child(even) .timeline-content::before {
            right: -35px;
        }

        .company-name {
            color: #00ff88;
            font-size: 1.5em;
            margin-bottom: 5px;
        }

        .role-name {
            color: #00d4ff;
            margin-bottom: 15px;
        }

        /* Contact Section */
        .contact-grid {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin: 50px 0;
        }

        .contact-btn {
            display: inline-block;
            padding: 15px 40px;
            background: rgba(255, 255, 255, 0.05);
            border: 2px solid #00ff88;
            color: #00ff88;
            text-decoration: none;
            border-radius: 30px;
            font-weight: bold;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .contact-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: #00ff88;
            transform: translate(-50%, -50%);
            transition: width 0.5s, height 0.5s;
            z-index: -1;
        }

        .contact-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .contact-btn:hover {
            color: #0a0e27;
            transform: scale(1.1);
        }

        .section-title {
            font-size: 2.5em;
            text-align: center;
            margin: 50px 0 30px;
            color: #00ff88;
            position: relative;
            display: inline-block;
            width: 100%;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, transparent, #00ff88, transparent);
        }

        /* Code Block */
        .code-block {
            background: rgba(0, 0, 0, 0.5);
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #00ff88;
            margin: 20px 0;
            overflow-x: auto;
        }

        .code-line {
            display: block;
            margin: 5px 0;
        }

        .keyword { color: #ff0080; }
        .string { color: #00ff88; }
        .number { color: #00d4ff; }
        .comment { color: #666; font-style: italic; }

        @media (max-width: 768px) {
            .glitch { font-size: 2em; }
            .tech-grid { grid-template-columns: 1fr; }
            .timeline::before { left: 20px; }
            .timeline-content { width: calc(100% - 60px); margin-left: 60px !important; }
            .timeline-item:nth-child(odd) .timeline-content::before,
            .timeline-item:nth-child(even) .timeline-content::before {
                left: -35px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="glitch">HARSHITA UPRETI</div>
            <div class="typing-text" id="typing"></div>
        </div>

        <!-- DNA Helix -->
        <div class="dna-container">
            <div class="dna-strand" id="dna"></div>
        </div>

        <!-- Stats -->
        <div class="stats-container">
            <div class="stat-box">
                <span class="stat-number">25%</span>
                <span class="stat-label">Performance Boost</span>
            </div>
            <div class="stat-box">
                <span class="stat-number">15+</span>
                <span class="stat-label">Components Built</span>
            </div>
            <div class="stat-box">
                <span class="stat-number">3</span>
                <span class="stat-label">Internships</span>
            </div>
            <div class="stat-box">
                <span class="stat-number">40%</span>
                <span class="stat-label">Dev Time Saved</span>
            </div>
        </div>

        <!-- Code Bio -->
        <div class="code-block">
            <span class="code-line"><span class="keyword">class</span> Developer {</span>
            <span class="code-line">    <span class="keyword">constructor</span>() {</span>
            <span class="code-line">        <span class="keyword">this</span>.name = <span class="string">"Harshita Upreti"</span>;</span>
            <span class="code-line">        <span class="keyword">this</span>.role = <span class="string">"SDE @ Phoenix Contact"</span>;</span>
            <span class="code-line">        <span class="keyword">this</span>.education = <span class="string">"B.Tech CSE (AI) | NIET '26"</span>;</span>
            <span class="code-line">        <span class="keyword">this</span>.specialization = [</span>
            <span class="code-line">            <span class="string">"Frontend Engineering"</span>,</span>
            <span class="code-line">            <span class="string">"Backend Development"</span>,</span>
            <span class="code-line">            <span class="string">"AI/ML Integration"</span></span>
            <span class="code-line">        ];</span>
            <span class="code-line">    }</span>
            <span class="code-line">    <span class="comment">// Building the future, one commit at a time</span></span>
            <span class="code-line">}</span>
        </div>

        <!-- Tech Stack -->
        <h2 class="section-title">⚡ TECH ARSENAL</h2>
        <div class="tech-grid">
            <div class="tech-card">
                <div class="tech-icon">⚛️</div>
                <div class="tech-title">Frontend Engineering</div>
                <p>Building blazing-fast, pixel-perfect user interfaces</p>
                <div class="tech-items">
                    <span class="tech-tag">React</span>
                    <span class="tech-tag">TypeScript</span>
                    <span class="tech-tag">JavaScript</span>
                    <span class="tech-tag">Redux Toolkit</span>
                    <span class="tech-tag">Tailwind CSS</span>
                </div>
            </div>
            <div class="tech-card">
                <div class="tech-icon">⚙️</div>
                <div class="tech-title">Backend Development</div>
                <p>Architecting scalable, secure server-side systems</p>
                <div class="tech-items">
                    <span class="tech-tag">Node.js</span>
                    <span class="tech-tag">Express.js</span>
                    <span class="tech-tag">Python</span>
                    <span class="tech-tag">Flask</span>
                    <span class="tech-tag">PostgreSQL</span>
                    <span class="tech-tag">MongoDB</span>
                </div>
            </div>
            <div class="tech-card">
                <div class="tech-icon">🤖</div>
                <div class="tech-title">AI/ML Integration</div>
                <p>Infusing intelligence into production applications</p>
                <div class="tech-items">
                    <span class="tech-tag">Scikit-learn</span>
                    <span class="tech-tag">NLP</span>
                    <span class="tech-tag">TensorFlow</span>
                    <span class="tech-tag">Predictive Models</span>
                    <span class="tech-tag">OpenAI API</span>
                </div>
            </div>
        </div>

        <!-- Experience Timeline -->
        <h2 class="section-title">🚀 MISSION LOG</h2>
        <div class="timeline">
            <div class="timeline-item">
                <div class="timeline-content">
                    <div class="company-name">Phoenix Contact</div>
                    <div class="role-name">SDE Intern | Jul 2025 - Present</div>
                    <p>✓ Optimized React rendering → 25% performance improvement</p>
                    <p>✓ Architected clean REST API integration layer</p>
                    <p>✓ Delivered features in Agile sprints with high quality</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-content">
                    <div class="company-name">WapVenture & Edyyo Digital</div>
                    <div class="role-name">Frontend Developer</div>
                    <p>✓ Built enterprise component library (15+ components)</p>
                    <p>✓ Reduced dev time by 40% through reusability</p>
                    <p>✓ Enhanced SEO across multiple products</p>
                </div>
            </div>
        </div>

        <!-- Projects -->
        <h2 class="section-title">💎 FLAGSHIP PROJECTS</h2>
        
        <div class="project-card">
            <div class="project-title">🧠 Resume Matcher</div>
            <div class="project-subtitle">AI-Powered Career Intelligence Engine</div>
            <p>NLP-driven system that analyzes resumes against job descriptions, extracts critical skills, and identifies gaps with surgical precision. Automated screening with 85%+ accuracy.</p>
            <div class="project-tech">Tech: Python • Streamlit • NLP • Keyword Extraction</div>
            <a href="https://github.com/harshitaupr12/resume-matcher" class="project-link">Explore →</a>
        </div>

        <div class="project-card">
            <div class="project-title">🤖 AI Blog Generator</div>
            <div class="project-subtitle">Intelligent Content Creation Engine</div>
            <p>Transform ideas into SEO-optimized blog posts using AI. Features auto-heading generation, keyword enrichment, and adaptive tone control. 10x faster content creation.</p>
            <div class="project-tech">Tech: Flask • OpenAI API • Python • NLP</div>
            <a href="https://github.com/harshitaupr12/ai-blog-generator" class="project-link">Explore →</a>
        </div>

        <div class="project-card">
            <div class="project-title">💸 Expense Tracker Dashboard</div>
            <div class="project-subtitle">ML-Enabled Financial Intelligence Platform</div>
            <p>Predictive analytics dashboard that learns spending habits and forecasts future expenses. Smart categorization with visual analytics for data-driven financial decisions.</p>
            <div class="project-tech">Tech: React • Flask • Scikit-learn • Chart.js</div>
            <a href="https://github.com/harshitaupr12/expense-tracker" class="project-link">Explore →</a>
        </div>

        <div class="project-card">
            <div class="project-title">🎓 Smart ERP System</div>
            <div class="project-subtitle">Enterprise Workflow Automation</div>
            <p>Role-based administrative system with automated workflows for educational institutions. Features attendance tracking, access control, and intelligent record management.</p>
            <div class="project-tech">Tech: PHP • MySQL • Bootstrap • MVC</div>
            <a href="https://github.com/harshitaupr12/erp-system" class="project-link">Explore →</a>
        </div>

        <!-- Contact -->
        <h2 class="section-title">📡 CONNECT</h2>
        <div class="contact-grid">
            <a href="https://linkedin.com/in/harshitaupr12" class="contact-btn">LinkedIn</a>
            <a href="mailto:harshitaupreti07@gmail.com" class="contact-btn">Email</a>
            <a href="https://my-portfolio-two-gamma-81.vercel.app" class="contact-btn">Portfolio</a>
            <a href="https://github.com/harshitaupr12?tab=repositories" class="contact-btn">All Projects</a>
        </div>

        <div style="text-align: center; margin: 60px 0 30px; color: #666;">
            <p>⭐ Star repos you find useful | 💡 Always open to collaborations</p>
            <p style="margin-top: 10px; color: #00ff88;">"Code is poetry written in logic"</p>
        </div>
    </div>

    <script>
        // Typing Animation
        const texts = [
            "SDE + Frontend + AI/ML Engineer",
            "Building Scalable Systems",
            "Optimizing Performance",
            "Integrating Intelligence",
            "Shipping Production Code"
        ];
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing');

        function type() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentText.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
            }

            const speed = isDeleting ? 50 : 100;
            setTimeout(type, speed);
        }

        type();

        // DNA Helix Animation
        const dnaContainer = document.getElementById('dna');
        const numPoints = 20;
        const radius = 200;
        const colors = ['frontend', 'backend', 'aiml'];

        for (let i = 0; i < numPoints; i++) {
            const point = document.createElement('div');
            point.className = `dna-point ${colors[i % 3]}`;
            const angle = (i / numPoints) * Math.PI * 4;
            const x = Math.cos(angle) * radius + 290;
            const y = Math.sin(angle) * 30 + 100;
            point.style.left = x + 'px';
            point.style.top = y + 'px';
            point.style.animationDelay = (i * 0.1) + 's';
            dnaContainer.appendChild(point);
        }

        // Animate DNA continuously
        let rotation = 0;
        setInterval(() => {
            rotation += 0.5;
            const points = dnaContainer.querySelectorAll('.dna-point');
            points.forEach((point, i) => {
                const angle = (i / numPoints) * Math.PI * 4 + (rotation * Math.PI / 180);
                const x = Math.cos(angle) * radius + 290;
                const y = Math.sin(angle) * 30 + 100;
                point.style.left = x + 'px';
                point.style.top = y + 'px';
            });
        }, 50);
    </script>
</body>
</html>
