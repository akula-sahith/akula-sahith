<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sahith Akula - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header Section with Animation */
        .header {
            text-align: center;
            padding: 60px 20px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            margin-bottom: 40px;
            animation: fadeInDown 1s ease-out;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 5px solid #fff;
            margin-bottom: 20px;
            animation: float 3s ease-in-out infinite;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .name {
            font-size: 3em;
            font-weight: bold;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #fff, #a8edea);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient 3s ease infinite;
        }

        .title {
            font-size: 1.5em;
            margin-bottom: 20px;
            animation: fadeIn 1.5s ease-out;
        }

        .typing-animation {
            font-size: 1.2em;
            color: #a8edea;
            min-height: 30px;
            animation: blink 1s step-end infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }

        .contact-info {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 30px;
        }

        .contact-badge {
            background: rgba(255, 255, 255, 0.2);
            padding: 10px 20px;
            border-radius: 25px;
            backdrop-filter: blur(5px);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .contact-badge:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }

        /* Section Styling */
        .section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease-out;
            transition: all 0.3s ease;
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
        }

        .section-title {
            font-size: 2.5em;
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .section-title::before {
            content: '';
            width: 50px;
            height: 5px;
            background: linear-gradient(90deg, #a8edea, #fed6e3);
            border-radius: 5px;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { width: 50px; }
            50% { width: 80px; }
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .skill-category {
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 15px;
            transition: all 0.3s ease;
        }

        .skill-category:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: scale(1.05);
        }

        .skill-category h3 {
            margin-bottom: 15px;
            color: #a8edea;
        }

        .skill-badge {
            display: inline-block;
            background: rgba(255, 255, 255, 0.2);
            padding: 8px 15px;
            border-radius: 20px;
            margin: 5px;
            font-size: 0.9em;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-badge:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-3px);
        }

        /* Projects */
        .project-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 20px;
            border-left: 5px solid #a8edea;
            transition: all 0.3s ease;
            animation: slideInLeft 0.8s ease-out;
        }

        .project-card:hover {
            background: rgba(255, 255, 255, 0.15);
            transform: translateX(10px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .project-title {
            font-size: 1.8em;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .project-description {
            line-height: 1.8;
            margin-bottom: 15px;
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 15px;
        }

        .tech-tag {
            background: linear-gradient(45deg, #667eea, #764ba2);
            padding: 5px 15px;
            border-radius: 15px;
            font-size: 0.85em;
            animation: fadeIn 1s ease-out;
        }

        /* Achievements */
        .achievements-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .achievement-card {
            background: rgba(255, 255, 255, 0.15);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            animation: bounceIn 1s ease-out;
        }

        .achievement-card:hover {
            transform: scale(1.1) rotate(2deg);
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
        }

        .medal {
            font-size: 3em;
            margin-bottom: 10px;
            animation: swing 2s ease-in-out infinite;
        }

        @keyframes swing {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(10deg); }
            75% { transform: rotate(-10deg); }
        }

        /* Education Timeline */
        .timeline {
            position: relative;
            padding-left: 40px;
            margin-top: 30px;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            height: 100%;
            width: 3px;
            background: linear-gradient(180deg, #a8edea, #fed6e3);
        }

        .timeline-item {
            position: relative;
            margin-bottom: 30px;
            animation: slideInRight 0.8s ease-out;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -47px;
            top: 0;
            width: 15px;
            height: 15px;
            border-radius: 50%;
            background: #a8edea;
            border: 3px solid #fff;
            animation: pulse-dot 2s ease-in-out infinite;
        }

        @keyframes pulse-dot {
            0%, 100% { box-shadow: 0 0 0 0 rgba(168, 237, 234, 0.7); }
            50% { box-shadow: 0 0 0 10px rgba(168, 237, 234, 0); }
        }

        /* Certifications */
        .cert-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .cert-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 15px;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .cert-card:hover {
            border: 2px solid #a8edea;
            background: rgba(255, 255, 255, 0.15);
            transform: translateY(-5px);
        }

        /* Stats Section */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .stat-box {
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-box:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: scale(1.1);
        }

        .stat-number {
            font-size: 3em;
            font-weight: bold;
            color: #a8edea;
            animation: countUp 2s ease-out;
        }

        /* Animations */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes bounceIn {
            0% {
                opacity: 0;
                transform: scale(0.3);
            }
            50% {
                opacity: 1;
                transform: scale(1.05);
            }
            70% {
                transform: scale(0.9);
            }
            100% {
                transform: scale(1);
            }
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 40px 20px;
            margin-top: 50px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
        }

        .footer-quote {
            font-size: 1.2em;
            font-style: italic;
            margin-bottom: 20px;
            animation: fadeIn 2s ease-out;
        }

        /* Floating Particles Background */
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
            background: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            animation: rise 10s infinite ease-in;
        }

        @keyframes rise {
            0% {
                bottom: -100px;
                opacity: 1;
            }
            100% {
                bottom: 100%;
                opacity: 0;
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .name {
                font-size: 2em;
            }
            
            .section-title {
                font-size: 2em;
            }
            
            .skills-grid,
            .achievements-grid,
            .cert-grid,
            .stats-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Floating Particles Background -->
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-img" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); display: flex; align-items: center; justify-content: center; font-size: 4em;">
                👨‍💻
            </div>
            <h1 class="name">Sahith Akula</h1>
            <p class="title">B.Tech IT Student | Full Stack Developer | AI/ML Enthusiast</p>
            <div class="typing-animation" id="typing-text">Always learning • Building • Improving ✨</div>
            
            <div class="contact-info">
                <div class="contact-badge">📍 Vijayawada, India</div>
                <div class="contact-badge">📧 akulasahith268@gmail.com</div>
                <div class="contact-badge">📞 +91 8341999296</div>
                <div class="contact-badge">🔗 GitHub</div>
            </div>
        </header>

        <!-- Stats Section -->
        <div class="section">
            <h2 class="section-title">📊 Quick Stats</h2>
            <div class="stats-container">
                <div class="stat-box">
                    <div class="stat-number">8.96</div>
                    <div>CGPA</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">3+</div>
                    <div>Major Projects</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">4</div>
                    <div>Awards</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">4</div>
                    <div>Certifications</div>
                </div>
            </div>
        </div>

        <!-- Education Section -->
        <div class="section">
            <h2 class="section-title">🎓 Education</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <h3>B.Tech – Information Technology</h3>
                    <p><strong>VR Siddhartha Engineering College, Vijayawada</strong></p>
                    <p>2023 – 2027 | CGPA: 8.96</p>
                </div>
                <div class="timeline-item">
                    <h3>Intermediate</h3>
                    <p><strong>Narayana Junior College, Vijayawada</strong></p>
                    <p>2021 – 2023 | CGPA: 9.73</p>
                </div>
                <div class="timeline-item">
                    <h3>SSC</h3>
                    <p><strong>HMK High School, Vijayawada</strong></p>
                    <p>2021 | CGPA: 10</p>
                </div>
            </div>
        </div>

        <!-- Skills Section -->
        <div class="section">
            <h2 class="section-title">🛠️ Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3>💻 Programming</h3>
                    <div>
                        <span class="skill-badge">Java</span>
                        <span class="skill-badge">Python</span>
                        <span class="skill-badge">JavaScript</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3>🚀 Frameworks & Tools</h3>
                    <div>
                        <span class="skill-badge">Spring Boot</span>
                        <span class="skill-badge">React</span>
                        <span class="skill-badge">Flutter</span>
                        <span class="skill-badge">Docker</span>
                        <span class="skill-badge">Git</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3>💾 Databases</h3>
                    <div>
                        <span class="skill-badge">MySQL</span>
                        <span class="skill-badge">PostgreSQL</span>
                        <span class="skill-badge">MongoDB</span>
                        <span class="skill-badge">Firebase</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3>🤖 AI & ML</h3>
                    <div>
                        <span class="skill-badge">OpenCV</span>
                        <span class="skill-badge">LLMs</span>
                        <span class="skill-badge">RAG</span>
                        <span class="skill-badge">NLP</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Projects Section -->
        <div class="section">
            <h2 class="section-title">🚀 Featured Projects</h2>
            
            <div class="project-card">
                <h3 class="project-title">🚗 Drowsiness Detection System for Vehicle Safety</h3>
                <p class="project-description">
                    Developed a real-time system to monitor driver alertness and prevent accidents. 
                    Detected eye closure, yawning, and head tilts using computer vision. 
                    Triggered audio-visual alerts and automatically stopped the vehicle if unresponsive. 
                    Initiated emergency contact calls when critical fatigue was detected.
                </p>
                <div class="tech-stack">
                    <span class="tech-tag">Python</span>
                    <span class="tech-tag">OpenCV</span>
                    <span class="tech-tag">CNN</span>
                    <span class="tech-tag">IoT</span>
                </div>
            </div>

            <div class="project-card">
                <h3 class="project-title">🤖 AI Career & Employee Assistance Platform</h3>
                <p class="project-description">
                    Built an AI-driven platform for resume optimization, job search, and interview preparation. 
                    Developed an AI chatbot and interview practice module with real-time feedback. 
                    Implemented ATS resume scoring, job recommendations, salary benchmarking, and skill gap analysis.
                </p>
                <div class="tech-stack">
                    <span class="tech-tag">React.js</span>
                    <span class="tech-tag">Express.js</span>
                    <span class="tech-tag">MongoDB</span>
                    <span class="tech-tag">Firebase</span>
                    <span class="tech-tag">NLP</span>
                    <span class="tech-tag">LLMs</span>
                    <span class="tech-tag">RAG</span>
                </div>
            </div>

            <div class="project-card">
                <h3 class="project-title">📚 AI Powered StudyMate App</h3>
                <p class="project-description">
                    Designed a Flutter mobile app integrated with a Spring Boot backend. 
                    Implemented PDF text extraction, summarization, and AI-based quiz generation. 
                    Used Spring AI for LLM integration and Spring Security for authentication. 
                    Containerized backend services using Docker.
                </p>
                <div class="tech-stack">
                    <span class="tech-tag">Flutter</span>
                    <span class="tech-tag">Spring Boot</span>
                    <span class="tech-tag">Spring AI</span>
                    <span class="tech-tag">Docker</span>
                    <span class="tech-tag">PostgreSQL</span>
                    <span class="tech-tag">LLMs</span>
                </div>
            </div>
        </div>

        <!-- Achievements Section -->
        <div class="section">
            <h2 class="section-title">🏆 Achievements</h2>
            <div class="achievements-grid">
                <div class="achievement-card">
                    <div class="medal">🥇</div>
                    <h3>1st Prize</h3>
                    <p>Game of Algorithms</p>
                    <small>IEEE Student Chapter</small>
                </div>
                <div class="achievement-card">
                    <div class="medal">🥇</div>
                    <h3>1st Prize</h3>
                    <p>Startup Competition</p>
                    <small>ECE Department</small>
                </div>
                <div class="achievement-card">
                    <div class="medal">🥈</div>
                    <h3>2nd Prize</h3>
                    <p>Bughunt Event</p>
                    <small>ACM Student Chapter</small>
                </div>
                <div class="achievement-card">
                    <div class="medal">🥈</div>
                    <h3>2nd Prize</h3>
                    <p>24-Hour Hackathon</p>
                    <small>Potti Sreeramulu Engineering College</small>
                </div>
            </div>
        </div>

        <!-- Certifications Section -->
        <div class="section">
            <h2 class="section-title">📜 Certifications</h2>
            <div class="cert-grid">
                <div class="cert-card">
                    <h3>Spring Boot</h3>
                    <p>Telusko - Udemy</p>
                </div>
                <div class="cert-card">
                    <h3>Docker</h3>
                    <p>Telusko - Udemy</p>
                </div>
                <div class="cert-card">
                    <h3>The Joy of Computing using Python</h3>
                    <p>NPTEL</p>
                </div>
                <div class="cert-card">
                    <h3>Python Essentials</h3>
                    <p>Cisco</p>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <footer class="footer">
            <p class="footer-quote">"Code is poetry written in logic."</p>
            <p>✨ Always learning • Building • Improving ✨</p>
            <p style="margin-top: 20px; opacity: 0.8;">© 2026 Sahith Akula. Made with ❤️ and ☕</p>
        </footer>
    </div>

    <script>
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            for (let i = 0; i < 20; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.width = Math.random() * 5 + 2 + 'px';
                particle.style.height = particle.style.width;
                particle.style.animationDelay = Math.random() * 10 + 's';
                particle.style.animationDuration = Math.random() * 10 + 10 + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Typing animation
        const texts = [
            'Always learning • Building • Improving ✨',
            'Java • Spring Boot • AI/ML 🚀',
            'Full Stack Developer 💻',
            'Problem Solver 💡'
        ];
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing-text');

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
                isDeleting = true;
                setTimeout(type, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
                setTimeout(type, 500);
            } else {
                setTimeout(type, isDeleting ? 50 : 100);
            }
        }

        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Initialize
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
            type();
            
            // Observe all sections
            document.querySelectorAll('.section').forEach(section => {
                section.style.opacity = '0';
                section.style.transform = 'translateY(50px)';
                section.style.transition = 'all 0.6s ease-out';
                observer.observe(section);
            });
        });

        // Add hover effects to skill badges
        document.querySelectorAll('.skill-badge').forEach(badge => {
            badge.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-5px) scale(1.1)';
            });
            badge.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });
    </script>
</body>
</html>
