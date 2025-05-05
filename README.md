<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
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
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background-color: #2c3e50;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
        }

        nav ul li {
            margin: 0 20px;
        }

        nav ul li a {
            color: white;
            text-decoration: none;
            font-size: 1.1rem;
            transition: color 0.3s ease;
        }

        nav ul li a:hover {
            color: #3498db;
        }

        section {
            padding: 80px 0;
        }

        #home {
            background: linear-gradient(135deg, #3498db, #2c3e50);
            color: white;
            text-align: center;
            padding: 150px 0;
        }

        #home h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .skill-card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: transform 0.3s ease;
        }

        .skill-card:hover {
            transform: translateY(-5px);
        }

        .skill-card img {
            width: 80px;
            height: 80px;
            margin-bottom: 1rem;
        }

        .skill-card h3 {
            margin-bottom: 1rem;
            color: #2c3e50;
        }

        .progress-bar {
            background: #f0f0f0;
            height: 10px;
            border-radius: 5px;
            overflow: hidden;
        }

        .progress {
            background: linear-gradient(90deg, #3498db, #2980b9);
            height: 100%;
            border-radius: 5px;
            transition: width 0.3s ease;
        }

        #contact {
            background-color: #f9f9f9;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        label {
            display: block;
            margin-bottom: 0.5rem;
            color: #2c3e50;
        }

        input,
        textarea {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }

        textarea {
            height: 150px;
            resize: vertical;
        }

        button {
            background: #3498db;
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            transition: background 0.3s ease;
        }

        button:hover {
            background: #2980b9;
        }

        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 1.5rem 0;
        }

        #message-alert {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 1rem;
            border-radius: 5px;
            display: none;
            z-index: 1001;
        }

        .success {
            background: #2ecc71;
            color: white;
        }

        @media (max-width: 768px) {
            #home h1 {
                font-size: 2rem;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            nav ul {
                flex-direction: column;
                text-align: center;
            }

            nav ul li {
                margin: 10px 0;
            }
        }
    </style>
</head>
<body>
    <div id="message-alert"></div>
    <header>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home">
            <div class="container">
                <h1>Welcome to My Portfolio</h1>
                <p>Hi! I'm a web developer passionate about creating beautiful websites.</p>
            </div>
        </section>

        <section id="skills">
            <div class="container">
                <h2>My Skills</h2>
                <div class="skills-grid">
                    <div class="skill-card">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML5">
                        <h3>HTML</h3>
                        <div class="progress-bar">
                            <div class="progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-card">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS3">
                        <h3>CSS</h3>
                        <div class="progress-bar">
                            <div class="progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-card">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python">
                        <h3>Python</h3>
                        <div class="progress-bar">
                            <div class="progress" style="width: 40%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact">
            <div class="container">
                <h2>Contact Me</h2>
                <form id="contact-form">
                    <div class="form-group">
                        <label for="name">Name:</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email:</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Message:</label>
                        <textarea id="message" name="message" required></textarea>
                    </div>
                    <button type="submit">Send Message</button>
                </form>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <p>&copy; 2025 My Portfolio. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Form handling (simulating Python backend functionality)
        document.getElementById('contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const formData = {
                name: document.getElementById('name').value,
                email: document.getElementById('email').value,
                message: document.getElementById('message').value
            };

            // Simulate form processing
            const alert = document.getElementById('message-alert');
            alert.textContent = `Thank you ${formData.name}! Your message has been sent.`;
            alert.className = 'success';
            alert.style.display = 'block';

            // Clear form
            this.reset();

            // Hide alert after 3 seconds
            setTimeout(() => {
                alert.style.display = 'none';
            }, 3000);
        });
    </script>
</body>
</html>
