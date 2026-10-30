<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Griffins & Terry - Forever ♾️</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&family=Great+Vibes&display=swap" rel="stylesheet">

    <style>
        :root { --primary:#ff4d6d; --primary-glow:rgba(255,77,109,0.5); --card-bg:rgba(18,18,22,0.75); }
        *{box-sizing:border-box;margin:0;padding:0;font-family:'Poppins',sans-serif;}
        body{background:#000;background-image:url('https://images.unsplash.com/photo-1518199266791-5375a83190b7?q=80&w=1920');background-size:cover;background-position:center;background-attachment:fixed;color:#f5f5f5;min-height:100vh;overflow-x:hidden;}
        .hearts{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:1;overflow:hidden;}
        .heart{position:absolute;color:var(--primary);animation:floatUp linear infinite;opacity:0.7;}
        @keyframes floatUp{0%{transform:translateY(100vh) scale(0) rotate(0deg);opacity:0;}10%{opacity:0.8;}90%{opacity:0.8;}100%{transform:translateY(-10vh) scale(1.5) rotate(360deg);opacity:0;}}
        .overlay{position:relative;min-height:100vh;background:linear-gradient(135deg,rgba(0,0,0,0.92),rgba(20,5,10,0.85));display:flex;flex-direction:column;z-index:2;}
        nav{display:flex;justify-content:center;gap:15px;padding:18px;background:rgba(0,0,0,0.6);backdrop-filter:blur(10px);border-bottom:1px solid rgba(255,77,109,0.2);position:sticky;top:0;z-index:10;}
        nav button{background:transparent;border:1px solid rgba(255,255,255,0.15);color:#aaa;padding:10px 22px;border-radius:25px;cursor:pointer;transition:all 0.3s;}
        nav button.active,nav button:hover{color:var(--primary);border-color:var(--primary);background:rgba(255,77,109,0.12);box-shadow:0 0 15px var(--primary-glow);}
        .container{flex:1;display:flex;justify-content:center;align-items:flex-start;padding:25px 15px;}
        .page{display:none;width:100%;max-width:680px;background:var(--card-bg);border:1px solid rgba(255,255,255,0.08);border-radius:20px;padding:32px;backdrop-filter:blur(15px);box-shadow:0 10px 40px rgba(0,0,0,0.8),0 0 0 1px rgba(255,77,109,0.1);animation:fadeIn 0.6s ease;}
        .page.active{display:block;}
        @keyframes fadeIn{from{opacity:0;transform:translateY(15px) scale(0.98);}to{opacity:1;transform:translateY(0) scale(1);}}
        h1{font-family:'Great Vibes',cursive;font-size:3.2rem;color:var(--primary);text-align:center;text-shadow:0 0 20px var(--primary-glow);}
        h2{font-size:1.1rem;letter-spacing:2px;text-transform:uppercase;color:var(--primary);text-align:center;margin-bottom:20px;opacity:0.9;}
        .couple-name{text-align:center;font-size:1.3rem;margin:5px 0 25px;letter-spacing:1px;}
        .couple-name span{color:var(--primary);}
        .timer-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-top:15px;}
        .timer-box{background:linear-gradient(180deg,rgba(30,30,30,0.8),rgba(0,0,0,0.8));border:1px solid rgba(255,77,109,0.15);padding:16px 5px;border-radius:14px;text-align:center;box-shadow:inset 0 1px 0 rgba(255,255,255,0.05);}
        .timer-box .num{font-size:2rem;font-weight:700;color:#fff;display:block;}
        .timer-box .label{font-size:0.7rem;color:#888;text-transform:uppercase;letter-spacing:1.5px;margin-top:4px;}
        .love-quote{text-align:center;margin-top:28px;font-style:italic;color:#bbb;line-height:1.6;font-size:0.95rem;}
        .love-quote b{color:#fff;font-style:normal;}
        .board{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;max-width:260px;margin:15px auto;}
        .cell{background:rgba(255,255,255,0.04);border:1px solid rgba(255,77,109,0.2);height:75px;border-radius:12px;display:flex;justify-content:center;align-items:center;font-size:2rem;font-weight:bold;cursor:pointer;transition:all 0.2s;}
        .cell:hover{background:rgba(255,77,109,0.1);transform:scale(1.03);}
        .cell.X{color:var(--primary);text-shadow:0 0 10px var(--primary-glow);}
        .cell.O{color:#6bb8ff;text-shadow:0 0 10px rgba(107,184,255,0.5);}
        .game-status{text-align:center;margin-bottom:10px;font-weight:500;min-height:24px;}
        .btn{display:block;width:140px;margin:12px auto 0;background:linear-gradient(135deg,var(--primary),#ff2d55);border:none;color:white;padding:10px;border-radius:25px;cursor:pointer;font-weight:600;box-shadow:0 5px 15px rgba(255,77,109,0.4);transition:transform 0.2s;}
        .btn:hover{transform:translateY(-2px);}
        .chat-box{height:200px;background:rgba(0,0,0,0.6);border-radius:12px;padding:12px;overflow-y:auto;margin-bottom:12px;border:1px solid rgba(255,255,255,0.06);display:flex;flex-direction:column;gap:10px;}
        .msg{padding:8px 14px;border-radius:14px;max-width:85%;font-size:0.9rem;line-height:1.4;animation:msgIn 0.3s;}
        @keyframes msgIn{from{opacity:0;transform:translateY(5px);}to{opacity:1;transform:translateY(0);}}
        .msg.me{background:linear-gradient(135deg,rgba(255,77,109,0.3),rgba(255,45,85,0.2));align-self:flex-end;border-bottom-right-radius:4px;border:1px solid rgba(255,77,109,0.3);}
        .msg.terry{background:rgba(255,255,255,0.08);align-self:flex-start;border-bottom-left-radius:4px;}
        .msg-meta{font-size:0.68rem;color:#999;margin-bottom:3px;display:block;font-weight:600;}
        .chat-input-area{display:flex;gap:8px;}
        .chat-input-area select{background:#1a1a1a;color:white;border:1px solid #333;border-radius:20px;padding:8px 10px;}
        .chat-input-area input{flex:1;background:#151515;border:1px solid rgba(255,255,255,0.1);border-radius:20px;padding:10px 14px;color:white;}
        .chat-input-area input:focus{outline:none;border-color:var(--primary);}
        .music-btn{position:fixed;bottom:20px;right:20px;z-index:20;background:var(--card-bg);border:1px solid rgba(255,77,109,0.3);width:48px;height:48px;border-radius:50%;display:flex;justify-content:center;align-items:center;cursor:pointer;backdrop-filter:blur(10px);font-size:1.3rem;}
        @media (max-width:600px){.timer-grid{gap:8px;}.timer-box .num{font-size:1.6rem;}h1{font-size:2.6rem;}.page{padding:22px 16px;}}
    </style>
</head>
<body>
<div class="hearts" id="hearts"></div>
<div class="music-btn" id="musicBtn" onclick="toggleMusic()">🎵</div>
<audio id="bgMusic" loop>
  <source src="https://cdn.pixabay.com/download/audio/2022/03/24/audio_1234.mp3?filename=romantic-piano-110831.mp3" type="audio/mpeg">
</audio>
<div class="overlay">
    <nav>
        <button id="nav-btn-1" class="active" onclick="switchPage(1)">❤️ Timeline</button>
        <button id="nav-btn-2" onclick="switchPage(2)">🎮 Play & Chat</button>
    </nav>
    <div class="container">
        <div id="page-1" class="page active">
            <h1>Forever Us</h1>
            <div class="couple-name"><span>Griffins</span> & <span>Terry</span></div>
            <div class="timer-grid">
                <div class="timer-box"><span class="num" id="days">00</span><span class="label">Days</span></div>
                <div class="timer-box"><span class="num" id="hours">00</span><span class="label">Hours</span></div>
                <div class="timer-box"><span class="num" id="minutes">00</span><span class="label">Mins</span></div>
                <div class="timer-box"><span class="num" id="seconds">00</span><span class="label">Secs</span></div>
            </div>
            <div class="love-quote">Since <b>October 27, 2026</b> — every second with you is my favorite.<br><br>"In all the world, there is no heart for me like yours. In all the world, there is no love for you like mine."<br><span style="color:var(--primary);">— Griffins to Terry</span></div>
            <button class="btn" onclick="switchPage(2)" style="margin-top:22px;width:180px;">Send Her a Message 💌</button>
        </div>

        <div id="page-2" class="page">
            <div style="display:flex;flex-direction:column;gap:28px;">
                <div>
                    <h2>Tic-Tac-Toe • Love Edition</h2>
                    <div class="game-status" id="gameStatus">Griffins' turn! ❌</div>
                    <div class="board" id="board">
                        <div class="cell" onclick="makeMove(0)"></div><div class="cell" onclick="makeMove(1)"></div><div class="cell" onclick="makeMove(2)"></div>
                        <div class="cell" onclick="makeMove(3)"></div><div class="cell" onclick="makeMove(4)"></div><div class="cell" onclick="makeMove(5)"></div>
                        <div class="cell" onclick="makeMove(6)"></div><div class="cell" onclick="makeMove(7)"></div><div class="cell" onclick="makeMove(8)"></div>
                    </div>
                    <button class="btn" onclick="resetGame()">New Game</button>
                </div>

                <div>
                    <h2>Our Private Space</h2>
                    <div class="chat-box" id="chatBox"></div>
                    <div class="chat-input-area">
                        <select id="userSelect">
                            <option value="me">Griffins</option>
                            <option value="terry">Terry</option>
                        </select>
                        <input type="text" id="chatInput" placeholder="Write something sweet..." onkeypress="handleKeyPress(event)">
                        <button id="sendBtn" class="btn" style="width:auto;margin:0;padding:10px 18px;border-radius:20px;">Send</button>
                    </div>
                    <p style="text-align:center;font-size:0.7rem;color:#666;margin-top:8px;">Messages sync in real time with Firebase ❤️</p>
                </div>
            </div>
        </div>
    </div>
</div>

<script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js";
    import {
        getFirestore,
        collection,
        addDoc,
        onSnapshot,
        query,
        orderBy,
        serverTimestamp
    } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore.js";

    const firebaseConfig = {
        apiKey: "AIzaSyB8O4NJBFPuIrszbuWREX0B6tTcqW-yqs8",
        authDomain: "terry-love.firebaseapp.com",
        projectId: "terry-love",
        storageBucket: "terry-love.firebasestorage.app",
        messagingSenderId: "761934904733",
        appId: "1:761934904733:web:08847072e2d57c3b348374",
        measurementId: "G-W45W5CVP0F"
    };

    const app = initializeApp(firebaseConfig);
    const db = getFirestore(app);
    const messagesRef = collection(db, "terry-love");

    function switchPage(n){
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        document.querySelectorAll('nav button').forEach(b => b.classList.remove('active'));
        document.getElementById('page-' + n).classList.add('active');
        document.getElementById('nav-btn-' + n).classList.add('active');
    }

    const targetDate = new Date("2026-10-27T00:00:00").getTime();
    function updateTimer(){
        const diff = Date.now() - targetDate;
        if(diff < 0) return;
        const d = Math.floor(diff / (1000 * 60 * 60 * 24));
        const h = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const m = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
        const s = Math.floor((diff % (1000 * 60)) / 1000);

        document.getElementById("days").innerText = String(d).padStart(2, '0');
        document.getElementById("hours").innerText = String(h).padStart(2, '0');
        document.getElementById("minutes").innerText = String(m).padStart(2, '0');
        document.getElementById("seconds").innerText = String(s).padStart(2, '0');
    }
    setInterval(updateTimer, 1000);
    updateTimer();

    function createHeart(){
        const container = document.getElementById('hearts');
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.innerHTML = '❤';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.fontSize = (Math.random() * 20 + 12) + 'px';
        heart.style.animationDuration = (Math.random() * 5 + 4) + 's';
        container.appendChild(heart);
        setTimeout(() => heart.remove(), 8000);
    }
    setInterval(createHeart, 400);

    let boardState = ["", "", "", "", "", "", "", "", ""];
    let currentPlayer = "X";
    let gameActive = true;

    function getWinner(b){
        const wins = [[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,8],[2,4,6]];
        for (const [a, b1, c] of wins) {
            if (b[a] && b[a] === b[b1] && b[a] === b[c]) return b[a];
        }
        return null;
    }

    function makeMove(i){
        if (boardState[i] !== "" || !gameActive) return;

        boardState[i] = currentPlayer;
        const cells = document.querySelectorAll('.cell');
        cells[i].innerText = currentPlayer;
        cells[i].classList.add(currentPlayer);

        const winner = getWinner(boardState);
        if (winner) {
            gameActive = false;
            document.getElementById("gameStatus").innerText = winner === "X" ? "🎉 Griffins Wins! ❤️" : "🎉 Terry Wins! ❤️";
            for (let k = 0; k < 15; k++) setTimeout(createHeart, k * 100);
            return;
        }

        if (!boardState.includes("")) {
            gameActive = false;
            document.getElementById("gameStatus").innerText = "🤝 Draw! You both win love ❤️";
            return;
        }

        currentPlayer = currentPlayer === "X" ? "O" : "X";
        document.getElementById("gameStatus").innerText = currentPlayer === "O" ? "Terry's turn! ⭕" : "Griffins' turn! ❌";
    }

    function resetGame(){
        boardState = ["", "", "", "", "", "", "", "", ""];
        currentPlayer = "X";
        gameActive = true;
        document.getElementById("gameStatus").innerText = "Griffins' turn! ❌";
        document.querySelectorAll('.cell').forEach(c => {
            c.innerText = "";
            c.className = "cell";
        });
    }

    function renderMessages(snapshot) {
        const box = document.getElementById("chatBox");
        box.innerHTML = "";

        if (!snapshot || snapshot.empty) {
            const div = document.createElement("div");
            div.className = "msg terry";
            const meta = document.createElement("span");
            meta.className = "msg-meta";
            meta.textContent = "Terry 💖";
            div.appendChild(meta);
            div.append("Welcome to our forever space! ❤️ I love you!");
            box.appendChild(div);
            return;
        }

        snapshot.forEach((docSnap) => {
            const msg = docSnap.data();
            const div = document.createElement("div");
            div.className = "msg " + msg.sender;

            const meta = document.createElement("span");
            meta.className = "msg-meta";
            meta.textContent = msg.sender === "terry" ? "Terry 💖" : "Griffins 💙";

            div.appendChild(meta);
            div.append(msg.text);
            box.appendChild(div);
        });

        box.scrollTop = box.scrollHeight;
    }

    const q = query(messagesRef, orderBy("createdAt", "asc"));
    onSnapshot(q, (snapshot) => {
        renderMessages(snapshot);
    });

    async function sendMessage() {
        const input = document.getElementById("chatInput");
        const sender = document.getElementById("userSelect").value;
        const text = input.value.trim();

        if (!text) return;

        try {
            await addDoc(messagesRef, {
                sender,
                text,
                createdAt: serverTimestamp()
            });

            input.value = "";
            createHeart();
        } catch (error) {
            console.error("Error sending message:", error);
            alert("Message could not be sent. Check your Firebase setup.");
        }
    }

    function handleKeyPress(e) {
        if (e.key === "Enter") {
            sendMessage();
        }
    }

    document.getElementById("sendBtn").addEventListener("click", sendMessage);

    let playing = false;
    function toggleMusic(){
        const audio = document.getElementById('bgMusic');
        const btn = document.getElementById('musicBtn');
        if (!playing) {
            audio.play().catch(() => {});
            btn.innerText = '🔊';
            playing = true;
        } else {
            audio.pause();
            btn.innerText = '🎵';
            playing = false;
        }
    }
</script>
</body>
</html>
