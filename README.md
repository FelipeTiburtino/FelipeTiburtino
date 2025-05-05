<!-- index.html -->
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Perfil • Felipe Tiburtino Meireles</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header class="header">
    <div class="container">
      <img
        src="https://github.com/FelipeTiburtino.png"
        alt="Avatar"
        class="avatar"
      />
      <h1>Felipe Tiburtino Meireles</h1>
      <p class="bio">Full-stack Developer | Entusiasta de IA, Web3 & Código Limpo</p>
      <div class="social-links">
        <a href="https://twitter.com/FelipeTiburtino" target="_blank">🐦 Twitter</a>
        <a href="https://linkedin.com/in/FelipeTiburtino" target="_blank">💼 LinkedIn</a>
      </div>
    </div>
  </header>

  <main class="main container">
    <section class="tech">
      <h2>🛠 Tecnologias</h2>
      <ul class="tech-list">
        <li>HTML5 & CSS3</li>
        <li>JavaScript / TypeScript</li>
        <li>Python</li>
        <li>React</li>
        <li>Git & GitHub</li>
      </ul>
    </section>

    <section class="repos">
      <h2>📂 Repositórios Recentes</h2>
      <div id="repos" class="repos-grid">
        <!-- Conteúdo gerado por generate_profile.py -->
      </div>
      <small>Atualizado automaticamente via <code>generate_profile.py</code></small>
    </section>
  </main>

  <footer class="footer">
    <p>Feito com ❤️ usando HTML, CSS e Python</p>
  </footer>
</body>
</html>

/* style.css */
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');

:root {
  --primary: #6f42c1;
  --bg: #f0f2f5;
  --text: #2f2f2f;
  --card: #ffffff;
  --shadow: rgba(0, 0, 0, 0.1);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: 'Inter', sans-serif;
  background: var(--bg);
  color: var(--text);
  line-height: 1.6;
}
.container {
  width: 90%;
  max-width: 900px;
  margin: 0 auto;
}

/* Header */
.header {
  background: linear-gradient(135deg, var(--primary), #8a63d2);
  color: #fff;
  padding: 3rem 0;
  text-align: center;
  clip-path: ellipse(75% 100% at 50% 0);
}
.avatar {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  border: 4px solid #fff;
  margin-bottom: 1rem;
}
.header h1 {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
  font-weight: 700;
}
.bio {
  font-weight: 600;
  opacity: 0.9;
}
.social-links a {
  margin: 0 0.75rem;
  color: #fff;
  font-weight: 600;
  text-decoration: none;
  transition: opacity 0.2s;
}
.social-links a:hover {
  opacity: 0.8;
}

/* Main */
.main {
  margin-top: -2rem;
  padding-bottom: 2rem;
}
.tech,
.repos {
  background: var(--card);
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 4px 16px var(--shadow);
  margin-bottom: 2rem;
}
.tech h2,
.repos h2 {
  color: var(--primary);
  margin-bottom: 1rem;
  font-size: 1.75rem;
}
.tech-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}
.tech-list li {
  background: var(--primary);
  color: #fff;
  padding: 0.5rem 0.75rem;
  border-radius: 999px;
  font-size: 0.9rem;
}

/* Repos */
.repos-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
  gap: 1rem;
}
.repo-card {
  background: #fff;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 8px var(--shadow);
  transition: transform 0.3s, box-shadow 0.3s;
}
.repo-card:hover {
  transform: translateY(-5px) scale(1.02);
  box-shadow: 0 12px 24px var(--shadow);
}
.repo-card h3 {
  margin-bottom: 0.5rem;
  font-size: 1.2rem;
  color: var(--primary);
  transition: color 0.2s;
}
.repo-card h3 a {
  text-decoration: none;
}
.repo-card h3 a:hover {
  color: #51328f;
}
.repo-card p {
  font-size: 0.95rem;
  color: #555;
}

/* Footer */
.footer {
  text-align: center;
  padding: 1rem 0;
  opacity: 0.7;
  font-size: 0.9rem;
}

