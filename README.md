<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>First DigitalOcean Project - README</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            margin-top: 40px;
            margin-bottom: 40px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            animation: slideUp 0.8s ease-out;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }

        .project-title {
            font-size: clamp(2rem, 5vw, 3.5rem);
            font-weight: 700;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            animation: pulse 2s ease-in-out infinite alternate;
        }

        @keyframes pulse {
            from { opacity: 0.8; }
            to { opacity: 1; }
        }

        .subtitle {
            font-size: 1.2rem;
            color: #666;
            margin-bottom: 20px;
        }

        .badges {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 30px;
        }

        .badge {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
            text-decoration: none;
            transition: all 0.3s ease;
            animation: fadeInUp 0.8s ease-out forwards;
            opacity: 0;
        }

        .badge:hover {
            transform: translateY(-2px) scale(1.05);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .section {
            margin-bottom: 30px;
            padding: 25px;
            background: rgba(255, 255, 255, 0.7);
            border-radius: 12px;
            border-left: 4px solid #667eea;
            transition: all 0.3s ease;
            animation: fadeInLeft 0.8s ease-out forwards;
            opacity: 0;
        }

        .section:hover {
            transform: translateX(5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }

        .section h2 {
            color: #333;
            margin-bottom: 15px;
            font-size: 1.5rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .icon {
            width: 24px;
            height: 24px;
            opacity: 0.8;
        }

        .description {
            font-size: 1.1rem;
            margin-bottom: 20px;
            color: #555;
        }

        .tech-stack {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .tech-item {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            font-weight: 500;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-item:hover {
            transform: translateY(-3px) rotate(2deg);
            box-shadow: 0 10px 20px rgba(240, 147, 251, 0.3);
        }

        .cta-button {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 25px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            margin: 10px 5px;
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(102, 126, 234, 0.3);
        }

        .demo-section {
            text-align: center;
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            border-left-color: #fcb69f;
        }

        .footer {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 2px solid rgba(102, 126, 234, 0.2);
            color: #666;
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInLeft {
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .badge:nth-child(1) { animation-delay: 0.1s; }
        .badge:nth-child(2) { animation-delay: 0.2s; }
        .badge:nth-child(3) { animation-delay: 0.3s; }
        .badge:nth-child(4) { animation-delay: 0.4s; }

        .section:nth-child(1) { animation-delay: 0.2s; }
        .section:nth-child(2) { animation-delay: 0.4s; }
        .section:nth-child(3) { animation-delay: 0.6s; }
        .section:nth-child(4) { animation-delay: 0.8s; }
        .section:nth-child(5) { animation-delay: 1s; }

        @media (max-width: 768px) {
            .container {
                margin: 20px;
                padding: 20px;
            }
            
            .tech-stack {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
                gap: 10px;
            }
            
            .badges {
                flex-direction: column;
                align-items: center;
            }
        }

        .pulse-dot {
            display: inline-block;
            width: 8px;
            height: 8px;
            background: #4ade80;
            border-radius: 50%;
            margin-left: 10px;
            animation: pulseGreen 2s ease-in-out infinite;
        }

        @keyframes pulseGreen {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.5; transform: scale(1.2); }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1 class="project-title">🚀 First DO Project</h1>
            <p class="subtitle">My inaugural journey with DigitalOcean deployment</p>
            
            <div class="badges">
                <span class="badge">✨ Live</span>
                <span class="badge">🔧 In Development</span>
                <span class="badge">☁️ DigitalOcean</span>
                <span class="badge">🎯 Learning Project</span>
            </div>
        </div>

        <div class="section">
            <h2>
                <svg class="icon" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/>
                </svg>
                Project Overview
            </h2>
            <p class="description">
                Welcome to my first DigitalOcean deployment project! This represents my initial foray into cloud infrastructure, 
                combining modern development practices with scalable deployment strategies. Built with passion and a lot of learning curves.
            </p>
        </div>

        <div class="section">
            <h2>
                <svg class="icon" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h6a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6zM14 9a1 1 0 00-1 1v6a1 1 0 001 1h2a1 1 0 001-1v-6a1 1 0 00-1-1h-2z"/>
                </svg>
                Tech Stack
            </h2>
            <div class="tech-stack">
                <div class="tech-item" onclick="techClick(this)">Node.js</div>
                <div class="tech-item" onclick="techClick(this)">Express</div>
                <div class="tech-item" onclick="techClick(this)">DigitalOcean</div>
                <div class="tech-item" onclick="techClick(this)">Docker</div>
                <div class="tech-item" onclick="techClick(this)">Nginx</div>
                <div class="tech-item" onclick="techClick(this)">Git</div>
            </div>
        </div>

        <div class="section">
            <h2>
                <svg class="icon" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M3 3a1 1 0 000 2v8a2 2 0 002 2h2a2 2 0 002-2v-8a1 1 0 100-2H3z"/>
                    <path d="M11 3a1 1 0 100 2h4a2 2 0 012 2v8a2 2 0 01-2 2h-4a1 1 0 100-2H15V7H11V5z"/>
                </svg>
                Quick Start
            </h2>
            <div style="background: #1f2937; color: #e5e7eb; padding: 20px; border-radius: 8px; margin: 15px 0; font-family: 'Courier New', monospace;">
                <div># Clone the repository</div>
                <div style="color: #10b981;">git clone https://github.com/SyedAliHamzaBukhari/First-DO-Project.git</div>
                <br>
                <div># Install dependencies</div>
                <div style="color: #10b981;">npm install</div>
                <br>
                <div># Start development server</div>
                <div style="color: #10b981;">npm start</div>
            </div>
        </div>

        <div class="section demo-section">
            <h2>
                <svg class="icon" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M15 8a3 3 0 10-2.977-2.63l-4.94 2.47a3 3 0 100 4.319l4.94 2.47a3 3 0 10.895-1.789l-4.94-2.47a3.027 3.027 0 000-.74l4.94-2.47C13.456 7.68 14.19 8 15 8z"/>
                </svg>
                Live Demo
                <span class="pulse-dot"></span>
            </h2>
            <p style="margin-bottom: 20px;">Experience the deployed application in action!</p>
            <a href="#" class="cta-button" onclick="demoClick()">🌐 View Live Demo</a>
            <a href="#" class="cta-button" onclick="repoClick()">📂 View Source Code</a>
        </div>

        <div class="section">
            <h2>
                <svg class="icon" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z"/>
                </svg>
                What I Learned
            </h2>
            <p>This project taught me invaluable lessons about:</p>
            <ul style="margin-left: 20px; margin-top: 10px; color: #555;">
                <li>☁️ Cloud deployment fundamentals</li>
                <li>🔧 DevOps practices and CI/CD pipelines</li>
                <li>🚀 Scaling applications in production</li>
                <li>📊 Monitoring and logging best practices</li>
                <li>🔒 Security considerations for web applications</li>
            </ul>
        </div>

        <div class="footer">
            <p>Built with ❤️ by <strong>Syed Ali Hamza Bukhari</strong></p>
            <p style="margin-top: 10px; font-size: 0.9rem; opacity: 0.8;">
                🚀 Powered by DigitalOcean | 🔧 Made for learning
            </p>
        </div>
    </div>

    <script>
        function techClick(element) {
            element.style.background = 'linear-gradient(135deg, #667eea 0%, #764ba2 100%)';
            element.style.transform = 'translateY(-3px) rotate(-2deg) scale(1.05)';
            
            setTimeout(() => {
                element.style.background = 'linear-gradient(135deg, #f093fb 0%, #f5576c 100%)';
                element.style.transform = 'translateY(0) rotate(0deg) scale(1)';
            }, 300);
        }

        function demoClick() {
            alert('🚀 Demo would open here! Update the href with your live URL.');
        }

        function repoClick() {
            window.open('https://github.com/SyedAliHamzaBukhari/First-DO-Project', '_blank');
        }

        // Add floating animation to badges
        document.querySelectorAll('.badge').forEach((badge, index) => {
            setInterval(() => {
                badge.style.transform = `translateY(${Math.sin(Date.now() * 0.001 + index) * 2}px)`;
            }, 50);
        });

        // Add intersection observer for scroll animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0) translateX(0)';
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.section').forEach(section => {
            observer.observe(section);
        });
    </script>
</body>
</html>
