<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Ravi Agrahari · DevOps & Cloud Engineering Portfolio</title>
    <!-- Google Fonts + Enhanced Typography -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&family=Fira+Code:wght@400;500;600&display=swap" rel="stylesheet">
    <!-- Font Awesome 6 (free icons) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Animate.css for subtle scroll + entrance animations -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: radial-gradient(circle at 10% 20%, #0b0f1c, #05070f);
            font-family: 'Inter', sans-serif;
            color: #eef2ff;
            line-height: 1.5;
            scroll-behavior: smooth;
            padding: 2rem 1rem;
        }

        /* glowing glassmorphic container */
        .glass-card {
            background: rgba(15, 25, 45, 0.55);
            backdrop-filter: blur(12px);
            border-radius: 2.5rem;
            border: 1px solid rgba(66, 153, 225, 0.25);
            box-shadow: 0 25px 45px -12px rgba(0, 0, 0, 0.5), 0 0 0 1px rgba(66, 220, 220, 0.1) inset;
            transition: transform 0.2s ease, border-color 0.2s;
        }

        .glass-card:hover {
            border-color: rgba(0, 255, 255, 0.4);
            box-shadow: 0 30px 50px -18px rgba(0, 200, 255, 0.2);
        }

        .wrapper {
            max-width: 1280px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        /* header area with dynamic glow */
        .hero-section {
            text-align: center;
            padding: 2.8rem 1.5rem 2rem;
        }

        .glow-text {
            font-size: 3rem;
            font-weight: 800;
            background: linear-gradient(135deg, #FFFFFF, #7dd3fc, #38bdf8);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            letter-spacing: -0.02em;
            text-shadow: 0 2px 5px rgba(0,160,255,0.2);
        }

        .typing-wrapper {
            margin-top: 1rem;
            font-family: 'Fira Code', monospace;
            font-weight: 500;
            background: rgba(0, 20, 40, 0.6);
            display: inline-block;
            padding: 0.6rem 1.8rem;
            border-radius: 60px;
            backdrop-filter: blur(4px);
            font-size: 1.2rem;
            border-left: 3px solid cyan;
        }

        /* badges + stats grid */
        .stats-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
            margin: 1.5rem 0 0.5rem;
        }

        .tech-pill {
            background: #0f172ad9;
            border-radius: 40px;
            padding: 0.5rem 1.2rem;
            font-size: 0.85rem;
            font-weight: 500;
            backdrop-filter: blur(4px);
            border: 1px solid #2d3a5e;
            transition: all 0.2s;
        }

        .tech-pill i {
            margin-right: 8px;
            color: #2dd4bf;
        }

        .section-title {
            font-size: 1.8rem;
            font-weight: 700;
            letter-spacing: -0.3px;
            margin-bottom: 1.5rem;
            display: flex;
            align-items: center;
            gap: 12px;
            border-left: 5px solid #22d3ee;
            padding-left: 1rem;
        }

        .icon-ring {
            background: #1e2a47;
            border-radius: 50%;
            width: 44px;
            height: 44px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }

        /* skill icons grid + hover animation */
        .skills-panel {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 1rem;
        }
        .skill-icon {
            background: rgba(30, 41, 59, 0.7);
            border-radius: 18px;
            padding: 0.7rem 1rem;
            transition: all 0.2s ease-in-out;
            border: 1px solid #2d3e6e;
        }
        .skill-icon:hover {
            transform: translateY(-4px);
            background: #1e2f4b;
            border-color: #2dd4bf;
            box-shadow: 0 12px 20px -12px #0ff3;
        }

        /* project cards */
        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.6rem;
            margin-top: 0.8rem;
        }
        .project-card {
            background: rgba(12, 20, 32, 0.7);
            border-radius: 1.8rem;
            padding: 1.4rem;
            backdrop-filter: blur(8px);
            border: 1px solid #2a3c60;
            transition: 0.25s;
        }
        .project-card:hover {
            border-color: #38bdf8;
            transform: translateY(-6px);
            background: rgba(18, 30, 48, 0.85);
        }
        .project-icon {
            font-size: 2.2rem;
            color: #5eead4;
            margin-bottom: 12px;
        }

        /* timeline / goals list */
        .goals-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1rem;
        }
        .goal-item {
            background: #0f172b80;
            border-radius: 1.5rem;
            padding: 0.8rem 1.2rem;
            display: flex;
            align-items: center;
            gap: 12px;
            border-left: 4px solid #2dd4bf;
        }

        /* github stats row */
        .github-stats {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 2rem;
            align-items: center;
        }
        .stat-card {
            background: #0e1628aa;
            border-radius: 2rem;
            padding: 1rem;
            flex: 1;
            min-width: 240px;
            text-align: center;
        }

        /* horizontal trophies scroll */
        .trophy-scroll {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
            margin: 1rem 0;
        }

        footer {
            text-align: center;
            font-size: 0.85rem;
            border-top: 1px dashed #2d4270;
            padding-top: 2rem;
            margin-top: 1rem;
        }

        a {
            color: #b9f3ff;
            text-decoration: none;
        }
        a:hover {
            color: white;
            text-decoration: underline;
        }

        hr {
            border-color: #1e2f4a;
            margin: 0.8rem 0;
        }

        @media (max-width: 750px) {
            .glow-text {
                font-size: 2rem;
            }
            .section-title {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
<div class="wrapper">
    <!-- HEADER with animated glitch + badge -->
    <div class="glass-card hero-section animate__animated animate__fadeInUp">
        <h1 class="glow-text"><i class="fas fa-cloud-upload-alt me-2" style="margin-right: 10px;"></i>Hi, I'm Ravi Agrahari</h1>
        <h3 style="font-weight: 500; margin-top: 12px; color: #cbd5e6;">
            🚀 DevOps Enthusiast | ☁️ Cloud Learner | ⚙️ Automation Explorer | 💻 Full Stack Developer
        </h3>
        <div class="typing-wrapper">
            <i class="fas fa-terminal"></i> DevOps Engineer in Progress · Docker · K8s · Terraform · AWS
        </div>
        <div class="stats-grid">
            <span class="tech-pill"><i class="fas fa-eye"></i> 4.2k+ profile views</span>
            <span class="tech-pill"><i class="fab fa-github"></i> 21+ repositories</span>
            <span class="tech-pill"><i class="fas fa-rocket"></i> CI/CD obsessed</span>
        </div>
        <p align="center" style="margin-top: 18px;">
            <img src="https://komarev.com/ghpvc/?username=Ravi-Agrahari&label=PROFILE%20VIEWS&color=0e75b6&style=for-the-badge" alt="views" style="max-width: 100%;">
        </p>
    </div>

    <!-- ABOUT ME: YAML style modern block -->
    <div class="glass-card" style="padding: 1.6rem 2rem;">
        <div class="section-title">
            <div class="icon-ring"><i class="fas fa-user-astronaut"></i></div>
            <span>📄 dev/ravi.yaml</span>
        </div>
        <div style="background: #010a1a80; border-radius: 1.2rem; padding: 1.2rem; font-family: 'Fira Code', monospace; font-size: 0.9rem; border: 1px solid #2c416e;">
            <pre style="color:#b9e2ff; overflow-x: auto; white-space: pre-wrap; word-break: break-word;">
name: "Ravi Agrahari"
role: "DevOps & Cloud Engineering Student"
focus:
  - Linux · Docker · Kubernetes
  - GitHub Actions · Jenkins · Terraform
  - AWS Cloud · Prometheus · GitOps
background:
  - MERN Stack
  - Next.js · Web Development
goals:
  - Cloud Engineering · Infrastructure Automation
philosophy: "Automate reliable systems, share knowledge openly."
            </pre>
        </div>
    </div>

    <!-- TECH STACK + DEVOPS ARSENAL combined modern -->
    <div class="glass-card" style="padding: 1.6rem 2rem;">
        <div class="section-title">
            <i class="fas fa-microchip"></i> 
            <span>🛠️ Development & DevOps Arsenal</span>
        </div>
        <div>
            <h4 style="margin: 0.5rem 0 1rem 0; display: flex; gap: 8px;"><i class="fab fa-dev"></i> Frontend / Backend</h4>
            <div class="skills-panel">
                <span class="skill-icon"><i class="fab fa-html5"></i> HTML5</span>
                <span class="skill-icon"><i class="fab fa-css3-alt"></i> CSS3</span>
                <span class="skill-icon"><i class="fab fa-js"></i> JavaScript</span>
                <span class="skill-icon"><i class="fab fa-react"></i> React</span>
                <span class="skill-icon"><i class="fab fa-node-js"></i> Node.js</span>
                <span class="skill-icon"><i class="fab fa-python"></i> Python</span>
                <span class="skill-icon"><i class="fas fa-database"></i> MongoDB/PostgreSQL</span>
            </div>
            <h4 style="margin: 1.5rem 0 1rem 0;"><i class="fas fa-cogs"></i> DevOps & Cloud</h4>
            <div class="skills-panel">
                <span class="skill-icon"><i class="fab fa-docker"></i> Docker</span>
                <span class="skill-icon"><i class="fas fa-cubes"></i> Kubernetes</span>
                <span class="skill-icon"><i class="fab fa-jenkins"></i> Jenkins</span>
                <span class="skill-icon"><i class="fab fa-github-alt"></i> GitHub Actions</span>
                <span class="skill-icon"><i class="fas fa-code-branch"></i> Terraform</span>
                <span class="skill-icon"><i class="fab fa-linux"></i> Linux/Bash</span>
                <span class="skill-icon"><i class="fab fa-aws"></i> AWS</span>
                <span class="skill-icon"><i class="fas fa-chart-line"></i> Prometheus/Grafana</span>
            </div>
        </div>
        <hr>
        <div align="center">
            <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black"/>
            <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>
            <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white"/>
            <img src="https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white"/>
            <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white"/>
            <img src="https://img.shields.io/badge/Terraform-844FBA?style=for-the-badge&logo=terraform&logoColor=white"/>
            <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white"/>
        </div>
    </div>

    <!-- FEATURED PROJECTS with modern icons -->
    <div class="glass-card" style="padding: 1.6rem 2rem;">
        <div class="section-title">
            <i class="fas fa-star-of-life"></i>
            <span>🚀 Featured Projects · DevOps in Action</span>
        </div>
        <div class="project-grid">
            <div class="project-card"><div class="project-icon"><i class="fab fa-docker"></i></div><h3>🐳 Dockerized MERN Stack</h3><p>Full MERN app containerized with Docker Compose, multi-stage builds, volume management.</p><span style="font-size:12px; background:#1f2b46; padding:4px 8px; border-radius:20px;">docker · compose · node</span></div>
            <div class="project-card"><div class="project-icon"><i class="fas fa-code-branch"></i></div><h3>⚙️ GitHub Actions CI/CD</h3><p>Automated testing & deployment workflows for React + Node apps, linting & security checks.</p><span style="font-size:12px; background:#1f2b46; padding:4px 8px; border-radius:20px;">yaml · actions · automation</span></div>
            <div class="project-card"><div class="project-icon"><i class="fab fa-jenkins"></i></div><h3>🔨 Jenkins Pipeline as Code</h3><p>Declarative pipeline for Java/Spring app, integrated with SonarQube & DockerHub push.</p><span style="font-size:12px; background:#1f2b46; padding:4px 8px; border-radius:20px;">jenkins · groovy · ci/cd</span></div>
            <div class="project-card"><div class="project-icon"><i class="fas fa-cubes"></i></div><h3>☸️ Kubernetes Deployment</h3><p>Microservices orchestration using K8s, HPA, ConfigMaps, Ingress, rolling updates.</p><span style="font-size:12px; background:#1f2b46; padding:4px 8px; border-radius:20px;">k8s · yaml · scalability</span></div>
            <div class="project-card"><div class="project-icon"><i class="fab fa-aws"></i></div><h3>☁️ AWS Cloud Project</h3><p>Serverless app with Lambda, API Gateway, S3, DynamoDB, CloudFront CDN & IaC via Terraform.</p><span style="font-size:12px; background:#1f2b46; padding:4px 8px; border-radius:20px;">aws · serverless · terraform</span></div>
            <div class="project-card"><div class="project-icon"><i class="fas fa-infinity"></i></div><h3>📦 Terraform Infrastructure</h3><p>AWS VPC, EC2, RDS fully provisioned using Terraform modules & remote state management.</p><span style="font-size:12px; background:#1f2b46; padding:4px 8px; border-radius:20px;">iac · terraform · automation</span></div>
        </div>
    </div>

    <!-- GITHUB STATS DYNAMIC + STREAK + ACTIVITY modern layout -->
    <div class="glass-card" style="padding: 1.6rem 2rem;">
        <div class="section-title">
            <i class="fab fa-github-alt"></i>
            <span>📈 GitHub Analytics & Contribution Pulse</span>
        </div>
        <div class="github-stats">
            <div class="stat-card"><img src="https://github-readme-stats.vercel.app/api?username=Ravi-Agrahari&show_icons=true&theme=tokyonight&hide_border=true&bg_color=00000000" width="100%" alt="stats"></div>
            <div class="stat-card"><img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ravi-Agrahari&layout=compact&theme=tokyonight&hide_border=true&bg_color=00000000" width="100%" alt="langs"></div>
        </div>
        <div align="center" style="margin: 1rem 0;">
            <img src="https://github-readme-streak-stats.herokuapp.com/?user=Ravi-Agrahari&theme=tokyonight&hide_border=true&background=0D111700" alt="streak" style="max-width:100%">
        </div>
        <div align="center">
            <img src="https://github-readme-activity-graph.vercel.app/graph?username=Ravi-Agrahari&theme=tokyo-night&bg_color=0a0f1f&color=70e0ff&line=38bdf8&point=ffffff&area=true&hide_border=true" width="100%" alt="activity graph">
        </div>
        <div class="trophy-scroll" style="margin-top: 1.2rem;">
            <img src="https://github-profile-trophy.vercel.app/?username=Ravi-Agrahari&theme=tokyonight&no-frame=true&row=1&column=7" width="100%" alt="trophies">
        </div>
    </div>

    <!-- 2026 GOALS with checklist style -->
    <div class="glass-card" style="padding: 1.6rem 2rem;">
        <div class="section-title">
            <i class="fas fa-bullseye"></i>
            <span>🎯 2026 Roadmap — Mission Control</span>
        </div>
        <div class="goals-list">
            <div class="goal-item"><i class="fas fa-check-circle" style="color:#2dd4bf"></i> Master Linux Administration</div>
            <div class="goal-item"><i class="fas fa-check-circle" style="color:#2dd4bf"></i> Master Docker & K8s (CKA path)</div>
            <div class="goal-item"><i class="fas fa-check-circle" style="color:#2dd4bf"></i> Learn Terraform Deeply + Terragrunt</div>
            <div class="goal-item"><i class="fas fa-check-circle" style="color:#2dd4bf"></i> Deploy HA Apps on AWS (EKS)</div>
            <div class="goal-item"><i class="fas fa-check-circle" style="color:#2dd4bf"></i> Build Production CI/CD Pipelines</div>
            <div class="goal-item"><i class="fas fa-check-circle" style="color:#2dd4bf"></i> Learn GitOps (ArgoCD)</div>
            <div class="goal-item"><i class="fas fa-check-circle" style="color:#2dd4bf"></i> Monitoring Stack (Prometheus/ Loki)</div>
            <div class="goal-item"><i class="fas fa-check-circle" style="color:#2dd4bf"></i> Earn AWS Solutions Architect Cert</div>
            <div class="goal-item"><i class="fas fa-check-circle" style="color:#2dd4bf"></i> Contribute to CNCF Open Source</div>
        </div>
    </div>

    <!-- Connect & Engineering Philosophy -->
    <div class="glass-card" style="padding: 1.8rem 2rem;">
        <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 2rem;">
            <div>
                <div class="section-title" style="margin-bottom: 0.8rem;"><i class="fas fa-hand-peace"></i> 🌐 Connect & Collaborate</div>
                <div style="display: flex; gap: 2rem; flex-wrap: wrap;">
                    <a href="https://linkedin.com/in/ravi-agrahari-9a653027a" target="_blank"><i class="fab fa-linkedin" style="font-size: 2.2rem;"></i> LinkedIn</a>
                    <a href="https://codepen.io/ravi-agrahari-the-typescripter" target="_blank"><i class="fab fa-codepen" style="font-size: 2.2rem;"></i> CodePen</a>
                    <a href="https://www.hackerrank.com/raviagrahari2021" target="_blank"><i class="fab fa-hackerrank" style="font-size: 2.2rem;"></i> HackerRank</a>
                    <a href="#"><i class="fab fa-github" style="font-size: 2rem;"></i> GitHub/Ravi-Agrahari</a>
                </div>
            </div>
            <div style="max-width: 340px; background: #0e162f70; border-radius: 1.5rem; padding: 1rem;">
                <i class="fas fa-quote-left" style="color:#2dd4bf;"></i>
                <p style="font-style: italic; font-weight: 300; margin: 8px 0;">Automate repetitive work. Build reliable systems. Learn continuously. Share knowledge openly.</p>
                <p>— DevOps Philosophy</p>
            </div>
        </div>
        <hr style="margin: 1.5rem 0 1rem;">
        <div align="center">
            <i class="fas fa-terminal"></i> “Infrastructure as Code, resilience as culture”<br/>
            ⭐ From <strong>Ravi Agrahari</strong> | DevOps Engineer in Progress 🚀
        </div>
    </div>
    <footer>
        <i class="fas fa-cloud-moon"></i> 24/7 automation mindset · Last commit: passion for cloud native · 2026 edition
    </footer>
</div>
<!-- Optional: smooth entrance fade on scroll observed with CSS + inline animation -->
</body>
</html>
