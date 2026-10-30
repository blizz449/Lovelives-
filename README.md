# Profile Picture / Repository Asset

This repository contains image assets used for profile customization or project documentation.

## Asset Details
- **File Name:** street_portrait.png
- **Description:** A scenic street view portrait featuring a woman walking down an urban neighborhood street.
- **Usage:** Ideal for personal GitHub Profile READMEs or landing page assets.

## How to use this in your GitHub README
To display this image in your profile README, use the following Markdown syntax:
```markdown
![Street Portrait](street_portrait.png)
```

Or with custom alignment and sizing:
```html
<img src="street_portrait.png" alt="Street Portrait" width="400" align="center" />
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Griffins & Terry</title>
    <style>
        :root {
            --primary: #ff4d4d;
            --bg-overlay: rgba(10, 10, 10, 0.88);
            --card-bg: rgba(20, 20, 20, 0.7);
            --text-main: #f0f0f0;
            --text-muted: #aaaaaa;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-image: url('background.jpg');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            background-attachment: fixed;
            color: var(--text-main);
            height: 100vh;
            overflow: hidden;
        }

        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(0,0,0,0.95), rgba(15,5,5,0.9));
            display: flex;
            flex-direction: column;
        }

        nav {
            display: flex;
            justify-content: center;
            gap: 20px;
            padding: 20px;
            background: rgba(0, 0, 0, 0.5);
            border-bottom: 1px solid rgba(255, 77, 77, 0.2);
            z-index: 10;
        }

        nav button {
            background: transparent;
            border: 1px solid transparent;
            color: var(--text-muted);
            padding: 10px 20px;
            font-size: 1rem;
            cursor: pointer;
            border-radius: 20px;
            transition: all 0.3s ease;
        }

        nav button.active, nav button:hover {
            color: var(--primary);
            border-color: var(--primary);
            background: rgba(255, 77, 77, 0.1);
            text-shadow: 0 0 8px var(--primary);
        }

        .container {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            overflow-y: auto;
            position: relative;
        }

        .page {
            display: none;
            width: 100%;
            max-width: 650px;
            background: var(--card-bg);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 30px;
            backdrop-filter: blur(12px);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.7);
            animation: fadeIn 0.5s ease forwards;
        }

        .page.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h1, h2 {
            color: var(--primary);
            text-align: center;
            margin-bottom: 20px;
            font-weight: 600;
            letter-spacing: 1px;
        }

        .timer-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
            margin-top: 25px;
        }

        .timer-box {
            background: rgba(0, 0, 0, 0.6);
            border: 1px solid rgba(255, 77, 77, 0.1);
            padding: 15px 5px;
            border-radius: 10px;
            text-align: center;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.5);
        }

        .timer-box .num {
            font-size: 2.2rem;
            font-weight: 700;
            color: #ffffff;
            display: block;
        }

        .timer-box .label {
            font-size: 0.8rem;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 5px;
        }

        .sub-text {
            text-align: center;
            color: var(--text-muted);
            margin-top: 20px;
            font-style: italic;
        }

        .hub-layout {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .game-section, .chat-section {
            background: rgba(0, 0, 0, 0.4);
            border-radius: 12px;
            padding: 20px;
            border: 1px solid rgba(255,255,255,0.05);
        }

        .board {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 8px;
            max-width: 240px;
            margin: 15px auto;
        }

        .cell {
            background: rgba(20, 20, 20, 0.8);
            border: 1px solid rgba(255, 77, 77, 0.2);
            height: 70px;
            border-radius: 8px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.8rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.2s;
        }

        .cell:hover {
            background: rgba(255, 77, 77, 0.1);
        }

        .cell.X { color: var(--primary); }
        .cell.O { color: #4da6ff; }

        .game-status {
            text-align: center;
            margin-bottom: 10px;
            font-weight: 500;
        }

        .btn {
            display: block;
            width: 120px;
            margin: 10px auto 0;
            background: var(--primary);
            border: none;
            color: white;
            padding: 8px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 600;
            transition: opacity 0.2s;
        }

        .btn:hover { opacity: 0.9; }

        .chat-box {
            height: 180px;
            background: rgba(10, 10, 10, 0.8);
            border-radius: 8px;
            padding: 10px;
            overflow-y: auto;
            margin-bottom: 10px;
            border: 1px solid rgba(255,255,255,0.05);
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .msg {
            padding: 6px 12px;
            border-radius: 6px;
            max-width: 85%;
            font-size: 0.9rem;
            line-height: 1.4;
        }

        .msg.me {
            background: rgba(255, 77, 77, 0.2);
            align-self: flex-end;
            border-bottom-right-radius: 2px;
            border: 1px solid rgba(255, 77, 77, 0.3);
        }

        .msg.terry {
            background: rgba(255, 255, 255, 0.1);
            align-self: flex-start;
            border-bottom-left-radius: 2px;
        }

        .msg-meta {
            font-size: 0.7rem;
            color: var(--text-muted);
            margin-bottom: 2px;
            display: block;
        }

        .chat-input-area {
            display: flex;
            gap: 10px;
        }

        .chat-input-area select {
            background: #222;
            color: white;
            border: 1px solid #444;
            border-radius: 6px;
            padding: 8px;
        }

        .chat-input-area input {
            flex: 1;
            background: #151515;
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 6px;
            padding: 8px 12px;
            color: white;
        }

        .chat-input-area input:focus {
            outline: none;
            border-color: var(--primary);
        }
    </style>
</head>
<body>

    <div class="overlay">
        <nav>
            <button id="nav-btn-1" class="active" onclick="switchPage(1)">Our Timeline</button>
            <button id="nav-btn-2" onclick="switchPage(2)">Play & Chat</button>
        </nav>

        <div class="container">
            <div id="page-1" class="page active">
                <h1>Since We Met</h1>
                <div class="sub-text" style="margin-bottom: 20px; font-size: 1.1rem; color: #fff;">Griffins & Terry</div>
                <div class="timer-grid">
                    <div class="timer-box"><span class="num" id="days">00</span><span class="label">Days</span></div>
                    <div class="timer-box"><span class="num" id="hours">00</span><span class="label">Hours</span></div>
                    <div class="timer-box"><span class="num" id="minutes">00</span><span class="label">Mins</span></div>
                    <div class="timer-box"><span class="num" id="seconds">00</span><span class="label">Secs</span></div>
                </div>
                <div class="sub-text">Cherishing every beautiful moment since October 27, 2026.</div>
            </div>

            <div id="page-2" class="page">
                <div class="hub-layout">
                    <div class="game-section">
                        <h2>Play Tic-Tac-Toe</h2>
                        <div class="game-status" id="gameStatus">Griffins' turn! (X)</div>
                        <div class="board" id="board">
                            <div class="cell" onclick="makeMove(0)"></div>
                            <div class="cell" onclick="makeMove(1)"></div>
                            <div class="cell" onclick="makeMove(2)"></div>
                            <div class="cell" onclick="makeMove(3)"></div>
                            <div class="cell" onclick="makeMove(4)"></div>
                            <div class="cell" onclick="makeMove(5)"></div>
                            <div class="cell" onclick="makeMove(6)"></div>
                            <div class="cell" onclick="makeMove(7)"></div>
                            <div class="cell" onclick="makeMove(8)"></div>
                        </div>
                        <button class="btn" onclick="resetGame()">Reset Game</button>
                    </div>

                    <div class="chat-section">
                        <h2>Our Message Board</h2>
                        <div class="chat-box" id="chatBox"></div>
                        <div class="chat-input-area">
                            <select id="userSelect">
                                <option value="me">Griffins</option>
                                <option value="terry">Terry</option>
                            </select>
                            <input type="text" id="chatInput" placeholder="Type a message..." onkeypress="handleKeyPress(event)">
                            <button class="btn" style="width: auto; margin: 0; padding: 8px 15px;" onclick="sendMessage()">Send</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        function switchPage(pageNum) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.querySelectorAll('nav button').forEach(b => b.classList.remove('active'));

            document.getElementById(`page-${pageNum}`).classList.add('active');
            document.getElementById(`nav-btn-${pageNum}`).classList.add('active');
        }

        const targetDate = new Date("2026-10-27T00:00:00").getTime();

        function updateTimer() {
            const now = new Date().getTime();
            const difference = now - targetDate;

            if (difference < 0) return;

            const days = Math.floor(difference / (1000 * 60 * 60 * 24));
            const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((difference % (1000 * 60)) / 1000);

            document.getElementById("days").innerText = String(days).padStart(2, '0');
            document.getElementById("hours").innerText = String(hours).padStart(2, '0');
            document.getElementById("minutes").innerText = String(minutes).padStart(2, '0');
            document.getElementById("seconds").innerText = String(seconds).padStart(2, '0');
        }

        setInterval(updateTimer, 1000);
        updateTimer();

        let boardState = ["", "", "", "", "", "", "", "", ""];
        let currentPlayer = "X";
        let gameActive = true;

        function getWinner(board) {
            const wins = [
                [0, 1, 2], [3, 4, 5], [6, 7, 8],
                [0, 3, 6], [1, 4, 7], [2, 5, 8],
                [0, 4, 8], [2, 4, 6]
            ];

            for (const [a, b, c] of wins) {
                if (board[a] && board[a] === board[b] && board[a] === board[c]) {
                    return board[a];
                }
            }

            return null;
        }

        function makeMove(index) {
            if (boardState[index] !== "" || !gameActive) return;

            boardState[index] = currentPlayer;
            const cells = document.querySelectorAll('.cell');
            cells[index].innerText = currentPlayer;
            cells[index].classList.add(currentPlayer);

            const winner = getWinner(boardState);

            if (winner) {
                gameActive = false;
                document.getElementById("gameStatus").innerText =
                    winner === "X" ? "🎉 Griffins Wins!" : "🎉 Terry Wins!";
                return;
            }

            if (!boardState.includes("")) {
                gameActive = false;
                document.getElementById("gameStatus").innerText = "🤝 It's a Draw!";
                return;
            }

            currentPlayer = currentPlayer === "X" ? "O" : "X";
            document.getElementById("gameStatus").innerText =
                currentPlayer === "O" ? "Terry's turn! (O)" : "Griffins' turn! (X)";
        }

        function resetGame() {
            boardState = ["", "", "", "", "", "", "", "", ""];
            currentPlayer = "X";
            gameActive = true;
            document.getElementById("gameStatus").innerText = "Griffins' turn! (X)";
            document.querySelectorAll('.cell').forEach(cell => {
                cell.innerText = "";
                cell.className = "cell";
            });
        }

        const STORAGE_KEY = 'terry_chat_hub';
        const defaultMessages = [
            { sender: 'terry', text: 'Welcome to our space! ❤️' }
        ];

        function getMessages() {
            try {
                const saved = localStorage.getItem(STORAGE_KEY);
                return saved ? JSON.parse(saved) : defaultMessages;
            } catch (error) {
                return defaultMessages;
            }
        }

        let messages = getMessages();

        function renderMessages() {
            const chatBox = document.getElementById('chatBox');
            chatBox.innerHTML = '';

            messages.forEach(msg => {
                const div = document.createElement('div');
                div.className = `msg ${msg.sender}`;

                const meta = document.createElement('span');
                meta.className = 'msg-meta';
                meta.innerText = msg.sender === 'terry' ? 'Terry' : 'Griffins';

                div.appendChild(meta);
                div.append(msg.text);
                chatBox.appendChild(div);
            });

            chatBox.scrollTop = chatBox.scrollHeight;
        }

        function sendMessage() {
            const input = document.getElementById('chatInput');
            const sender = document.getElementById('userSelect').value;
            const text = input.value.trim();

            if (!text) return;

            messages.push({ sender, text });

            try {
                localStorage.setItem(STORAGE_KEY, JSON.stringify(messages));
            } catch (error) {
                // Ignore storage issues silently
            }

            input.value = '';
            renderMessages();
        }

        function handleKeyPress(e) {
            if (e.key === 'Enter') sendMessage();
        }

        renderMessages();
    </script>
</body>
</html>
