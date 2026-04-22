<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JEONG CHANHO - Backend Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0d1117 0%, #1a0033 50%, #0d1117 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .container {
            width: 100%;
            max-width: 1000px;
            background: rgba(13, 17, 23, 0.8);
            border: 2px solid #30363d;
            border-radius: 12px;
            overflow: hidden;
            backdrop-filter: blur(10px);
            box-shadow: 0 20px 60px rgba(0, 255, 209, 0.15);
        }

        .header {
            height: 250px;
            background: linear-gradient(135deg, #1a0033 0%, #330066 50%, #00ffcc 100%);
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            width: 300px;
            height: 300px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            top: -100px;
            right: -100px;
            animation: float 6s ease-in-out infinite;
        }

        .header::after {
            content: '';
            position: absolute;
            width: 200px;
            height: 200px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 50%;
            bottom: -50px;
            left: -50px;
            animation: float 8s ease-in-out infinite reverse;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .header-content {
            position: relative;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
            z-index: 1;
        }

        .title {
            font-size: 3.5em;
            font-weight: 800;
            letter-spacing: 2px;
            margin-bottom: 10px;
            text-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
            animation: slideDown 0.8s ease-out;
        }

        .subtitle {
            font-size: 1.3em;
            font-weight: 300;
            letter-spacing: 1px;
            color: rgba(255, 255, 255, 0.9);
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
            animation: slideUp 0.8s ease-out 0.2s both;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
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

        .content {
            padding: 50px;
        }

        .section {
            margin-bottom: 40px;
        }

        .section-title {
            font-size: 1.5em;
            color: #00ffd1;
            margin-bottom: 20px;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section-title::before {
            content: '';
            display: inline-block;
            width: 4px;
            height: 24px;
            background: linear-gradient(180deg, #00ffd1 0%, #1a0033 100%);
            border-radius: 2px;
        }

        .about-text {
            color: #c9cacc;
            line-height: 1.8;
            font-size: 1.05em;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-bottom: 30px;
        }

        .tech-tag {
            background: linear-gradient(135deg, rgba(0, 255, 209, 0.1) 0%, rgba(51, 0, 102, 0.1) 100%);
            border: 1px solid #00ffd1;
            color: #00ffd1;
            padding: 12px 20px;
            border-radius: 8px;
            text-align: center;
            font-weight: 600;
            font-size: 0.95em;
            transition: all 0.3s ease;
            cursor: default;
        }

        .tech-tag:hover {
            background: linear-gradient(135deg, rgba(0, 255, 209, 0.2) 0%, rgba(51, 0, 102, 0.2) 100%);
            box-shadow: 0 0 20px rgba(0, 255, 209, 0.3);
            transform: translateY(-3px);
        }

        .tech-category {
            margin-bottom: 25px;
        }

        .tech-category-title {
            color: #58a6ff;
            font-size: 1.1em;
            font-weight: 600;
            margin-bottom: 12px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-box {
            background: rgba(30, 42, 61, 0.6);
            border: 1px solid #30363d;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-box:hover {
            border-color: #00ffd1;
            box-shadow: 0 0 20px rgba(0, 255, 209, 0.2);
        }

        .stat-number {
            font-size: 2.5em;
            font-weight: 800;
            color: #00ffd1;
            margin-bottom: 10px;
        }

        .stat-label {
            color: #8b949e;
            font-size: 0.95em;
        }

        .footer {
            background: rgba(30, 42, 61, 0.4);
            padding: 30px 50px;
            text-align: center;
            border-top: 1px solid #30363d;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .contact-btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 10px 20px;
            background: linear-gradient(135deg, rgba(0, 255, 209, 0.15) 0%, rgba(51, 0, 102, 0.15) 100%);
            border: 1px solid #00ffd1;
            color: #00ffd1;
            border-radius: 6px;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.95em;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .contact-btn:hover {
            background: linear-gradient(135deg, rgba(0, 255, 209, 0.25) 0%, rgba(51, 0, 102, 0.25) 100%);
            box-shadow: 0 0 20px rgba(0, 255, 209, 0.3);
            transform: translateY(-2px);
        }

        .footer-text {
            color: #8b949e;
            font-size: 0.95em;
        }

        .philosophy {
            background: rgba(51, 0, 102, 0.3);
            border-left: 4px solid #00ffd1;
            padding: 20px;
            border-radius: 6px;
            margin: 20px 0;
            color: #c9cacc;
            line-height: 1.8;
        }

        .philosophy strong {
            color: #00ffd1;
        }

        @media (max-width: 768px) {
            .title {
                font-size: 2.5em;
            }

            .subtitle {
                font-size: 1.1em;
            }

            .content {
                padding: 30px;
            }

            .footer {
                padding: 20px 30px;
            }

            .tech-grid {
                grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="header-content">
                <div>
                    <h1 class="title">JEONG CHANHO</h1>
                    <p class="subtitle">Back-End Developer | Problem Solver</p>
                </div>
            </div>
        </div>

        <div class="content">
            <div class="section">
                <h2 class="section-title">About Me</h2>
                <p class="about-text">
                    Backend engineer passionate about building scalable, secure, and efficient systems. 
                    With expertise in Spring Boot and modern web architecture, I focus on creating clean code 
                    and robust solutions that solve real-world problems.
                </p>
            </div>

            <div class="section">
                <h2 class="section-title">Tech Stack</h2>
                
                <div class="tech-category">
                    <div class="tech-category-title">Back-End</div>
                    <div class="tech-grid">
                        <div class="tech-tag">Java</div>
                        <div class="tech-tag">Spring Boot</div>
                        <div class="tech-tag">Spring Security</div>
                        <div class="tech-tag">JPA</div>
                        <div class="tech-tag">MyBatis</div>
                        <div class="tech-tag">OAuth2.0</div>
                        <div class="tech-tag">JWT</div>
                        <div class="tech-tag">FastAPI</div>
                        <div class="tech-tag">Python</div>
                        <div class="tech-tag">Redis</div>
                    </div>
                </div>

                <div class="tech-category">
                    <div class="tech-category-title">Database</div>
                    <div class="tech-grid">
                        <div class="tech-tag">MySQL</div>
                        <div class="tech-tag">PostgreSQL</div>
                        <div class="tech-tag">MariaDB</div>
                    </div>
                </div>

                <div class="tech-category">
                    <div class="tech-category-title">Infra & DevOps</div>
                    <div class="tech-grid">
                        <div class="tech-tag">AWS EC2</div>
                        <div class="tech-tag">AWS S3</div>
                        <div class="tech-tag">Docker</div>
                        <div class="tech-tag">Nginx</div>
                        <div class="tech-tag">Git</div>
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title">Philosophy</h2>
                <div class="philosophy">
                    <p><strong>"Write code that's not just functional, but maintainable. Solve problems with elegance and clarity."</strong></p>
                    <br>
                    <ul style="margin-left: 20px; color: #c9cacc;">
                        <li>🎓 Continuous learner with a passion for best practices</li>
                        <li>🔒 Security-first mindset in every implementation</li>
                        <li>⚡ Performance-conscious code optimization</li>
                        <li>🤝 Collaborative developer who values clear communication</li>
                    </ul>
                </div>
            </div>
        </div>

        <div class="footer">
            <div class="contact-links">
                <a href="mailto:jh940412@gmail.com" class="contact-btn">📧 Gmail</a>
                <a href="https://notion.so" class="contact-btn">📝 Notion</a>
                <a href="https://github.com/chanho8629-lgtm" class="contact-btn">💻 GitHub</a>
            </div>
            <p class="footer-text">Made with ❤️ by JEONG CHANHO | Always learning, always growing</p>
        </div>
    </div>
</body>
</html>
