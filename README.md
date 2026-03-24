<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Abdullah B. Aqeel - Portfolio Header</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&family=Rajdhani:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #0a0e17;
            --bg-secondary: #0f1419;
            --accent-cyan: #00d9ff;
            --accent-electric: #0099ff;
            --accent-purple: #7b2ff7;
            --text-primary: #e8edf4;
            --text-secondary: #8b95a8;
            --glow-cyan: rgba(0, 217, 255, 0.3);
            --glow-electric: rgba(0, 153, 255, 0.2);
        }

        body {
            font-family: 'Rajdhani', sans-serif;
            background: var(--bg-primary);
            color: var(--text-primary);
            overflow-x: hidden;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .header-container {
            position: relative;
            width: 100%;
            max-width: 1400px;
            padding: 4rem 3rem;
            overflow: hidden;
        }

        /* Animated gradient background */
        .gradient-bg {
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: 
                radial-gradient(circle at 20% 50%, var(--accent-purple) 0%, transparent 50%),
                radial-gradient(circle at 80% 50%, var(--accent-electric) 0%, transparent 50%),
                radial-gradient(circle at 50% 50%, var(--accent-cyan) 0%, transparent 70%);
            opacity: 0.08;
            animation: gradientFloat 20s ease-in-out infinite;
            filter: blur(80px);
        }

        @keyframes gradientFloat {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            33% { transform: translate(-10%, 5%) rotate(120deg); }
            66% { transform: translate(10%, -5%) rotate(240deg); }
        }

        /* Particle system */
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            background: var(--accent-cyan);
            border-radius: 50%;
            opacity: 0;
            animation: particleFloat linear infinite;
        }

        @keyframes particleFloat {
            0% {
                opacity: 0;
                transform: translateY(0) scale(0);
            }
            10% {
                opacity: 0.6;
            }
            90% {
                opacity: 0.2;
            }
            100% {
                opacity: 0;
                transform: translateY(-100vh) scale(1);
            }
        }

        /* Grid overlay */
        .grid-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(var(--accent-cyan) 1px, transparent 1px),
                linear-gradient(90deg, var(--accent-cyan) 1px, transparent 1px);
            background-size: 50px 50px;
            opacity: 0.03;
            animation: gridPulse 4s ease-in-out infinite;
        }

        @keyframes gridPulse {
            0%, 100% { opacity: 0.03; }
            50% { opacity: 0.06; }
        }

        /* Main content */
        .header-content {
            position: relative;
            z-index: 10;
        }

        .name-wrapper {
            margin-bottom: 1.5rem;
            overflow: hidden;
        }

        .name {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(2.5rem, 6vw, 5rem);
            font-weight: 900;
            line-height: 1.1;
            background: linear-gradient(135deg, var(--text-primary) 0%, var(--accent-cyan) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-fill-color: transparent;
            letter-spacing: -0.02em;
            position: relative;
            display: inline-block;
            animation: nameReveal 1.2s cubic-bezier(0.22, 1, 0.36, 1) forwards;
            opacity: 0;
            transform: translateY(100px);
        }

        @keyframes nameReveal {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .name::before {
            content: '';
            position: absolute;
            top: 0;
            left: -10px;
            width: calc(100% + 20px);
            height: 100%;
            background: linear-gradient(90deg, transparent, var(--glow-cyan), transparent);
            opacity: 0;
            filter: blur(20px);
            animation: nameGlow 3s ease-in-out infinite;
        }

        @keyframes nameGlow {
            0%, 100% { opacity: 0; }
            50% { opacity: 0.5; }
        }

        .title-wrapper {
            margin-bottom: 2.5rem;
            overflow: hidden;
        }

        .title {
            font-size: clamp(1.2rem, 3vw, 2rem);
            font-weight: 400;
            color: var(--text-secondary);
            letter-spacing: 0.05em;
            text-transform: uppercase;
            position: relative;
            display: inline-block;
            animation: titleReveal 1.2s cubic-bezier(0.22, 1, 0.36, 1) 0.2s forwards;
            opacity: 0;
            transform: translateY(50px);
        }

        @keyframes titleReveal {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .title span {
            background: linear-gradient(135deg, var(--accent-electric), var(--accent-cyan));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-weight: 500;
        }

        /* Contact info */
        .contact-info {
            display: flex;
            gap: 3rem;
            flex-wrap: wrap;
            animation: contactReveal 1.2s cubic-bezier(0.22, 1, 0.36, 1) 0.4s forwards;
            opacity: 0;
            transform: translateY(30px);
        }

        @keyframes contactReveal {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            font-size: 1.1rem;
            font-weight: 400;
            letter-spacing: 0.02em;
            color: var(--text-secondary);
            transition: all 0.3s cubic-bezier(0.22, 1, 0.36, 1);
            position: relative;
            padding: 0.5rem 0;
        }

        .contact-item::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--accent-electric), var(--accent-cyan));
            transition: width 0.4s cubic-bezier(0.22, 1, 0.36, 1);
        }

        .contact-item:hover {
            color: var(--text-primary);
            transform: translateX(5px);
        }

        .contact-item:hover::before {
            width: 100%;
        }

        .contact-icon {
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent-cyan);
            filter: drop-shadow(0 0 8px var(--glow-cyan));
        }

        /* Decorative elements */
        .corner-accent {
            position: absolute;
            width: 150px;
            height: 150px;
            border: 2px solid var(--accent-cyan);
            opacity: 0.2;
            animation: cornerPulse 3s ease-in-out infinite;
        }

        .corner-accent.top-left {
            top: 0;
            left: 0;
            border-right: none;
            border-bottom: none;
            animation-delay: 0s;
        }

        .corner-accent.bottom-right {
            bottom: 0;
            right: 0;
            border-left: none;
            border-top: none;
            animation-delay: 1.5s;
        }

        @keyframes cornerPulse {
            0%, 100% { 
                opacity: 0.2;
                transform: scale(1);
            }
            50% { 
                opacity: 0.4;
                transform: scale(1.05);
            }
        }

        /* Scan line effect */
        .scan-line {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, var(--accent-cyan), transparent);
            opacity: 0.3;
            animation: scan 8s linear infinite;
        }

        @keyframes scan {
            0% { transform: translateY(0); }
            100% { transform: translateY(100vh); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header-container {
                padding: 2rem 1.5rem;
            }

            .contact-info {
                gap: 1.5rem;
            }

            .contact-item {
                font-size: 1rem;
            }

            .corner-accent {
                width: 80px;
                height: 80px;
            }
        }
    </style>
</head>
<body>
    <div class="header-container">
        <!-- Background effects -->
        <div class="gradient-bg"></div>
        <div class="grid-overlay"></div>
        <div class="scan-line"></div>
        <div class="particles" id="particles"></div>
        
        <!-- Corner accents -->
        <div class="corner-accent top-left"></div>
        <div class="corner-accent bottom-right"></div>

        <!-- Main content -->
        <div class="header-content">
            <div class="name-wrapper">
                <h1 class="name">Abdullah B. Aqeel</h1>
            </div>
            
            <div class="title-wrapper">
                <h2 class="title">
                    <span>Full Stack Engineer</span> & <span>AI Developer</span>
                </h2>
            </div>

            <div class="contact-info">
                <div class="contact-item">
                    <div class="contact-icon">
                        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                            <polyline points="22,6 12,13 2,6"></polyline>
                        </svg>
                    </div>
                    <span>abdul575@hotmail.com</span>
                </div>
                
                <div class="contact-item">
                    <div class="contact-icon">
                        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path>
                        </svg>
                    </div>
                    <span>+92 321 66 44 106</span>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Particle system
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 30;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                
                // Random properties
                const size = Math.random() * 4 + 1;
                const startX = Math.random() * 100;
                const duration = Math.random() * 20 + 15;
                const delay = Math.random() * 10;
                
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.left = `${startX}%`;
                particle.style.animationDuration = `${duration}s`;
                particle.style.animationDelay = `${delay}s`;
                
                particlesContainer.appendChild(particle);
            }
        }

        // Initialize particles on load
        window.addEventListener('load', createParticles);

        // Cursor glow effect
        const headerContainer = document.querySelector('.header-container');
        let cursorGlow = null;

        headerContainer.addEventListener('mousemove', (e) => {
            if (!cursorGlow) {
                cursorGlow = document.createElement('div');
                cursorGlow.style.position = 'absolute';
                cursorGlow.style.width = '300px';
                cursorGlow.style.height = '300px';
                cursorGlow.style.background = 'radial-gradient(circle, rgba(0, 217, 255, 0.15) 0%, transparent 70%)';
                cursorGlow.style.pointerEvents = 'none';
                cursorGlow.style.transform = 'translate(-50%, -50%)';
                cursorGlow.style.transition = 'opacity 0.3s ease';
                cursorGlow.style.zIndex = '5';
                headerContainer.appendChild(cursorGlow);
            }

            const rect = headerContainer.getBoundingClientRect();
            const x = e.clientX - rect.left;
            const y = e.clientY - rect.top;

            cursorGlow.style.left = `${x}px`;
            cursorGlow.style.top = `${y}px`;
            cursorGlow.style.opacity = '1';
        });

        headerContainer.addEventListener('mouseleave', () => {
            if (cursorGlow) {
                cursorGlow.style.opacity = '0';
            }
        });
    </script>
</body>
</html>

---

# About Me:
I’m currently working on Insaf, a legal-tech platform aimed at bridging the gap between lawyers and clients in Pakistan through digital accessibility.<br>I’m looking to collaborate on Full-stack applications built with Next.js, React Native, React.js, and FastAPI. I am particularly interested in open-source projects involving RAG (Retrieval-Augmented Generation), LangChain, and Computer Vision pipelines using YOLOv8 and ResNet50. I can also contribute to system architecture requiring Docker, PostgreSQL, and Redis for scalable, high-performance backends.<br>I’m looking for help with Architecting microservices using Kubernetes and implementing event-driven systems for industry-level scalability. I am looking to deepen my knowledge of MLOps—specifically model deployment, monitoring, and A/B testing for Generative AI. Additionally, I am interested in learning enterprise-grade security protocols for SaaS platforms and optimizing WebRTC for low-latency, real-time communication in AI-driven tools.<br>I’m currently learning<br>Ask me about Cross-platform mobile development with Expo, building AI wrappers for niche industries, or forensic image analysis using Deep Learning. You can also ask me about my research on Skin Cancer Detection using CNNs, my experience with ICPC competitive programming, or how I built a production-scale AI courseware platform with WebRTC.<br>Fun fact Round 1 winner International Collegiate Programming Competition 2024-25 (ICPC), Winner Ignite AI Wrapper 2026, Winner GDGoC LeetCode Challenge (Google Developer Club)<br>Skills C++, C#, Python, SQL, JavaScript, ES6+, No-SQL, MongoDB, Firebase, React, React Native, Next.js, Express.js, Node.js, Flask, FastAPI, Tailwind CSS, Redux, Docker, AWS, Git, GitHub, CI/CD Pipelines, PostgreSQL, Redis, Linux, Ubuntu, LangChain, OpenAI API, RAG Pipelines, BERT, GPT, YOLOv8, ResNet50, TensorFlow, PyTorch, Hadoop, WebRTC


## Socials:
[![Discord](https://img.shields.io/badge/Discord-%237289DA.svg?logo=discord&logoColor=white)](https://discord.gg/paracetamol___) [![Instagram](https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&logoColor=white)](https://instagram.com/fimiliaricemos) [![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white)](https://linkedin.com/in/https://www.linkedin.com/in/abdullah-bin-aqeel-43b597170) [![Medium](https://img.shields.io/badge/Medium-12100E?logo=medium&logoColor=white)](https://medium.com/@abdulbinaqeel) [![Stack Overflow](https://img.shields.io/badge/-Stackoverflow-FE7A16?logo=stack-overflow&logoColor=white)](https://stackoverflow.com/users/21563047) [![Mastodon](https://img.shields.io/badge/-MASTODON-%232B90D9?logo=mastodon&logoColor=white)](https://mastodon.social/@Abdullah Bin Aqeel) [![email](https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white)](mailto:abdul575@hotmail.com) 

# Tech Stack:
![C](https://img.shields.io/badge/c-%2300599C.svg?style=flat&logo=c&logoColor=white) ![C#](https://img.shields.io/badge/c%23-%23239120.svg?style=flat&logo=csharp&logoColor=white) ![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=flat&logo=c%2B%2B&logoColor=white) ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=flat&logo=css3&logoColor=white) ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=flat&logo=html5&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=flat&logo=javascript&logoColor=%23F7DF1E) ![Python](https://img.shields.io/badge/python-3670A0?style=flat&logo=python&logoColor=ffdd54) ![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=flat&logo=typescript&logoColor=white) ![Windows Terminal](https://img.shields.io/badge/Windows%20Terminal-%234D4D4D.svg?style=flat&logo=windows-terminal&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=flat&logo=amazon-aws&logoColor=white) ![Azure](https://img.shields.io/badge/azure-%230072C6.svg?style=flat&logo=microsoftazure&logoColor=white) ![Firebase](https://img.shields.io/badge/firebase-%23039BE5.svg?style=flat&logo=firebase) ![Google Cloud](https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=flat&logo=google-cloud&logoColor=white) ![Netlify](https://img.shields.io/badge/netlify-%23000000.svg?style=flat&logo=netlify&logoColor=#00C7B7) ![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat&logo=oracle&logoColor=white) ![Vercel](https://img.shields.io/badge/vercel-%23000000.svg?style=flat&logo=vercel&logoColor=white) ![Apache Hadoop](https://img.shields.io/badge/Apache%20Hadoop-66CCFF?style=flat&logo=apachehadoop&logoColor=black) ![Bootstrap](https://img.shields.io/badge/bootstrap-%238511FA.svg?style=flat&logo=bootstrap&logoColor=white) ![Expo](https://img.shields.io/badge/expo-1C1E24?style=flat&logo=expo&logoColor=#D04A37) ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=flat&logo=fastapi) ![Flask](https://img.shields.io/badge/flask-%23000.svg?style=flat&logo=flask&logoColor=white) ![jQuery](https://img.shields.io/badge/jquery-%230769AD.svg?style=flat&logo=jquery&logoColor=white) ![NPM](https://img.shields.io/badge/NPM-%23CB3837.svg?style=flat&logo=npm&logoColor=white) ![Next JS](https://img.shields.io/badge/Next-black?style=flat&logo=next.js&logoColor=white) ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=flat&logo=node.js&logoColor=white) ![OpenCV](https://img.shields.io/badge/opencv-%23white.svg?style=flat&logo=opencv&logoColor=white) ![React](https://img.shields.io/badge/react-%2320232a.svg?style=flat&logo=react&logoColor=%2361DAFB) ![React Native](https://img.shields.io/badge/react_native-%2320232a.svg?style=flat&logo=react&logoColor=%2361DAFB) ![Redux](https://img.shields.io/badge/redux-%23593d88.svg?style=flat&logo=redux&logoColor=white) ![Socket.io](https://img.shields.io/badge/Socket.io-black?style=flat&logo=socket.io&badgeColor=010101) ![SASS](https://img.shields.io/badge/SASS-hotpink.svg?style=flat&logo=SASS&logoColor=white) ![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=flat&logo=tailwind-css&logoColor=white) ![Three js](https://img.shields.io/badge/threejs-black?style=flat&logo=three.js&logoColor=white) ![Vue.js](https://img.shields.io/badge/vue.js-%2335495e.svg?style=flat&logo=vuedotjs&logoColor=%234FC08D) ![Vite](https://img.shields.io/badge/vite-%23646CFF.svg?style=flat&logo=vite&logoColor=white) ![Yarn](https://img.shields.io/badge/yarn-%232C8EBB.svg?style=flat&logo=yarn&logoColor=white) ![Apache](https://img.shields.io/badge/apache-%23D42029.svg?style=flat&logo=apache&logoColor=white) ![Firebase](https://img.shields.io/badge/firebase-a08021?style=flat&logo=firebase&logoColor=ffcd34) ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat&logo=mariadb&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=flat&logo=mongodb&logoColor=white) ![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=flat&logo=mysql&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=flat&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/redis-%23DD0031.svg?style=flat&logo=redis&logoColor=white) ![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat&logo=supabase&logoColor=white) ![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=flat&logo=figma&logoColor=white) ![Canva](https://img.shields.io/badge/Canva-%2300C4CC.svg?style=flat&logo=Canva&logoColor=white) ![Adobe](https://img.shields.io/badge/adobe-%23FF0000.svg?style=flat&logo=adobe&logoColor=white) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=flat&logo=numpy&logoColor=white) ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=flat&logo=pandas&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=flat&logo=PyTorch&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=flat&logo=scikit-learn&logoColor=white) ![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=flat&logo=TensorFlow&logoColor=white) ![Git](https://img.shields.io/badge/git-%23F05033.svg?style=flat&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=flat&logo=github&logoColor=white) ![Cisco](https://img.shields.io/badge/cisco-%23049fd9.svg?style=flat&logo=cisco&logoColor=black) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=flat&logo=docker&logoColor=white) ![Notion](https://img.shields.io/badge/Notion-%23000000.svg?style=flat&logo=notion&logoColor=white) ![Raspberry Pi](https://img.shields.io/badge/-Raspberry_Pi-C51A4A?style=flat&logo=Raspberry-Pi) ![Swagger](https://img.shields.io/badge/-Swagger-%23Clojure?style=flat&logo=swagger&logoColor=white)
# GitHub Stats:
![](https://github-readme-stats.vercel.app/api?username=abdullahbinaqeel&theme=dark&hide_border=false&include_all_commits=true&count_private=true)<br/>
![](https://nirzak-streak-stats.vercel.app/?user=abdullahbinaqeel&theme=dark&hide_border=false)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=abdullahbinaqeel&theme=dark&hide_border=false&include_all_commits=true&count_private=true&layout=compact)

## GitHub Trophies
![](https://github-profile-trophy.vercel.app/?username=abdullahbinaqeel&theme=radical&no-frame=false&no-bg=false&margin-w=4)

### 🔝 Top Contributed Repo
![](https://github-contributor-stats.vercel.app/api?username=abdullahbinaqeel&limit=5&theme=dark&combine_all_yearly_contributions=true)

---
[![](https://visitcount.itsvg.in/api?id=abdullahbinaqeel&icon=3&color=0)](https://visitcount.itsvg.in)

<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->
