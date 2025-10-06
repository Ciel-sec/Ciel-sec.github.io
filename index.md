<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Ciel Sec — Blog & Projetos</title>
  <meta name="description" content="Portfólio técnico e blog: automação, segurança em ambientes autorizados, PyQt, Flask e IA." />
  <meta name="color-scheme" content="dark light" />
  <style>
    /* ---------- Design tokens ---------- */
    :root{
      --bg:#0d1117; --bg-elev:#111720; --card:#141b25; --muted:#aab2c0;
      --text:#e6edf3; --accent:#2ec7a9; --accent-2:#60a5fa; --danger:#ff6b6b;
      --border:#212938; --shadow:0 10px 30px rgba(0,0,0,.35);
      --radius:14px; --r-sm:8px; --space:clamp(16px,2vw,24px);
      --font: "Inter", system-ui, -apple-system, Segoe UI, Roboto, sans-serif;
      --mono: "JetBrains Mono", ui-monospace, SFMono-Regular, Menlo, monospace;
      --code-bg:#0c1118;
    }
    *{box-sizing:border-box} html,body{height:100%}
    body{margin:0;background:var(--bg);color:var(--text);font-family:var(--font);line-height:1.6}
    img{max-width:100%;display:block}
    a{color:var(--accent);text-decoration:none} a:hover{opacity:.9}
    .container{max-width:1120px;margin-inline:auto;padding-inline:clamp(16px,3vw,28px)}
    .btn{display:inline-block;padding:.65rem 1.1rem;border-radius:10px;background:var(--accent);color:#0a0e13;font-weight:700;border:1px solid transparent;transition:.2s}
    .btn:hover{filter:brightness(.96)}
    .btn.ghost{background:transparent;border-color:var(--border);color:var(--text)}
    .btn.ghost:hover{border-color:var(--accent)}

    /* ---------- Navbar ---------- */
    header.nav{position:sticky;top:0;backdrop-filter:saturate(120%) blur(6px);
      background:color-mix(in oklab, var(--bg) 80%, #000 20%);border-bottom:1px solid var(--border);z-index:50}
    .nav .wrap{display:flex;align-items:center;justify-content:space-between;padding:.8rem 0}
    .brand{display:flex;gap:.6rem;align-items:center;font-weight:800;letter-spacing:.4px}
    .brand .dot{width:.9rem;height:.9rem;border-radius:50%;background:linear-gradient(135deg,var(--accent),var(--accent-2))}
    .nav ul{display:flex;gap:1rem;list-style:none;margin:0;padding:0}
    .nav a{color:var(--text);padding:.5rem .7rem;border-radius:10px}
    .nav a:hover{background:color-mix(in oklab, var(--card) 70%, #000 30%)}

    /* ---------- Hero / Intro ---------- */
    .hero{padding:calc(var(--space)*2) 0}
    .intro{display:grid;grid-template-columns:120px 1fr;gap:clamp(16px,3vw,28px);align-items:center}
    .avatar{width:120px;height:120px;border-radius:50%;border:3px solid var(--accent);object-fit:cover;box-shadow:var(--shadow)}
    .hero p{color:var(--muted);margin:.4rem 0 0}

    /* ---------- Sections ---------- */
    section{padding:calc(var(--space)*2) 0;border-top:1px solid var(--border)}
    h2{font-size:clamp(1.2rem,2.6vw,1.6rem);margin:0 0 1rem}
    .muted{color:var(--muted)}

    /* ---------- Cards Grid ---------- */
    .grid{display:grid;gap:var(--space)}
    .grid.cols-3{grid-template-columns:repeat(3,1fr)}
    @media (max-width:920px){.grid.cols-3{grid-template-columns:repeat(2,1fr)}}
    @media (max-width:640px){.grid,.grid.cols-3{grid-template-columns:1fr}}

    .card{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:clamp(16px,2.5vw,22px);box-shadow:var(--shadow)}
    .card h3{margin:.2rem 0 .6rem}
    .meta{font-size:.9rem;color:var(--muted)}
    .tag{display:inline-block;padding:.25rem .55rem;border-radius:999px;background:#0f1420;border:1px solid var(--border);font-size:.75rem;margin-right:.3rem}

    /* ---------- Blog cards ---------- */
    .post .thumb{aspect-ratio:16/9;border-radius:12px;object-fit:cover;border:1px solid var(--border);margin-bottom:.7rem}

    /* ---------- Code Section (tabs) ---------- */
    .code-tabs{display:grid;gap:.7rem}
    .tabs{display:flex;flex-wrap:wrap;gap:.5rem}
    .tab-btn{padding:.45rem .75rem;border-radius:9px;border:1px solid var(--border);background:#0f1420;color:var(--text);cursor:pointer}
    .tab-btn.active{border-color:var(--accent);outline:2px solid color-mix(in oklab,var(--accent) 35%, transparent)}
    .snippet{display:none}
    .snippet.active{display:block}
    pre{background:var(--code-bg);color:var(--text);padding:1rem;border-radius:12px;border:1px solid var(--border);overflow:auto}
    code{font-family:var(--mono);font-size:.92rem}
    .copy{float:right;margin-top:-.4rem}

    /* ---------- Form ---------- */
    form{display:grid;gap:.8rem}
    input,textarea{background:var(--bg-elev);border:1px solid var(--border);color:var(--text);
      padding:.9rem;border-radius:10px;font:inherit}
    textarea{min-height:140px;resize:vertical}
    .notice{font-size:.85rem;color:var(--muted)}

    /* ---------- Footer ---------- */
    footer{padding:1.2rem 0;border-top:1px solid var(--border);color:var(--muted);text-align:center}
  </style>
</head>
<body>

  <!-- Navbar -->
  <header class="nav">
    <div class="container wrap">
      <div class="brand"><span class="dot"></span> <span>Ciel <span class="muted">Sec</span></span></div>
      <nav>
        <ul>
          <li><a href="#intro">Início</a></li>
          <li><a href="#projects">Projetos</a></li>
          <li><a href="#codes">Códigos</a></li>
          <li><a href="#blog">Blog</a></li>
          <li><a href="#contact">Contato</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <!-- Introdução -->
  <section id="intro" class="hero">
    <div class="container intro">
      <img class="avatar" src="https://i.imgur.com/kOXnswR.gif" alt="Ciel acenando">
      <div>
        <h1 style="margin:0">Olá, eu sou o Ciel</h1>
        <p>Desenvolvo automações, UIs e ferramentas de segurança para **laboratórios/escopos autorizados**.  
           Gosto de código limpo, logs, testes e design com propósito.</p>
        <p class="muted">⚠️ Nada de dados sensíveis por aqui. Chaves de API e credenciais ficam sempre em variáveis de ambiente.</p>
        <div style="margin-top:.8rem">
          <a class="btn" href="#projects">Ver projetos</a>
          <a class="btn ghost" href="https://github.com/Ciel-sec" target="_blank" rel="noreferrer">GitHub</a>
        </div>
      </div>
    </div>
  </section>

  <!-- Projetos -->
  <section id="projects">
    <div class="container">
      <h2>Projetos</h2>
      <p class="muted">Alguns exemplos com foco em produtividade, observabilidade e segurança responsável.</p>
      <div class="grid cols-3" style="margin-top:var(--space)">
        <!-- Projeto 1 -->
        <article class="card">
          <h3>Consulta360 (PyQt)</h3>
          <p>Aplicativo desktop para consultas (CPF/CNPJ/Telefone) com tabelas, filtros e exportação.</p>
          <p class="meta">Stack: PyQt (QtWidgets/QSS), requests, pandas, loguru</p>
          <div>
            <span class="tag">Desktop</span>
            <span class="tag">Tabelas</span>
            <span class="tag">Export CSV/JSON</span>
          </div>
        </article>
        <!-- Projeto 2 -->
        <article class="card">
          <h3>StormCentral (Flask)</h3>
          <p>Painel para orquestrar varreduras **autorizadas**, acompanhar logs e gerar relatórios.</p>
          <p class="meta">Stack: Flask, Flask-SocketIO, requests/aiohttp, pandas, pydantic, loguru</p>
          <div>
            <span class="tag">Web</span>
            <span class="tag">Tempo real</span>
            <span class="tag">Relatórios</span>
          </div>
        </article>
        <!-- Projeto 3 -->
        <article class="card">
          <h3>Jarvis (Voz Local)</h3>
          <p>Assistente local com Vosk (STT) e pyttsx3 (TTS), intents plugáveis e respostas com IA.</p>
          <p class="meta">Stack: Vosk, pyttsx3, Python</p>
          <div>
            <span class="tag">Voice</span>
            <span class="tag">Offline</span>
            <span class="tag">Plugins</span>
          </div>
        </article>
      </div>
    </div>
  </section>

  <!-- Códigos (snippets organizados) -->
  <section id="codes">
    <div class="container">
      <h2>Códigos</h2>
      <p class="muted">Trechos reais/representativos, sem segredos expostos. Use variáveis de ambiente e arquivos .env no local.</p>

      <div class="card code-tabs" style="margin-top:var(--space)">
        <div class="tabs" id="tabbar">
          <button class="tab-btn active" data-tab="pyqt">PyQt — tabela & status</button>
          <button class="tab-btn" data-tab="flask">Flask — rota + WebSocket</button>
          <button class="tab-btn" data-tab="voz">Voz — Vosk + pyttsx3</button>
          <button class="tab-btn" data-tab="wrapper">Wrapper seguro (CLI)</button>
        </div>

        <!-- PyQt -->
        <div class="snippet active" id="pyqt">
          <button class="btn copy" data-copy="code-pyqt">Copiar</button>
<pre><code id="code-pyqt"># Consulta360 — PyQt: tabela e status
# (estrutura simplificada para exibição)
from PyQt6 import QtWidgets, QtGui, QtCore
import pandas as pd

class TabelaEnderecos(QtWidgets.QTableView):
    def __init__(self, df: pd.DataFrame):
        super().__init__()
        model = PandasModel(df)
        self.setModel(model)
        self.setAlternatingRowColors(True)
        self.setSelectionBehavior(self.SelectionBehavior.SelectRows)
        self.verticalHeader().setVisible(False)
        self.horizontalHeader().setStretchLastSection(True)

class PandasModel(QtCore.QAbstractTableModel):
    def __init__(self, df):
        super().__init__(); self._df = df
    def rowCount(self, *_): return len(self._df.index)
    def columnCount(self, *_): return len(self._df.columns)
    def data(self, index, role):
        if role in (QtCore.Qt.ItemDataRole.DisplayRole,):
            return str(self._df.iloc[index.row(), index.column()])
    def headerData(self, section, orient, role):
        if role == QtCore.Qt.ItemDataRole.DisplayRole and orient == QtCore.Qt.Orientation.Horizontal:
            return str(self._df.columns[section])

class Main(QtWidgets.QMainWindow):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("Consulta360")
        self.statusBar().showMessage("Pronto")
        df = pd.DataFrame([{"Logradouro":"Rua X","Cidade":"RJ","CEP":"00000-000"}])
        self.setCentralWidget(TabelaEnderecos(df))

if __name__ == "__main__":
    app = QtWidgets.QApplication([])
    w = Main(); w.resize(800,480); w.show()
    app.exec()</code></pre>
        </div>

        <!-- Flask -->
        <div class="snippet" id="flask">
          <button class="btn copy" data-copy="code-flask">Copiar</button>
<pre><code id="code-flask"># StormCentral — Flask: API + mensagens em tempo real (SocketIO)
from flask import Flask, jsonify, request
from flask_socketio import SocketIO, emit
import os

app = Flask(__name__)
app.config["SECRET_KEY"] = os.getenv("APP_SECRET", "dev")  # nunca comitar segredos
socketio = SocketIO(app, cors_allowed_origins="*")

@app.get("/api/health")
def health():
    return jsonify(status="ok")

@app.post("/api/scan")
def start_scan():
    # Exemplo didático: validação básica de escopo/autorização
    payload = request.get_json(force=True)
    target = payload.get("target")
    if not target or not payload.get("authorized"):
        return jsonify(error="escopo ou autorização ausente"), 400
    # sinaliza progresso para a UI
    socketio.emit("progress", {"target": target, "message": "scan iniciado"})
    # ... executar tarefa em worker/filas (celery/rq) ...
    socketio.emit("progress", {"target": target, "message": "scan finalizado"})
    return jsonify(ok=True)

@socketio.on("connect")
def on_connect():
    emit("progress", {"message": "conectado"})
    
if __name__ == "__main__":
    socketio.run(app, host="0.0.0.0", port=8000)</code></pre>
        </div>

        <!-- Voz -->
        <div class="snippet" id="voz">
          <button class="btn copy" data-copy="code-voz">Copiar</button>
<pre><code id="code-voz"># Jarvis — Pipeline de voz local (Vosk STT + pyttsx3 TTS)
import queue, sounddevice as sd, vosk, json, pyttsx3

model = vosk.Model("model-small")        # baixe o modelo offline
recognizer = vosk.KaldiRecognizer(model, 16000)
speaker = pyttsx3.init()

def say(text): speaker.say(text); speaker.runAndWait()

def listen(seconds=4):
    q = queue.Queue()
    def cb(indata, frames, time, status): q.put(bytes(indata))
    with sd.RawInputStream(samplerate=16000, blocksize=8000, dtype="int16", channels=1, callback=cb):
        data = b"".join(q.get() for _ in range(int(16000/8000*seconds)))
    recognizer.AcceptWaveform(data)
    result = json.loads(recognizer.Result())
    return result.get("text","").strip()

if __name__ == "__main__":
    say("Pronto para ouvir.")
    text = listen()
    if "horas" in text: say("Hora de codar, Ciel!")</code></pre>
        </div>

        <!-- Wrapper CLI seguro -->
        <div class="snippet" id="wrapper">
          <button class="btn copy" data-copy="code-wrap">Copiar</button>
<pre><code id="code-wrap">#!/usr/bin/env bash
# Wrapper didático: executa ferramenta CLI somente se o alvo estiver em allowlist.
set -euo pipefail
ALLOWLIST_FILE=".allowlist"  # cada linha: domínio/IP autorizado + ticket/contrato
TARGET="$1"

grep -q "^${TARGET}\b" "$ALLOWLIST_FILE" || {
  echo "Alvo não autorizado. Adicione ao .allowlist com ticket/contrato." >&2
  exit 1
}

# Exemplo de execução (placeholder):
# sqlmap -u "https://${TARGET}/?id=1" --batch --level=1 --risk=1
echo "OK: ${TARGET} autorizado. (execução real comentada por segurança)"</code></pre>
        </div>
      </div>
    </div>
  </section>

  <!-- Blog -->
  <section id="blog">
    <div class="container">
      <h2>Blog</h2>
      <div class="grid cols-3" style="margin-top:var(--space)">
        <article class="card post">
          <img class="thumb" src="https://picsum.photos/800/450?random=11" alt="">
          <h3>Arquitetando uma UI PyQt escalável</h3>
          <p class="muted">Padrão de módulos, QSS e boas práticas para manter a GUI organizada.</p>
          <a class="btn" href="posts/pyqt-ui.html">Ler mais</a>
        </article>
        <article class="card post">
          <img class="thumb" src="https://picsum.photos/800/450?random=12" alt="">
          <h3>Logs estruturados com Loguru</h3>
          <p class="muted">IDs de correlação, níveis e export para auditoria.</p>
          <a class="btn" href="posts/logs-estruturados.html">Ler mais</a>
        </article>
        <article class="card post">
          <img class="thumb" src="https://picsum.photos/800/450?random=13" alt="">
          <h3>Flask + SocketIO: tempo real sem dor</h3>
          <p class="muted">Streaming de eventos de tarefas e UX com feedback imediato.</p>
          <a class="btn" href="posts/flask-socketio.html">Ler mais</a>
        </article>
      </div>
    </div>
  </section>

  <!-- Contato -->
  <section id="contact">
    <div class="container">
      <h2>Contato</h2>
      <form action="https://formspree.io/f/mayvlxgz" method="POST" class="card">
        <input type="text" name="name" placeholder="Seu nome" required>
        <input type="email" name="_replyto" placeholder="Seu e-mail" required>
        <textarea name="message" placeholder="Sua mensagem" required></textarea>
        <span class="notice">Ao enviar, você concorda em ser contatado por e-mail. Nenhum dado sensível deve ser enviado neste formulário.</span>
        <div>
          <button type="submit" class="btn">Enviar</button>
          <a class="btn ghost" href="mailto:contato@exemplo.com">Ou enviar e-mail</a>
        </div>
      </form>
    </div>
  </section>

  <footer>
    <div class="container">© 2025 Ciel Sec — conteúdo técnico e educacional. Atuação apenas em ambientes autorizados.</div>
  </footer>

  <script>
    // Tabs simples + copiar código
    const tabs = document.querySelectorAll('.tab-btn');
    const snips = document.querySelectorAll('.snippet');
    tabs.forEach(btn=>{
      btn.addEventListener('click', ()=>{
        tabs.forEach(b=>b.classList.remove('active'));
        snips.forEach(s=>s.classList.remove('active'));
        btn.classList.add('active');
        document.getElementById(btn.dataset.tab).classList.add('active');
      });
    });
    // copy buttons
    document.querySelectorAll('.copy').forEach(b=>{
      b.addEventListener('click', async ()=>{
        const id = b.getAttribute('data-copy');
        const text = document.getElementById(id).innerText;
        try{ await navigator.clipboard.writeText(text);
          b.textContent='Copiado!'; setTimeout(()=>b.textContent='Copiar',1400);
        }catch{ b.textContent='Erro'; setTimeout(()=>b.textContent='Copiar',1400); }
      });
    });
  </script>
</body>
</html>
