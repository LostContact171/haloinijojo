<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My JJ Web</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6a0dad;
            --primary-light: #9b4dff;
            --primary-dark: #4a0072;
            --secondary: #ff9e00;
            --dark: #1a1a2e;
            --light: #f8f9fa;
            --gray: #e2e2e2;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.7;
        }
        
        /* Glassmorphism Navigation */
        header {
            position: fixed;
            width: 100%;
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(106, 13, 173, 0.1);
        }
        
        nav {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1.5rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-weight: 700;
            font-size: 1.5rem;
            color: var(--primary);
            text-decoration: none;
        }
        
        .nav-links {
            display: flex;
            gap: 2rem;
        }
        
        .nav-links a {
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            transition: all 0.3s ease;
        }
        
        .nav-links a:hover {
            color: var(--primary);
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--primary);
            bottom: -5px;
            left: 0;
            transition: width 0.3s ease;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        /* Sections */
        section {
            min-height: 100vh;
            padding: 8rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        /* Hero Section */
        #home {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 3rem;
            background: linear-gradient(135deg, var(--light) 50%, rgba(106, 13, 173, 0.05) 50%);
        }
        
        .hero-content {
            flex: 1;
        }
        
        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            line-height: 1.2;
            color: var(--primary-dark);
        }
        
        .hero-content h1 span {
            color: var(--primary);
        }
        
        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: #555;
            max-width: 600px;
        }
        
        .cta-buttons {
            display: flex;
            gap: 1rem;
        }
        
        .btn {
            padding: 0.8rem 1.8rem;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
            display: inline-block;
        }
        
        .btn-primary {
            background: var(--primary);
            color: white;
            box-shadow: 0 4px 15px rgba(106, 13, 173, 0.3);
        }
        
        .btn-primary:hover {
            background: var(--primary-dark);
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(106, 13, 173, 0.4);
        }
        
        .btn-outline {
            border: 2px solid var(--primary);
            color: var(--primary);
        }
        
        .btn-outline:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-3px);
        }
        
        .hero-image {
            flex: 1;
            display: flex;
            justify-content: center;
        }
        
        .fotojj-img {
            width: 350px;
            height: 350px;
            border-radius: 20px;
            object-fit: cover;
            box-shadow: 20px 20px 0 var(--primary-light);
            transition: all 0.5s ease;
        }
        
        .fotojj-img:hover {
            transform: rotate(-5deg);
            box-shadow: 25px 25px 0 var(--primary-light);
        }
        
        /* About Section */
        #about {
            background-color: white;
            border-radius: 30px;
            margin: 3rem auto;
            box-shadow: 0 10px 30px rgba(106, 13, 173, 0.1);
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 4rem;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary-dark);
            display: inline-block;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 5px;
            background: var(--primary);
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 5px;
        }
        
        .about-content {
            display: flex;
            gap: 3rem;
            align-items: center;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
        }
        
        .skills-container {
            margin-top: 2rem;
        }
        
        .skill-item {
            margin-bottom: 1.5rem;
        }
        
        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }
        
        .skill-bar {
            height: 10px;
            background: var(--gray);
            border-radius: 5px;
            overflow: hidden;
        }
        
        .skill-progress {
            height: 100%;
            background: var(--primary);
            border-radius: 5px;
        }
        
        /* Contact Section */
        #contact {
            text-align: center;
        }
        
        .social-container {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .social-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            width: 120px;
            box-shadow: 0 5px 15px rgba(106, 13, 173, 0.1);
            transition: all 0.3s ease;
        }
        
        .social-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(106, 13, 173, 0.2);
        }
        
        .social-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        .social-name {
            font-weight: 600;
            color: var(--dark);
        }
        
        /* Footer */
        footer {
            text-align: center;
            padding: 2rem;
            background: var(--primary-dark);
            color: white;
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 1rem 0;
        }
        
        .footer-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-links a:hover {
            color: var(--secondary);
        }
        
        .copyright {
            margin-top: 1rem;
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            #home {
                flex-direction: column;
                text-align: center;
                background: var(--light);
            }
            
            .hero-content {
                margin-bottom: 3rem;
            }
            
            .cta-buttons {
                justify-content: center;
            }
            
            .about-content {
                flex-direction: column;
            }
        }
        
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                padding: 1rem;
            }
            
            .nav-links {
                margin-top: 1rem;
                gap: 1rem;
            }
            
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .fotojj-img {
                width: 280px;
                height: 280px;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <a href="#" class="logo">JJ<span>WEB</span></a>
            <div class="nav-links">
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#contact">Contact</a>
            </div>
        </nav>
    </header>

    <section id="home">
        <div class="hero-content">
            <h1>Halo Saya <span>Jonathan</span></h1>
            <p>Passion saya ada di balik lensa kamera, kreativitas mengalir di meja editing, dan eksplorasi saya terus berkembang di dunia videografi. Inilah alchemy visual yang saya tawarkan.</p>
            <div class="cta-buttons">
                <a href="#about" class="btn btn-primary">Explore About Me</a>
                <a href="#contact" class="btn btn-outline">Contact Me</a>
            </div>
        </div>
        <div class="hero-image">
            <img src="fotojj.jpg" alt="fotojj Picture" class="fotojj-img">
        </div>
    </section>

    <section id="about">
        <div class="section-title">
            <h2>About Me</h2>
        </div>
        <div class="about-content">
            <div class="about-text">
                <h3>Professional Creative</h3>
                <p>Saya seorang profesional kreatif dengan spesialisasi utama di bidang fotografi yang telah saya kuasai hingga 90%. Didukung oleh keahlian editing gambar sebesar 70% dan kemampuan videografi sebesar 50%, saya menggabungkan ketiga elemen ini untuk menciptakan karya visual yang impactful.</p>
                
                <div class="skills-container">
                    <h3>My Talent</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Photography</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Editing</span>
                            <span>70%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 70%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Videografer</span>
                            <span>50%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 50%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="section-title">
            <h2>Get In Touch</h2>
        </div>
        <p>Saya fokus menciptakan momen yang berbicara melalui frame</p>
        
       
        <div class="social-container">
            <a href="https://www.instagram.com/jonathann171?igsh=MWRvcWthZ3ppbWQ1Zw==" target="_blank" class="social-card">
                <div class="social-icon"><i class="fab fa-instagram"></i></div>
                <div class="social-name">Instagram</div>
            </a>
            <a href="mailto:jonathanliuz172@gmail.com" class="social-card">
                <div class="social-icon"><i class="fas fa-envelope"></i></div>
                <div class="social-name">Email</div>
            </a>
        </div>
    </section>

    <footer>
        <div class="footer-links">
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#contact">Contact</a>
            <a href="#">Privacy Policy</a>
        </div>
        <div class="copyright">
            &copy; March 2025 [Jonathan]. All rights reserved.
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 100,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Header shadow on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if(window.scrollY > 50) {
                header.style.boxShadow = '0 4px 20px rgba(106, 13, 173, 0.15)';
            } else {
                header.style.boxShadow = '0 2px 20px rgba(106, 13, 173, 0.1)';
            }
        });

        // Animate skill bars on scroll
        const animateSkillBars = () => {
            const skillBars = document.querySelectorAll('.skill-progress');
            skillBars.forEach(bar => {
                const width = bar.style.width;
                bar.style.width = '0';
                setTimeout(() => {
                    bar.style.width = width;
                }, 100);
            });
        };

        const aboutSection = document.querySelector('#about');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if(entry.isIntersecting) {
                    animateSkillBars();
                    observer.unobserve(entry.target);
                }
            });
        }, { threshold: 0.5 });

        if(aboutSection) {
            observer.observe(aboutSection);
        }
    </script>
</body>
</html>
