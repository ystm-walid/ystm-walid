<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YSTM - Yousafzai Security Tranformation model</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #1a237e;
            --secondary: #4fc3f7;
            --accent: #ff6f00;
            --dark: #0d0d21;
            --light: #f5f8ff;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0d0d21 0%, #1a237e 100%);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
            background-attachment: fixed;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header & Navigation */
        header {
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            background: rgba(13, 13, 33, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.3);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .shield-icon {
            position: relative;
            width: 50px;
            height: 50px;
            background: var(--secondary);
            clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
            animation: pulse 3s infinite;
        }
        
        .shield-icon::before {
            content: '';
            position: absolute;
            top: 5px;
            left: 5px;
            right: 5px;
            bottom: 5px;
            background: var(--primary);
            clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
        }
        
        .logo-text {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(45deg, var(--secondary), #29b6f6, #4fc3f7);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
        }
        
        .nav-links a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            padding: 5px 0;
            transition: 0.3s;
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--secondary);
            transition: 0.3s;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            padding: 180px 0 100px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(79, 195, 247, 0.1) 0%, rgba(13, 13, 33, 0) 70%);
            z-index: -1;
        }
        
        .hero h1 {
            font-size: 4rem;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ffffff, var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: fadeIn 1.5s ease-out;
        }
        
        .hero p {
            font-size: 1.5rem;
            max-width: 800px;
            margin: 0 auto 40px;
            color: #bbdefb;
            animation: fadeIn 2s ease-out;
        }
        
        .author {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-top: 30px;
            animation: fadeIn 2.5s ease-out;
        }
        
        .author img {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            border: 3px solid var(--secondary);
            object-fit: cover;
        }
        
        .author span {
            font-weight: 500;
            font-size: 1.2rem;
        }
        
        /* Section Styling */
        section {
            padding: 100px 0;
            position: relative;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 70px;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.8rem;
            display: inline-block;
            background: linear-gradient(45deg, var(--secondary), #4fc3f7);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
            z-index: 2;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: var(--accent);
            border-radius: 2px;
        }
        
        /* Features Section */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(79, 195, 247, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }
        
        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--accent);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.3s;
        }
        
        .feature-card:hover::before {
            transform: scaleX(1);
        }
        
        .feature-icon {
            font-size: 3rem;
            color: var(--secondary);
            margin-bottom: 20px;
        }
        
        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }
        
        .feature-card p {
            color: #bbdefb;
            line-height: 1.6;
        }
        
        /* Architecture Section */
        .architecture {
            background: rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
        }
        
        .architecture::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><rect fill="rgba(79, 195, 247, 0.02)" width="100" height="100"/></svg>');
            background-size: 20px 20px;
            opacity: 0.3;
        }
        
        .blueprint {
            max-width: 800px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 30px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(79, 195, 247, 0.1);
        }
        
        .blueprint-header {
            text-align: center;
            margin-bottom: 40px;
        }
        
        .blueprint-header h3 {
            font-size: 2rem;
            margin-bottom: 10px;
            color: var(--secondary);
        }
        
        .pillars {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 50px;
        }
        
        .pillar {
            text-align: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 10px;
            transition: transform 0.3s;
        }
        
        .pillar:hover {
            transform: translateY(-5px);
        }
        
        .pillar h4 {
            font-size: 1.3rem;
            color: var(--secondary);
            margin-bottom: 10px;
        }
        
        .architecture-diagram {
            margin: 50px auto;
            max-width: 600px;
            position: relative;
        }
        
        .layer {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(79, 195, 247, 0.2);
            border-radius: 10px;
            padding: 25px;
            margin: 20px 0;
            position: relative;
            z-index: 2;
            backdrop-filter: blur(5px);
            transition: all 0.3s;
        }
        
        .layer:hover {
            background: rgba(79, 195, 247, 0.1);
            border-color: var(--secondary);
        }
        
        .layer h4 {
            color: var(--secondary);
            margin-bottom: 10px;
            font-size: 1.3rem;
        }
        
        .layer::before {
            content: '';
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 2px;
            height: 20px;
            background: var(--accent);
        }
        
        .layer:first-child::before {
            display: none;
        }
        
        /* Workflow Section */
        .workflow-steps {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            margin-top: 50px;
        }
        
        .step {
            flex: 1;
            min-width: 250px;
            max-width: 300px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(79, 195, 247, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .step-number {
            position: absolute;
            top: 15px;
            right: 15px;
            width: 40px;
            height: 40px;
            background: var(--accent);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        .step h3 {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: var(--secondary);
        }
        
        .step p {
            color: #bbdefb;
            line-height: 1.6;
        }
        
        /* Timeline Section */
        .timeline {
            max-width: 800px;
            margin: 80px auto 0;
            position: relative;
        }
        
        .timeline::before {
            content: '';
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 4px;
            height: 100%;
            background: var(--accent);
        }
        
        .timeline-item {
            margin-bottom: 50px;
            position: relative;
            width: 100%;
        }
        
        .timeline-item:nth-child(odd) {
            padding-right: calc(50% + 30px);
            text-align: right;
        }
        
        .timeline-item:nth-child(even) {
            padding-left: calc(50% + 30px);
        }
        
        .timeline-dot {
            position: absolute;
            top: 0;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: var(--accent);
            box-shadow: 0 0 10px rgba(255, 111, 0, 0.7);
        }
        
        .timeline-item:nth-child(odd) .timeline-dot {
            right: calc(50% - 10px);
        }
        
        .timeline-item:nth-child(even) .timeline-dot {
            left: calc(50% - 10px);
        }
        
        .timeline-content {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 25px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(79, 195, 247, 0.1);
        }
        
        .timeline-content h3 {
            color: var(--secondary);
            margin-bottom: 10px;
            font-size: 1.4rem;
        }
        
        /* Footer */
        footer {
            background: rgba(0, 0, 0, 0.3);
            padding: 50px 0 30px;
            text-align: center;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin-bottom: 30px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            color: var(--secondary);
            font-size: 1.5rem;
            transition: all 0.3s;
            text-decoration: none;
        }
        
        .social-links a:hover {
            background: var(--secondary);
            color: var(--dark);
            transform: translateY(-5px);
        }
        
        .copyright {
            color: #bbdefb;
            font-size: 0.9rem;
            margin-top: 20px;
        }
        
        /* Animations */
        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(79, 195, 247, 0.5); }
            70% { box-shadow: 0 0 0 15px rgba(79, 195, 247, 0); }
            100% { box-shadow: 0 0 0 0 rgba(79, 195, 247, 0); }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 3rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            .nav-links {
                display: none;
            }
            
            .timeline::before {
                left: 30px;
            }
            
            .timeline-item {
                padding-left: 70px !important;
                padding-right: 0 !important;
                text-align: left !important;
            }
            
            .timeline-item:nth-child(odd) .timeline-dot,
            .timeline-item:nth-child(even) .timeline-dot {
                left: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">
                    <div class="shield-icon"></div>
                    <div class="logo-text">YSTM</div>
                </div>
                <div class="nav-links">
                    <a href="#features">Features</a>
                    <a href="#architecture">Architecture</a>
                    <a href="#workflow">Workflow</a>
                    <a href="#timeline">Implementation</a>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Yousafzai Security Tranformation model</h1>
            <p>An innovative cybersecurity model developed by Waleed Yousafzai to protect digital environments using advanced threat detection, mitigation, and prevention strategies.</p>
            
            <div class="author">
                <div class="author-image">
                    <!-- Placeholder for author image -->
                    <div style="width: 60px; height: 60px; border-radius: 50%; background: linear-gradient(45deg, var(--secondary), var(--primary)); display: flex; align-items: center; justify-content: center; color: white; font-size: 24px; font-weight: bold;">WI</div>
                </div>
                <span>Walid Islam</span>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features">
        <div class="container">
            <div class="section-title">
                <h2>Core Features</h2>
            </div>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-search"></i>
                    </div>
                    <h3>Real-time Monitoring</h3>
                    <p>Continuous surveillance of digital environments to detect threats as they emerge.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-brain"></i>
                    </div>
                    <h3>AI-Powered Detection</h3>
                    <p>Advanced machine learning algorithms for identifying sophisticated threats.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h3>Layered Security</h3>
                    <p>Multiple defense layers to protect against various attack vectors.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-chart-bar"></i>
                    </div>
                    <h3>Incident Analysis</h3>
                    <p>Comprehensive reporting and analysis of security incidents.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Architecture Section -->
    <section id="architecture" class="architecture">
        <div class="container">
            <div class="section-title">
                <h2>Architecture Blueprint</h2>
            </div>
            
            <div class="blueprint">
                <div class="blueprint-header">
                    <h3>YSTM Framework</h3>
                    <p>An AI-driven cybersecurity framework for proactive, layered, and adaptive threat defense</p>
                </div>
                
                <h3 style="text-align: center; margin: 40px 0 20px; color: var(--secondary);">Core Pillars</h3>
                <div class="pillars">
                    <div class="pillar">
                        <h4>Detection</h4>
                        <p>Identify threats early</p>
                    </div>
                    <div class="pillar">
                        <h4>Mitigation</h4>
                        <p>Reduce immediate damage</p>
                    </div>
                    <div class="pillar">
                        <h4>Prevention</h4>
                        <p>Stop future attacks</p>
                    </div>
                    <div class="pillar">
                        <h4>Adaptation</h4>
                        <p>Learn from incidents & improve</p>
                    </div>
                </div>
                
                <div class="architecture-diagram">
                    <div class="layer">
                        <h4>Threat Intelligence Feed</h4>
                        <p>Collects threat intel from multiple sources</p>
                    </div>
                    
                    <div class="layer">
                        <h4>AI Threat Detection</h4>
                        <p>ML + Anomaly Scanning</p>
                    </div>
                    
                    <div class="layer">
                        <h4>Mitigation Engine</h4>
                        <p>Isolation, Blocking</p>
                    </div>
                    
                    <div class="layer">
                        <h4>Prevention Module</h4>
                        <p>Policy + Patching</p>
                    </div>
                    
                    <div class="layer">
                        <h4>Adaptive Learning AI</h4>
                        <p>Feedback Loop</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Workflow Section -->
    <section id="workflow">
        <div class="container">
            <div class="section-title">
                <h2>Security Workflow</h2>
            </div>
            
            <div class="workflow-steps">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3>Data Intake</h3>
                    <p>Collects threat intel from logs, sensors, network traffic</p>
                </div>
                
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Detection Layer</h3>
                    <p>AI models (supervised + anomaly detection) to flag threats</p>
                </div>
                
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Mitigation Layer</h3>
                    <p>Automatically isolates affected systems, blocks malicious IPs</p>
                </div>
                
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>Prevention Layer</h3>
                    <p>Enforces updated security policies, patches vulnerabilities</p>
                </div>
                
                <div class="step">
                    <div class="step-number">5</div>
                    <h3>Adaptive Learning</h3>
                    <p>AI retrains on past incidents to improve accuracy</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Implementation Timeline -->
    <section id="timeline">
        <div class="container">
            <div class="section-title">
                <h2>Implementation Plan</h2>
            </div>
            
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <h3>Phase 1: Detection & Logging</h3>
                        <p>Build detection system with comprehensive logging capabilities</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <h3>Phase 2: Mitigation & Prevention</h3>
                        <p>Add automated mitigation and prevention modules</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <h3>Phase 3: Adaptive Learning</h3>
                        <p>Integrate adaptive learning AI for continuous improvement</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <h3>Phase 4: Open-Source Release</h3>
                        <p>Publish open-source toolkit with comprehensive documentation</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="social-links">
                <a href="https://youtube.com/YSTM" target="_blank"><i class="fab fa-youtube"></i></a>
                <a href="https://github.com/walid-islam" target="_blank"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-linkedin"></i></a>
            </div>
            
            <div class="logo" style="justify-content: center; margin-bottom: 20px;">
                <div class="shield-icon" style="width: 40px; height: 40px;"></div>
                <div class="logo-text">YSTM</div>
            </div>
            
            <p>Yousafzai Security Tranformation model</p>
            <p class="copyright">© 2023 YSTM. Developed by Walid Islam. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Simple scroll animation for elements
        document.addEventListener('DOMContentLoaded', function() {
            // Add scroll event listener
            window.addEventListener('scroll', revealOnScroll);
            
            // Initially reveal elements in view
            revealOnScroll();
            
            function revealOnScroll() {
                const elements = document.querySelectorAll('.feature-card, .pillar, .layer, .step, .timeline-content');
                
                elements.forEach(element => {
                    const elementPosition = element.getBoundingClientRect().top;
                    const windowHeight = window.innerHeight;
                    
                    if (elementPosition < windowHeight - 50) {
                        element.style.opacity = "1";
                        element.style.transform = "translateY(0)";
                    }
                });
            }
            
            // Set initial styles for animated elements
            const animatedElements = document.querySelectorAll('.feature-card, .pillar, .layer, .step, .timeline-content');
            animatedElements.forEach(el => {
                el.style.opacity = "0";
                el.style.transform = "translateY(30px)";
                el.style.transition = "opacity 0.6s ease, transform 0.6s ease";
            });
        });
    </script>
</body>
</html>
