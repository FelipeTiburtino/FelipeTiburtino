<!-- index.html + style.css -->
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Perfil • Felipe Tiburtino Meireles</title>
  <style>
    * { margin:0; padding:0; box-sizing:border-box; }
    body { font-family:'Segoe UI', Tahoma, sans-serif; line-height:1.6; color:#333; background:#f5f5f5; padding:1rem; }
    .header { text-align:center; padding:2rem 0; }
    .avatar { width:150px; height:150px; border-radius:50%; border:5px solid #fff; box-shadow:0 0 10px rgba(0,0,0,0.1); }
    .header h1 { margin-top:1rem; font-size:2rem; }
    .bio { margin-top:0.5rem; color:#555; }
    .location { margin-top:0.25rem; font-size:0.9rem; color:#777; }
    .social-links { margin-top:1rem; }
    .social-links a { margin:0 0.5rem; text-decoration:none; color:#0366d6; }
    .section { margin:2rem 0; }
    .section h2 { margin-bottom:1rem; font-size:1.5rem; border-bottom:2px solid #0366d6; display:inline-block; }
    .tech-list { list-style:none; display:flex; flex-wrap:wrap; gap:0.75rem; }
    .tech-list li { background:#0366d6; color:#fff; padding:0.5rem 1rem; border-radius:999px; font-size:0.9rem; }
    .repos-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(220px,1fr)); gap:1rem; }
    .repo-card { background:#fff; padding:1rem; border-radius:8px; box-shadow:0 0 5px rgba(0,0,0,0.1); transition:transform .2s; }
    .repo-card:hover { transform:translateY(-5px); }
    .repo-card h3 { font-size:1.1rem; margin-bottom:0.5rem; }
    .repo-card a { text-decoration:none; color:#0366d6; }
    .repo-card p { font-size:0.9rem; color:#555; }
    .footer { text-align:center; margin-top:3rem; font-size:0.8rem; color:#999; }
  </style>
</head>
<body>
  <header class="header">
    <img src="https://github.com/FelipeTiburtino.png" alt="Avatar" class="avatar">
    <h1>Felipe Tiburtino Meireles</h1>
    <p class="bio">Desenvolvedor Full-stack | Apaixonado por IA, Web3 e código limpo.</p>
    <p class="location">Brasil</p>
    <div class="social-links">
      <a href="https://twitter.com/FelipeTiburtino" target="_blank">Twitter</a>
      <a href="https://linkedin.com/in/FelipeTiburtino" target="_blank">LinkedIn</a>
    </div>
  </header>

  <section class="section">
    <h2>🛠 Tecnologias</h2>
    <ul class="tech-list">
      <li>HTML5 & CSS3</li>
      <li>JavaScript / TypeScript</li>
      <li>Python</li>
      <li>React</li>
      <li>Git & GitHub</li>
    </ul>
  </section>

  <section class="section">
    <h2>📂 Repositórios Recentes</h2>
    <div id="repos" class="repos-grid">
      <!-- Conteúdo gerado por generate_profile.py -->
    </div>
    <small>Atualizado automaticamente via <code>generate_profile.py</code></small>
  </section>

  <footer class="footer">
    <p>Feito com ❤️ usando HTML, CSS e Python.</p>
  </footer>
</body>
</html>

# generate_profile.py
#!/usr/bin/env python3
import requests

USERNAME = "FelipeTiburtino"
API_URL = f"https://api.github.com/users/{USERNAME}/repos"
MAX_REPOS = 6

def fetch_repos():
    params = { "sort": "updated", "per_page": MAX_REPOS }
    resp = requests.get(API_URL, params=params)
    resp.raise_for_status()
    return resp.json()

def generate_html(repos):
    cards = []
    for repo in repos:
        name = repo["name"]
        desc = repo["description"] or "Sem descrição."
        url  = repo["html_url"]
        cards.append(f'''
    <div class="repo-card">
      <h3><a href="{url}" target="_blank">{name}</a></h3>
      <p>{desc}</p>
    </div>''')
    return "<div class=\\"repos-grid\\">"+ "".join(cards) +"</div>"

def main():
    repos = fetch_repos()
    html = generate_html(repos)
    with open("repos.html", "w", encoding="utf-8") as f:
        f.write(html)
    print(f"[+] Gerado repos.html com os {len(repos)} repositórios mais recentes.")

if __name__ == "__main__":
    main()
