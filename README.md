# sbrcs-science-club-554
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SBRCS Science Club</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a3e 50%, #2d2d5a 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: rgba(15, 15, 35, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0, 100, 255, 0.3);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo-img {
            width: 50px;
            height: 50px;
            background: radial-gradient(circle, #0066ff 0%, #003399 70%, #001166 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            box-shadow: 0 0 20px rgba(0, 102, 255, 0.5);
            animation: glow 2s ease-in-out infinite alternate;
        }

        .logo-img::before {
            content: '⚛';
            font-size: 24px;
            filter: brightness(1.5);
        }

        @keyframes glow {
            from { box-shadow: 0 0 20px rgba(0, 102, 255, 0.5); }
            to { box-shadow: 0 0 30px rgba(0, 102, 255, 0.8), 0 0 40px rgba(0, 102, 255, 0.3); }
        }

        .logo-text {
            color: white;
        }

        .logo-text h1 {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 2px;
        }

        .logo-text p {
            font-size: 0.9rem;
            opacity: 0.8;
            font-weight: 300;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: white;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
            padding: 0.5rem 1rem;
        }

        .nav-links a:hover {
            color: #66ccff;
            transform: translateY(-2px);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 2px;
            background: linear-gradient(45deg, #0066ff, #66ccff);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 80%;
        }

        main {
            padding-top: 80px;
        }

        .hero {
            text-align: center;
            padding: 6rem 0;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: 
                radial-gradient(circle at 20% 80%, rgba(0, 102, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(102, 204, 255, 0.1) 0%, transparent 50%);
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero-logo {
            width: 120px;
            height: 120px;
            margin: 0 auto 2rem;
            background: radial-gradient(circle, #0066ff 0%, #003399 70%, #001166 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 40px rgba(0, 102, 255, 0.6);
            animation: pulse 3s ease-in-out infinite;
        }

        .hero-logo::before {
            content: '⚛';
            font-size: 48px;
            filter: brightness(1.5);
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            animation: slideInUp 1s ease-out;
            background: linear-gradient(45deg, #66ccff, #0066ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero .school-name {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            opacity: 0.9;
            animation: slideInUp 1s ease-out 0.2s both;
            color: #66ccff;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.8;
            animation: slideInUp 1s ease-out 0.4s both;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #0066ff, #66ccff);
            color: white;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 102, 255, 0.4);
            animation: slideInUp 1s ease-out 0.6s both;
        }

        .cta-button:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 8px 25px rgba(0, 102, 255, 0.6);
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section {
            background: rgba(255, 255, 255, 0.95);
            margin: 2rem 0;
            border-radius: 20px;
            padding: 3rem 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .section:hover {
            transform: translateY(-5px);
        }

        .section h2 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            text-align: center;
            background: linear-gradient(45deg, #0066ff, #003399);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .activities-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .activity-card {
            background: linear-gradient(135deg, #0066ff 0%, #003399 100%);
            color: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        }

        .activity-card:hover {
            transform: rotateY(5deg) scale(1.05);
            box-shadow: 0 15px 35px rgba(0, 102, 255, 0.3);
        }

        .activity-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .events-timeline {
            position: relative;
            margin: 2rem 0;
        }

        .event-item {
            background: linear-gradient(135deg, #f8f9ff 0%, #e6f0ff 100%);
            margin: 1rem 0;
            padding: 1.5rem;
            border-radius: 10px;
            border-left: 4px solid #0066ff;
            transition: all 0.3s ease;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }

        .event-item:hover {
            background: linear-gradient(135deg, #e6f0ff 0%, #cce6ff 100%);
            transform: translateX(10px);
            box-shadow: 0 8px 25px rgba(0, 102, 255, 0.2);
        }

        .event-date {
            font-weight: bold;
            color: #0066ff;
            font-size: 0.9rem;
        }

        .event-title {
            font-size: 1.2rem;
            margin: 0.5rem 0;
            color: #003399;
        }

        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .member-card {
            text-align: center;
            padding: 2rem;
            background: linear-gradient(135deg, #e6f0ff 0%, #cce6ff 100%);
            border-radius: 15px;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(0, 102, 255, 0.2);
        }

        .member-card:hover {
            transform: translateY(-10px) rotateX(5deg);
            box-shadow: 0 15px 35px rgba(0, 102, 255, 0.2);
        }

        .member-avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: linear-gradient(45deg, #0066ff, #003399);
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2rem;
            font-weight: bold;
            box-shadow: 0 8px 25px rgba(0, 102, 255, 0.3);
        }

        .contact-info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .contact-card {
            background: linear-gradient(135deg, #e6f0ff 0%, #cce6ff 100%);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 102, 255, 0.2);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
        }

        .contact-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0, 102, 255, 0.2);
        }

        .contact-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
        }

        .contact-card h3 {
            color: #003399;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .contact-card p {
            margin-bottom: 0.5rem;
            color: #555;
        }

        .contact-card a {
            color: #0066ff;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .contact-card a:hover {
            color: #003399;
            text-decoration: underline;
        }

        .social-media-section {
            text-align: center;
            margin: 3rem 0;
            padding: 2rem;
            background: linear-gradient(135deg, #f8f9ff 0%, #e6f0ff 100%);
            border-radius: 15px;
            border: 1px solid rgba(0, 102, 255, 0.1);
        }

        .social-media-section h3 {
            color: #003399;
            margin-bottom: 2rem;
            font-size: 1.5rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .social-btn {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            padding: 1rem 1.5rem;
            background: linear-gradient(45deg, #0066ff, #003399);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s ease;
            font-weight: 500;
            box-shadow: 0 4px 15px rgba(0, 102, 255, 0.3);
        }

        .social-btn:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 8px 25px rgba(0, 102, 255, 0.4);
        }

        .social-btn.facebook:hover {
            background: linear-gradient(45deg, #1877f2, #0d47a1);
        }

        .social-btn.youtube:hover {
            background: linear-gradient(45deg, #ff0000, #cc0000);
        }

        .social-btn.instagram:hover {
            background: linear-gradient(45deg, #e4405f, #833ab4);
        }

        .social-btn.whatsapp:hover {
            background: linear-gradient(45deg, #25d366, #128c7e);
        }

        .contact-form-section {
            margin-top: 3rem;
            padding: 2rem;
            background: linear-gradient(135deg, #f8f9ff 0%, #e6f0ff 100%);
            border-radius: 15px;
            border: 1px solid rgba(0, 102, 255, 0.1);
        }

        .contact-form-section h3 {
            text-align: center;
            color: #003399;
            margin-bottom: 2rem;
            font-size: 1.5rem;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        .form-group select {
            padding: 1rem;
            border: 2px solid #e6f0ff;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s ease;
            background: white;
        }

        .form-group select:focus {
            outline: none;
            border-color: #0066ff;
            box-shadow: 0 0 0 3px rgba(0, 102, 255, 0.1);
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-group label {
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: #003399;
        }

        .form-group input,
        .form-group textarea {
            padding: 1rem;
            border: 2px solid #e6f0ff;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #0066ff;
            box-shadow: 0 0 0 3px rgba(0, 102, 255, 0.1);
        }

        .submit-btn {
            background: linear-gradient(45deg, #0066ff, #003399);
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 10px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 102, 255, 0.3);
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(0, 102, 255, 0.4);
        }

        footer {
            background: rgba(15, 15, 35, 0.95);
            backdrop-filter: blur(10px);
            text-align: center;
            padding: 3rem 2rem;
            margin-top: 3rem;
            border-radius: 20px 20px 0 0;
            color: white;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .footer-logo {
            width: 80px;
            height: 80px;
            margin: 0 auto 1rem;
            background: radial-gradient(circle, #0066ff 0%, #003399 70%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 20px rgba(0, 102, 255, 0.4);
        }

        .footer-logo::before {
            content: '⚛';
            font-size: 32px;
            filter: brightness(1.5);
        }

        .mobile-menu {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .contact-form {
            display: grid;
            gap: 1rem;
            max-width: 700px;
            margin: 0 auto;
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .mobile-menu {
                display: block;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero .school-name {
                font-size: 1.2rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .activities-grid,
            .team-grid,
            .contact-info-grid {
                grid-template-columns: 1fr;
            }

            .logo-text h1 {
                font-size: 1.2rem;
            }

            .logo-text p {
                font-size: 0.8rem;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .social-links {
                flex-direction: column;
                align-items: center;
            }

            .social-btn {
                width: 200px;
                justify-content: center;
            }
        }

        .science-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            background: rgba(0, 102, 255, 0.3);
            border-radius: 50%;
            animation: float-particle 15s infinite linear;
        }

        @keyframes float-particle {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="science-particles" id="particles"></div>

    <header>
        <nav class="container">
            <div class="logo">
                <div class="logo-img"></div>
                <div class="logo-text">
                    <h1>SBRCS Science Club</h1>
                    <p>Shaheed Bir Bikrom Ramiz Uddin Cantonment School</p>
                </div>
            </div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#activities">Activities</a></li>
                <li><a href="#events">Events</a></li>
                <li><a href="#team">Team</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <button class="mobile-menu">☰</button>
        </nav>
    </header>

    <main>
        <section id="home" class="hero">
            <div class="container hero-content">
                <div class="hero-logo"></div>
                <h1>SBRCS Science Club</h1>
                <div class="school-name">Shaheed Bir Bikrom Ramiz Uddin Cantonment School</div>
                <p>Exploring the wonders of science through innovation, experimentation, and discovery</p>
                <a href="#about" class="cta-button">Discover More</a>
            </div>
        </section>

        <div class="container">
            <section id="about" class="section">
                <h2>About Our Club</h2>
                <p>Welcome to the SBRCS Science Club of Shaheed Bir Bikrom Ramiz Uddin Cantonment School, where curiosity meets innovation! We are a passionate community of students dedicated to exploring the fascinating world of science through hands-on experiments, collaborative research, and exciting discoveries.</p>
                <p>Our club provides a platform for students to develop scientific thinking, engage in meaningful research projects, and connect with fellow science enthusiasts. Whether you're interested in biology, chemistry, physics, environmental science, or emerging technologies, there's a place for you in our diverse and inclusive community.</p>
                <p>Join us as we push the boundaries of knowledge, conduct groundbreaking experiments, and prepare for careers in STEM fields. Together, we're not just studying science – we're living it and making our school proud through scientific excellence!</p>
            </section>

            <section id="activities" class="section">
                <h2>Our Activities</h2>
                <div class="activities-grid">
                    <div class="activity-card">
                        <h3>🧪 Laboratory Experiments</h3>
                        <p>Conduct cutting-edge experiments in our state-of-the-art labs, exploring everything from molecular biology to quantum physics.</p>
                    </div>
                    <div class="activity-card">
                        <h3>🔬 Research Projects</h3>
                        <p>Collaborate on original research projects, presenting findings at regional and national science competitions.</p>
                    </div>
                    <div class="activity-card">
                        <h3>🚀 Science Fairs</h3>
                        <p>Organize and participate in science fairs, showcasing innovative projects and competing at various levels.</p>
                    </div>
                    <div class="activity-card">
                        <h3>🌱 Environmental Initiatives</h3>
                        <p>Lead sustainability projects and environmental research to make a positive impact on our community.</p>
                    </div>
                    <div class="activity-card">
                        <h3>👨‍🔬 Guest Lectures</h3>
                        <p>Host renowned scientists and researchers for inspiring talks and interactive workshops.</p>
                    </div>
                    <div class="activity-card">
                        <h3>🏆 Competitions</h3>
                        <p>Participate in regional and national science competitions, Olympiads, and academic challenges.</p>
                    </div>
                </div>
            </section>

            <section id="events" class="section">
                <h2>Upcoming Events</h2>
                <div class="events-timeline">
                    <div class="event-item">
                        <div class="event-date">October 15, 2025</div>
                        <div class="event-title">Annual Science Symposium</div>
                        <p>Join us for our biggest event of the year featuring student presentations, guest speakers, and interactive exhibits.</p>
                    </div>
                    <div class="event-item">
                        <div class="event-date">November 2, 2025</div>
                        <div class="event-title">Chemistry Lab Workshop</div>
                        <p>Hands-on chemistry experiments exploring reaction kinetics and thermodynamics.</p>
                    </div>
                    <div class="event-item">
                        <div class="event-date">November 20, 2025</div>
                        <div class="event-title">Environmental Field Trip</div>
                        <p>Visit to the local ecosystem research center for environmental science studies.</p>
                    </div>
                    <div class="event-item">
                        <div class="event-date">December 8, 2025</div>
                        <div class="event-title">Physics Competition Prep</div>
                        <p>Intensive preparation session for upcoming regional physics competitions.</p>
                    </div>
                    <div class="event-item">
                        <div class="event-date">December 22, 2025</div>
                        <div class="event-title">SBRCS Science Exhibition</div>
                        <p>Showcase of student research projects and innovations from our cantonment school.</p>
                    </div>
                </div>
            </section>

            <section id="team" class="section">
                <h2>Our Leadership Team</h2>
                <div class="team-grid">
                    <div class="member-card">
                        <div class="member-avatar">AP</div>
                        <h3>Alex Parker</h3>
                        <p><strong>President</strong></p>
                        <p>Passionate about biochemistry and molecular research. Leading our club toward new scientific horizons.</p>
                    </div>
                    <div class="member-card">
                        <div class="member-avatar">SJ</div>
                        <h3>Sarah Johnson</h3>
                        <p><strong>Vice President</strong></p>
                        <p>Environmental science enthusiast focused on sustainability and climate research initiatives.</p>
                    </div>
                    <div class="member-card">
                        <div class="member-avatar">MR</div>
                        <h3>Michael Rodriguez</h3>
                        <p><strong>Secretary</strong></p>
                        <p>Physics lover with expertise in quantum mechanics and theoretical physics applications.</p>
                    </div>
                    <div class="member-card">
                        <div class="member-avatar">EL</div>
                        <h3>Emily Liu</h3>
                        <p><strong>Treasurer</strong></p>
                        <p>Chemistry specialist managing our laboratory resources and experimental programs.</p>
                    </div>
                </div>
            </section>

            <section id="contact" class="section">
                <h2>Get in Touch</h2>
                <p style="text-align: center; margin-bottom: 3rem;">Ready to join our scientific community at SBRCS? We'd love to hear from you!</p>
                
                <!-- Contact Information Cards -->
                <div class="contact-info-grid">
                    <div class="contact-card">
                        <div class="contact-icon">📍</div>
                        <h3>Visit Us</h3>
                        <p><strong>Shaheed Bir Bikrom Ramiz Uddin Cantonment School</strong></p>
                        <p>Science Laboratory Building</p>
                        <p>Cantonment Area, Dhaka, Bangladesh</p>
                    </div>
                    
                    <div class="contact-card">
                        <div class="contact-icon">📧</div>
                        <h3>Email Us</h3>
                        <p><strong>Club Email:</strong></p>
                        <p><a href="mailto:scienceclub@sbrcs.edu.bd">scienceclub@sbrcs.edu.bd</a></p>
                        <p><strong>Faculty Advisor:</strong></p>
                        <p><a href="mailto:advisor@sbrcs.edu.bd">advisor@sbrcs.edu.bd</a></p>
                    </div>
                    
                    <div class="contact-card">
                        <div class="contact-icon">📱</div>
                        <h3>Call Us</h3>
                        <p><strong>Main Office:</strong></p>
                        <p>+880-2-XXXXXXX</p>
                        <p><strong>Science Department:</strong></p>
                        <p>+880-2-XXXXXXX</p>
                    </div>
                    
                    <div class="contact-card">
                        <div class="contact-icon">🕒</div>
                        <h3>Club Hours</h3>
                        <p><strong>Regular Meetings:</strong></p>
                        <p>Monday & Thursday: 3:00 PM - 5:00 PM</p>
                        <p><strong>Lab Sessions:</strong></p>
                        <p>Saturday: 10:00 AM - 12:00 PM</p>
                    </div>
                </div>

                <!-- Social Media Section -->
                <div class="social-media-section">
                    <h3>Follow Our Scientific Journey</h3>
                    <div class="social-links">
                        <a href="#" class="social-btn facebook">
                            <span>📘</span>
                            <span>Facebook</span>
                        </a>
                        <a href="#" class="social-btn youtube">
                            <span>📺</span>
                            <span>YouTube</span>
                        </a>
                        <a href="#" class="social-btn instagram">
                            <span>📷</span>
                            <span>Instagram</span>
                        </a>
                        <a href="#" class="social-btn whatsapp">
                            <span>💬</span>
                            <span>WhatsApp Group</span>
                        </a>
                    </div>
                </div>

                <!-- Contact Form -->
                <div class="contact-form-section">
                    <h3>Send Us a Message</h3>
                    <form class="contact-form">
                        <div class="form-row">
                            <div class="form-group">
                                <label for="name">Full Name</label>
                                <input type="text" id="name" name="name" required>
                            </div>
                            <div class="form-group">
                                <label for="email">Email Address</label>
                                <input type="email" id="email" name="email" required>
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-group">
                                <label for="class">Class</label>
                                <input type="text" id="class" name="class" placeholder="e.g., Class 9, Class 10" required>
                            </div>
                            <div class="form-group">
                                <label for="phone">Phone Number (Optional)</label>
                                <input type="tel" id="phone" name="phone" placeholder="+880-XXXXXXXXX">
                            </div>
                        </div>
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <select id="subject" name="subject" required>
                                <option value="">Select a topic</option>
                                <option value="membership">Club Membership</option>
                                <option value="events">Upcoming Events</option>
                                <option value="projects">Research Projects</option>
                                <option value="competitions">Science Competitions</option>
                                <option value="general">General Inquiry</option>
                                <option value="other">Other</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" name="message" rows="5" placeholder="Tell us about your interest in science, questions about the club, or how we can help you..."></textarea>
                        </div>
                        <button type="submit" class="submit-btn">Send Message ⚛</button>
                    </form>
                </div>
            </section>
        </div>
    </main>

    <footer>
        <div class="container">
            <div class="footer-logo"></div>
            <h3>SBRCS Science Club</h3>
            <p>Shaheed Bir Bikrom Ramiz Uddin Cantonment School</p>
            <p>&copy; 2025 SBRCS Science Club. All rights reserved.</p>
            <p>⚛ Inspiring the next generation of scientists 🔬</p>
        </div>
    </footer>

    <script>
        // Create floating particles
        function createParticle() {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.width = particle.style.height = Math.random() * 4 + 2 + 'px';
            particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
            particle.style.animationDelay = Math.random() * 2 + 's';
            document.getElementById('particles').appendChild(particle);

            setTimeout(() => {
                particle.remove();
            }, 15000);
        }

        // Create particles periodically
        setInterval(createParticle, 500);

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Form submission
        document.querySelector('.contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const formData = new FormData(this);
            const name = formData.get('name');
            const subject = formData.get('subject');
            
            let message = Thank you, ${name}! Your message about "${subject}" has been sent to SBRCS Science Club. We'll get back to you within 48 hours!;
            
            alert(message);
            
            this.reset();
        });

        // Add interactive effects to activity cards
        document.querySelectorAll('.activity-card').forEach(card => {
            card.addEventListener('click', function() {
                this.style.transform = 'scale(1.1) rotateY(10deg)';
                this.style.boxShadow = '0 20px 40px rgba(0, 102, 255, 0.4)';
                setTimeout(() => {
                    this.style.transform = '';
                    this.style.boxShadow = '';
                }, 300);
            });
        });

        // Add click effects to event items
        document.querySelectorAll('.event-item').forEach(item => {
            item.addEventListener('click', function() {
                this.style.background = 'linear-gradient(135deg, #0066ff, #003399)';
                this.style.color = 'white';
                this.style.transform = 'translateX(20px) scale(1.02)';
                
                setTimeout(() => {
                    this.style.background = '';
                    this.style.color = '';
                    this.style.transform = '';
                }, 1000);
            });
        });

        // Mobile menu toggle
        document.querySelector('.mobile-menu').addEventListener('click', function() {
            const navLinks = document.querySelector('.nav-links');
            if (navLinks.style.display === 'flex') {
                navLinks.style.display = 'none';
            } else {
                navLinks.style.display = 'flex';
                navLinks.style.flexDirection = 'column';
                navLinks.style.position = 'absolute';
                navLinks.style.top = '100%';
                navLinks.style.left = '0';
                navLinks.style.right = '0';
                navLinks.style.background = 'rgba(15, 15, 35, 0.98)';
                navLinks.style.padding = '1rem';
                navLinks.style.boxShadow = '0 2px 20px rgba(0, 102, 255, 0.3)';
                navLinks.style.borderRadius = '0 0 10px 10px';
            }
        });

        // Add scroll effects
        window.addEventListener('scroll', function() {
            const sections = document.querySelectorAll('.section');
            sections.forEach(section => {
                const rect = section.getBoundingClientRect();
                if (rect.top < window.innerHeight && rect.bottom > 0) {
                    section.style.opacity = '1';
                    section.style.transform = 'translateY(0)';
                }
            });
        });

        // Initialize scroll effects
        document.querySelectorAll('.section').forEach(section => {
            section.style.opacity = '0';
            section.style.transform = 'translateY(30px)';
            section.style.transition = 'all 0.6s ease';
        });

        // Create initial particles
        for (let i = 0; i < 5; i++) {
            setTimeout(createParticle, i * 1000);
        }
    </script>
</body>
</html>
