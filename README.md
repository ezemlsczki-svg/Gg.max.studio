<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GG MAX STUDIO | BOSS KANA EDITION</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Rajdhani:wght@300;500;700&display=swap');

        :root {
            --cyan: #00f2ff;
            --dark-bg: #01080e;
            --glass: rgba(0, 242, 255, 0.05);
            --glow: 0 0 15px rgba(0, 242, 255, 0.5);
        }

        body, html {
            margin: 0; padding: 0;
            background: var(--dark-bg);
            color: var(--cyan);
            font-family: 'Rajdhani', sans-serif;
            height: 100vh; overflow: hidden;
        }

        /* FUNDO COM GRID DINÂMICO */
        .grid-bg {
            position: fixed; width: 100%; height: 100%;
            background-image: linear-gradient(var(--glass) 1px, transparent 1px), linear-gradient(90deg, var(--glass) 1px, transparent 1px);
            background-size: 40px 40px; z-index: -1;
        }

        /* LOGIN SCREEN */
        #login-screen {
            display: flex; justify-content: center; align-items: center; height: 100vh;
            background: radial-gradient(circle, #061b2e 0%, #01080e 100%);
            z-index: 1000; position: relative;
        }

        .login-card {
            border: 2px solid var(--cyan); padding: 40px;
            background: rgba(0,0,0,0.9); box-shadow: var(--glow);
            text-align: center; clip-path: polygon(15% 0, 100% 0, 100% 85%, 85% 100%, 0 100%, 0 15%);
        }

        input {
            background: rgba(0, 242, 255, 0.1); border: 1px solid var(--cyan);
            color: white; padding: 12px; margin: 20px 0; width: 100%; font-family: 'Orbitron';
        }

        /* BARRA SUPERIOR (HEADER) */
        #header {
            display: none; position: fixed; top: 0; width: 100%; height: 60px;
            background: rgba(0, 15, 30, 0.8); backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--cyan); align-items: center; padding: 0 20px; z-index: 100;
        }

        .menu-btn {
            font-size: 30px; cursor: pointer; color: var(--cyan); transition: 0.3s;
        }

        .menu-btn:hover { text-shadow: var(--glow); }

        /* MENU LATERAL (SIDEBAR) FECHADO */
        .sidebar {
            position: fixed; left: -280px; top: 0; width: 280px; height: 100%;
            background: rgba(1, 8, 14, 0.95); border-right: 2px solid var(--cyan);
            transition: 0.4s; z-index: 200; padding-top: 80px;
        }

        .sidebar.open { left: 0; box-shadow: 20px 0 50px rgba(0,0,0,0.9); }

        .nav-item {
            padding: 20px; border-bottom: 1px solid var(--glass);
            cursor: pointer; font-family: 'Orbitron'; font-size: 14px; transition: 0.3s;
        }

        .nav-item:hover { background: var(--glass); padding-left: 30px; color: white; }

        /* ÁREA DE CONTEÚDO */
        #main-site { display: none; padding-top: 80px; height: 100vh; overflow-y: auto; }

        .container { max-width: 900px; margin: 0 auto; padding: 20px; }

        .card {
            background: var(--glass); border: 1px solid var(--border);
            padding: 25px; margin-bottom: 20px; border-left: 5px solid var(--cyan);
            animation: slideIn 0.5s ease-out;
        }

        @keyframes slideIn { from { opacity: 0; transform: translateX(-50px); } to { opacity: 1; transform: translateX(0); } }

        .app-tag {
            display: inline-block; background: var(--cyan); color: black;
            padding: 3px 10px; font-weight: bold; font-size: 12px; margin: 5px;
        }

        .discord-btn {
            display: block; text-align: center; background: #5865F2; color: white;
            padding: 20px; text-decoration: none; font-weight: bold; border-radius: 5px;
            margin-top: 40px; font-family: 'Orbitron'; box-shadow: 0 5px 20px rgba(88, 101, 242, 0.4);
        }

        .close-menu { position: absolute; top: 20px; right: 20px; cursor: pointer; font-size: 20px; }

    </style>
</head>
<body>

    <div class="grid-bg"></div>

    <div id="login-screen">
        <div class="login-card">
            <h2 style="font-family: 'Orbitron';">SISTEMA BOSS KANA</h2>
            <p style="font-size: 12px; letter-spacing: 2px;">INSIRA A CHAVE DE ACESSO</p>
            <input type="password" id="pass" placeholder="••••••••">
            <button onclick="unlock()" style="background: var(--cyan); border:none; padding: 12px 40px; cursor:pointer; font-weight:bold; font-family: 'Orbitron';">AUTENTICAR</button>
        </div>
    </div>

    <div id="header">
        <div class="menu-btn" onclick="toggleMenu()">☰</div>
        <div style="margin-left: 20px; font-family: 'Orbitron'; font-weight: bold; letter-spacing: 2px;">GG MAX STUDIO <span style="color:white">V4.0</span></div>
    </div>

    <div class="sidebar" id="sidebar">
        <div class="close-menu" onclick="toggleMenu()">✖</div>
        <div class="nav-item" onclick="showTab('home')">🏠 INÍCIO</div>
        <div class="nav-item" onclick="showTab('dev')">🔨 CRIAÇÃO DE JOGOS</div>
        <div class="nav-item" onclick="showTab('scripts')">📜 SCRIPTS & ROBLOX</div>
        <div class="nav-item" onclick="showTab('apps')">🛠️ TOOLS & APPS</div>
    </div>

    <div id="main-site">
        <div class="container">
            
            <div id="home" class="tab">
                <div class="card">
                    <h1>SISTEMA OPERACIONAL: <span style="color:white">BOSS KANA</span></h1>
                    <p>O <strong>GG MAX STUDIO</strong> é o epicentro do desenvolvimento avançado. Aqui, você não apenas aprende a programar, você aprende a dominar o sistema.</p>
                </div>
            </div>

            <div id="dev" class="tab" style="display:none;">
                <div class="card">
                    <h2>🎮 CRIAÇÃO DE JOGOS</h2>
                    <p>Ensinamos do zero ao profissional como criar mundos digitais:</p>
                    <ul>
                        <li>Arquitetura de Mapas</li>
                        <li>Física e Mecânicas Avançadas</li>
                        <li>Interface de Usuário (UI/UX) Futurista</li>
                        <li>Otimização para Performance</li>
                    </ul>
                </div>
            </div>

            <div id="scripts" class="tab" style="display:none;">
                <div class="card">
                    <h2>🟦 ROBLOX & SCRIPTS</h2>
                    <p>Domine o <strong>Luau</strong> e crie sistemas que ninguém consegue parar:</p>
                    <div class="app-tag">ROBLOX STUDIO</div> <div class="app-tag">LUAU</div> <div class="app-tag">EXPLOITS</div>
                    <p style="margin-top:15px;">Desenvolva Scripts de Admin, Sistemas de Inventário e Automações complexas para o Roblox.</p>
                </div>
                <div class="card">
                    <h2>🐍 PYTHON & HACKING</h2>
                    <p>Aprenda a linguagem mais poderosa do mundo para automação e segurança.</p>
                </div>
            </div>

            <div id="apps" class="tab" style="display:none;">
                <div class="card">
                    <h2>🛠️ SOFTWARE STACK</h2>
                    <p>Os apps que usamos para dominar o código:</p>
                    <div class="app-tag">VS CODE (Main Editor)</div>
                    <div class="app-tag">PYTHON 3.12</div>
                    <div class="app-tag">GIT & GITHUB</div>
                    <div class="app-tag">KALI TOOLS</div>
                </div>
            </div>

            <a href="https://discord.gg/T8h75tZst" class="discord-btn" target="_blank">
                CONECTAR AO DISCORD OFICIAL
            </a>

        </div>
    </div>

    <script>
        function unlock() {
            const p = document.getElementById('pass').value;
            if(p === "6666") {
                document.getElementById('login-screen').style.display = 'none';
                document.getElementById('header').style.display = 'flex';
                document.getElementById('main-site').style.display = 'block';
            } else { alert("ACESSO NEGADO: CHAVE INVÁLIDA"); }
        }

        function toggleMenu() {
            document.getElementById('sidebar').classList.toggle('open');
        }

        function showTab(tabId) {
            const tabs = document.querySelectorAll('.tab');
            tabs.forEach(t => t.style.display = 'none');
            document.getElementById(tabId).style.display = 'block';
            toggleMenu(); // Fecha o menu ao clicar
        }
    </script>
</body>
</html>
