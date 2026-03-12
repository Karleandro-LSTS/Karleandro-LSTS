<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sytem_Override // Portfolio</title>
    <style>
        :root {
            --neon-green: #39ff14;
            --dark-bg: #0a0a0a;
            --retro-pink: #ff007f;
            --terminal-font: 'Courier New', Courier, monospace;
        }

        body {
            background-color: var(--dark-bg);
            color: var(--neon-green);
            font-family: var(--terminal-font);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            overflow-x: hidden;
            text-transform: uppercase;
        }

        /* Efeito de scanline (linhas de TV antiga) */
        body::before {
            content: " ";
            display: block;
            position: absolute;
            top: 0; left: 0; bottom: 0; right: 0;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), 
                        linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
            z-index: 2;
            background-size: 100% 2px, 3px 100%;
            pointer-events: none;
        }

        .container {
            width: 80%;
            max-width: 800px;
            border: 2px solid var(--neon-green);
            padding: 20px;
            box-shadow: 0 0 15px var(--neon-green);
            position: relative;
            background: rgba(0, 20, 0, 0.9);
        }

        .header {
            border-bottom: 2px solid var(--neon-green);
            margin-bottom: 20px;
            padding-bottom: 10px;
        }

        .glitch {
            font-size: 2.5rem;
            font-weight: bold;
            text-shadow: 2px 2px var(--retro-pink);
            animation: glitch-anim 2s infinite;
        }

        @keyframes glitch-anim {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }

        .stats-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-top: 20px;
        }

        .card {
            border: 1px solid var(--neon-green);
            padding: 10px;
            transition: all 0.3s;
        }

        .card:hover {
            background: var(--neon-green);
            color: var(--dark-bg);
            cursor: crosshair;
        }

        .loading-bar {
            width: 100%;
            height: 10px;
            border: 1px solid var(--neon-green);
            margin-top: 5px;
        }

        .progress {
            height: 100%;
            background: var(--neon-green);
            animation: load 3s infinite alternate;
        }

        @keyframes load {
            0% { width: 0%; }
            100% { width: 85%; }
        }

        .blink {
            animation: blinker 1s linear infinite;
        }

        @keyframes blinker {
            50% { opacity: 0; }
        }
    </style>
</head>
<body>

<div class="container">
    <div class="header">
        <div class="glitch">> DATA_SCIENTIST_INIT</div>
        <p>Status: <span class="blink">Online</span> | Location: Brazil_Node</p>
    </div>

    <div class="content">
        <p>// BIOGRAFIA:</p>
        <p>Estudante de Ciência de Dados explorando as profundezas do Python e as camadas do HTML. Construindo o futuro, um commit por vez.</p>
        
        <div class="stats-grid">
            <div class="card">
                > LINGUAGENS
                <ul>
                    <li>Python (Scikit-Learn/Pandas)</li>
                    <li>HTML5 / CSS3</li>
                    <li>SQL Base</li>
                </ul>
            </div>
            <div class="card">
                > SISTEMA_INFO
                <p>Nível: Iniciante++</p>
                <p>Projetos: 0 (Aguardando Deploy...)</p>
                <div class="loading-bar"><div class="progress"></div></div>
            </div>
        </div>
    </div>

    <div style="margin-top: 30px; font-size: 0.8rem; color: var(--retro-pink);">
        [SISTEMA PROTEGIDO POR PROTOCOLO RETRO-WAVE v.84]
    </div>
</div>

</body>
</html>
