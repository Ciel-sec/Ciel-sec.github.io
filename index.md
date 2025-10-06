<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ciel Sec — Blog & Projetos</title>
  <link rel="stylesheet" href="style.css">
  <link rel="icon" href="img/profile.jpg">
</head>
<body>

  <header class="navbar">
    <div class="container">
      <h1 class="logo">Ciel <span>Sec</span></h1>
      <nav>
        <ul>
          <li><a href="#intro">Início</a></li>
          <li><a href="#projects">Projetos</a></li>
          <li><a href="#blog">Blog</a></li>
          <li><a href="#contact">Contato</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <section id="intro" class="intro-section">
    <div class="container intro">
      <img src="img/profile.jpg" alt="Foto de perfil" class="profile-img">
      <div>
        <h2>👋 Olá, eu sou o Ciel</h2>
        <p>Sou desenvolvedor e pesquisador em segurança, criando ferramentas e automações seguras em ambientes autorizados.  
        Apaixonado por tecnologia, UI elegante e código bem feito.</p>
      </div>
    </div>
  </section>

  <section id="projects" class="projects-section">
    <div class="container">
      <h2>🚀 Projetos</h2>
      <div class="project-grid">
        <div class="project-card">
          <h3>Consulta360</h3>
          <p>Ferramenta em PyQt para consultas de CPF/CNPJ com UI profissional e exportação de dados.</p>
          <a href="#" class="btn">Ver projeto</a>
        </div>

        <div class="project-card">
          <h3>StormCentral</h3>
          <p>Painel em Flask para automação de varreduras autorizadas, análise com IA e relatórios.</p>
          <a href="#" class="btn">Ver projeto</a>
        </div>

        <div class="project-card">
          <h3>Jarvis (Assistente de Voz)</h3>
          <p>Assistente local com Vosk + Pyttsx3, comandos por voz e respostas contextuais.</p>
          <a href="#" class="btn">Ver projeto</a>
        </div>
      </div>
    </div>
  </section>

  <section id="blog" class="blog-section">
    <div class="container">
      <h2>📰 Blog</h2>
      <div class="post-grid">
        <div class="post-card">
          <img src="img/blog1.jpg" alt="Post 1">
          <h3>Como criei meu painel de automação com Flask</h3>
          <p>Um overview de arquitetura, organização e UI responsiva para ferramentas seguras.</p>
          <a href="#" class="btn">Ler mais</a>
        </div>

        <div class="post-card">
          <img src="img/blog2.jpg" alt="Post 2">
          <h3>Integrando IA para análise de vulnerabilidades</h3>
          <p>Uso de LLMs (Groq e Gemini) para priorização e sumarização de achados técnicos.</p>
          <a href="#" class="btn">Ler mais</a>
        </div>
      </div>
    </div>
  </section>

  <section id="contact" class="contact-section">
    <div class="container">
      <h2>📫 Contato</h2>
      <form class="contact-form" action="https://formspree.io/f/mayvlxgz" method="POST">
        <input type="text" name="name" placeholder="Seu nome" required>
        <input type="email" name="_replyto" placeholder="Seu e-mail" required>
        <textarea name="message" rows="5" placeholder="Sua mensagem" required></textarea>
        <button type="submit" class="btn">Enviar</button>
      </form>
    </div>
  </section>

  <footer>
    <p>© 2025 Ciel Sec — Todos os direitos reservados.</p>
  </footer>

</body>
</html>
