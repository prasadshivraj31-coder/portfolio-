# portfolio-<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prasad Shivraj | Portfolio</title>
    <style>
        :root {
            --primary: #1e293b;
            --secondary: #0f172a;
            --accent: #2563eb;
            --text: #334155;
            --light: #f8fafc;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
            line-height: 1.6;
            color: var(--text);
            background-color: var(--light);
            margin: 0;
            padding: 0;
        }

        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 4rem 2rem;
            text-align: center;
            position: relative;
        }

        /* Custom Webpage Profile Icon */
        .profile-icon {
            width: 80px;
            height: 80px;
            background: var(--accent);
            border: 3px solid white;
            border-radius: 50%;
            margin: 0 auto 1rem auto;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: white;
            font-weight: bold;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
        }

        header h1 {
            margin: 0;
            font-size: 2.3rem;
            letter-spacing: -0.05em;
        }

        header p {
            font-size: 1.1rem;
            opacity: 0.9;
            margin-top: 0.5rem;
        }

        /* Interactive Quick Badges */
        .badge-container {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
            margin-top: 1.5rem;
        }

        .interactive-badge {
            background: rgba(255, 255, 255, 0.15);
            border: 1px solid rgba(255, 255, 255, 0.25);
            padding: 0.6rem 1.2rem;
            border-radius: 50px;
            color: white;
            font-size: 0.9rem;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            transition: all 0.3s ease;
            backdrop-filter: blur(5px);
        }

        .interactive-badge:hover {
            background: var(--accent);
            transform: translateY(-2px);
        }

        .container {
            max-width: 800px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }

        section {
            background: white;
            padding: 2rem;
            margin-bottom: 2rem;
            border-radius: 12px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
        }

        h2 {
            color: var(--primary);
            border-bottom: 2px solid var(--light);
            padding-bottom: 0.5rem;
            margin-top: 0;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 1.5rem;
        }

        .skills-group h3 {
            font-size: 1.1rem;
            color: var(--accent);
            margin-top: 0;
            margin-bottom: 0.5rem;
        }

        .project-title {
            font-weight: bold;
            color: var(--secondary);
            font-size: 1.1rem;
        }

        ul {
            padding-left: 1.2rem;
            margin: 0.5rem 0;
        }

        li {
            margin-bottom: 0.25rem;
        }

        /* Immersive Story Slideshow Popup */
        .story-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .story-content {
            width: 100%;
            max-width: 450px;
            height: 80vh;
            position: relative;
            background: #000;
            border-radius: 12px;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .story-slide {
            display: none;
            width: 100%;
            height: 100%;
        }

        .story-slide.active {
            display: block;
        }

        .story-slide img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .story-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0,0,0,0.85));
            color: white;
            padding: 2rem 1.5rem;
            text-align: center;
        }

        .story-caption h4 {
            margin: 0 0 0.4rem 0;
            font-size: 1.2rem;
        }

        .story-caption p {
            margin: 0;
            font-size: 0.9rem;
            opacity: 0.8;
        }

        /* Story Progress Bar indicators */
        .story-indicators {
            position: absolute;
            top: 15px;
            left: 10px;
            right: 10px;
            display: flex;
            gap: 5px;
            z-index: 10;
        }

        .indicator {
            height: 3px;
            background: rgba(255, 255, 255, 0.3);
            flex: 1;
            border-radius: 2px;
        }

        .indicator.active {
            background: white;
        }

        .story-nav {
            position: absolute;
            top: 0;
            bottom: 0;
            width: 25%;
            cursor: pointer;
            z-index: 5;
        }

        .story-nav.prev { left: 0; }
        .story-nav.next { right: 0; }

        .close-story {
            position: absolute;
            top: 30px;
            right: 20px;
            color: white;
            font-size: 2rem;
            cursor: pointer;
            z-index: 20;
            font-weight: bold;
            text-shadow: 0 2px 4px rgba(0,0,0,0.5);
        }

        footer {
            text-align: center;
            padding: 2rem;
            color: #94a3b8;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <header>
        <div class="profile-icon">PS</div>
        <h1>Prasad Shivraj</h1>
        <p>Procurement & Billing Operations | Mechanical Engineer</p>
        
        <div class="badge-container">
            <div class="interactive-badge" onclick="openStory('bidar')">
                📍 Native: Bidar, Karnataka
            </div>
            <div class="interactive-badge" onclick="openStory('dsu')">
                🎓 Dayananda Sagar University
            </div>
        </div>
    </header>

    <div class="container">

        <section id="about">
            <h2>About Me</h2>
            <p>A results-driven professional combining a technical foundation in Mechanical Engineering with strong capabilities in procurement, billing operations, and supply chain management. Highly proficient in navigating complex operational workflows, optimizing technical document structures, and executing material tracking processes.</p>
        </section>

        <section id="skills">
            <h2>Core Expertise & Skills</h2>
            <div class="skills-container">
                <div class="skills-group">
                    <h3>Procurement & Supply Chain</h3>
                    <ul>
                        <li>Procure-to-Pay (P2P) Lifecycle</li>
                        <li>Purchase Order Management</li>
                        <li>Vendor Coordination & Tracking</li>
                        <li>Inventory & Material Control</li>
                    </ul>
                </div>
                <div class="skills-group">
                    <h3>Billing & Commercial Ops</h3>
                    <ul>
                        <li>Order-to-Cash (O2C) Workflow</li>
                        <li>Advanced Shipping Notice (ASN) Creation</li>
                        <li>Billing Operations & Documentation</li>
                        <li>Financial Record Accuracy</li>
                    </ul>
                </div>
                <div class="skills-group">
                    <h3>Technical & Systems</h3>
                    <ul>
                        <li>SAP ERP Systems</li>
                        <li>B.Tech Mechanical Engineering</li>
                        <li>Process Optimization</li>
                    </ul>
                </div>
            </div>
        </section>

        <section id="projects">
            <h2>Engineering Projects</h2>
            <div class="project">
                <div class="project-title">Aluminum Foam Air Purifier</div>
                <p>Designed and developed an innovative mechanical system utilizing aluminum foam to serve as an effective air purification medium, combining materials science with environmental fluid dynamics for a final year capstone project.</p>
            </div>
        </section>

    </div>

    <div id="bidar-modal" class="story-modal">
        <span class="close-story" onclick="closeStory('bidar')">&times;</span>
        <div class="story-content">
            <div class="story-indicators" id="bidar-indicators"></div>
            <div class="story-nav prev" onclick="changeSlide('bidar', -1)"></div>
            <div class="story-nav next" onclick="changeSlide('bidar', 1)"></div>
            
            <div class="story-slide bidar-slide active">
                <img src="16441.jpg" alt="Bidar Fort">
                <div class="story-caption">
                    <h4>Bidar Fort Gateway</h4>
                    <p>The monumental, historic fortifications standing as a testament to classic medieval architecture.</p>
                </div>
            </div>
            <div class="story-slide bidar-slide">
                <img src="16440.jpg" alt="Mahmud Gawan Madrasa">
                <div class="story-caption">
                    <h4>Mahmud Gawan Madrasa</h4>
                    <p>An ancient architectural marvel showing the historic heritage of academic learning in Bidar.</p>
                </div>
            </div>
            <div class="story-slide bidar-slide">
                <img src="16447.jpg" alt="Gurdwara Nanak Jhira Sahib">
                <div class="story-caption">
                    <h4>Gurdwara Sri Nanak Jhira Sahib</h4>
                    <p>One of India's most serene holy shrines, famous for its historic fresh-water spring.</p>
                </div>
            </div>
            <div class="story-slide bidar-slide">
                <img src="16446.jpg" alt="Chaubara Clock Tower">
                <div class="story-caption">
                    <h4>Chaubara Clock Tower</h4>
                    <p>The iconic 22-meter tall old tower positioned right at the heart of Bidar city center.</p>
                </div>
            </div>
            <div class="story-slide bidar-slide">
                <img src="16444.jpg" alt="Bidar Park">
                <div class="story-caption">
                    <h4>Scenic Local Landmarks</h4>
                    <p>Beautiful leisure spaces and rock gardens showcasing modern local recreation areas.</p>
                </div>
            </div>
        </div>
    </div>

    <div id="dsu-modal" class="story-modal">
        <span class="close-story" onclick="closeStory('dsu')">&times;</span>
        <div class="story-content">
            <div class="story-indicators" id="dsu-indicators"></div>
            <div class="story-nav prev" onclick="changeSlide('dsu', -1)"></div>
            <div class="story-nav next" onclick="changeSlide('dsu', 1)"></div>
            
            <div class="story-slide dsu-slide active">
                <img src="16448.jpg" alt="DSU Campus Architecture Panorama">
                <div class="story-caption">
                    <h4>DSU Campus Infrastructure</h4>
                    <p>Grand panoramic architectural view of the university blocks and main facilities.</p>
                </div>
            </div>
            <div class="story-slide dsu-slide">
                <img src="16452.jpg" alt="DSU Sports Complex Aerial">
                <div class="story-caption">
                    <h4>University Sports Complex</h4>
                    <p>Aerial view of the synthetic track, football pitch, and expansive campus grounds.</p>
                </div>
            </div>
            <div class="story-slide dsu-slide">
                <img src="16450.jpg" alt="DSU Seminar Hall Auditorium">
                <div class="story-caption">
                    <h4>Main Seminar Auditorium</h4>
                    <p>High-capacity presentation hall engineered beautifully for academic symposiums.</p>
                </div>
            </div>
            <div class="story-slide dsu-slide">
                <img src="16451.jpg" alt="DSU Central Library Workspace">
                <div class="story-caption">
                    <h4>Central Library & Study Spaces</h4>
                    <p>Modern interactive learning environment equipped with extensive collaborative research spaces.</p>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 Prasad Shivraj. All Rights Reserved.</p>
    </footer>

    <script>
        let slideIndices = { bidar: 0, dsu: 0 };

        function setupIndicators(type) {
            const slides = document.querySelectorAll('.' + type + '-slide');
            const container = document.getElementById(type + '-indicators');
            container.innerHTML = '';
            slides.forEach((_, i) => {
                let ind = document.createElement('div');
                ind.className = 'indicator' + (i === slideIndices[type] ? ' active' : '');
                container.appendChild(ind);
            });
        }

        function openStory(type) {
            slideIndices[type] = 0;
            document.getElementById(type + '-modal').style.display = 'flex';
            setupIndicators(type);
            showSlide(type);
        }

        function closeStory(type) {
            document.getElementById(type + '-modal').style.display = 'none';
        }

        function changeSlide(type, direction) {
            const slides = document.querySelectorAll('.' + type + '-slide');
            slideIndices[type] += direction;
            if (slideIndices[type] >= slides.length) slideIndices[type] = 0;
            if (slideIndices[type] < 0) slideIndices[type] = slides.length - 1;
            showSlide(type);
        }

        function showSlide(type) {
            const slides = document.querySelectorAll('.' + type + '-slide');
            slides.forEach((slide, idx) => {
                slide.classList.toggle('active', idx === slideIndices[type]);
            });
            
            const indicators = document.getElementById(type + '-indicators').children;
            for (let i = 0; i < indicators.length; i++) {
                indicators[i].classList.toggle('active', i === slideIndices[type]);
            }
        }

        window.onclick = function(event) {
            if (event.target.classList.contains('story-modal')) {
                event.target.style.display = 'none';
            }
        }
    </script>
</body>
</html>
