# pixel-rUSH
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Colorful Gaming Hub</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            font-family: 'Segoe UI', Arial, sans-serif;
            color: #fff;
            margin: 0;
            padding: 0;
        }
        header {
            background: #0f2027;
            background: linear-gradient(90deg, #0f2027 0%, #2c5364 100%);
            padding: 20px 0;
            text-align: center;
            font-size: 2.5rem;
            letter-spacing: 3px;
            font-weight: bold;
            color: #f9d423;
            box-shadow: 0 2px 8px #0003;
        }
        nav {
            display: flex;
            justify-content: center;
            gap: 20px;
            background: #243b55;
            padding: 15px 0;
        }
        nav button {
            background: #f7971e;
            color: #fff;
            border: none;
            border-radius: 8px;
            padding: 12px 28px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: background 0.2s, transform 0.2s;
            font-weight: 600;
        }
        nav button:hover, nav button.active {
            background: #ffd200;
            color: #243b55;
            transform: scale(1.08);
        }
        main {
            margin: 30px auto;
            max-width: 700px;
            background: #243b55cc;
            border-radius: 20px;
            box-shadow: 0 4px 24px #0004;
            padding: 32px;
            min-height: 400px;
        }
        .hidden {
            display: none;
        }
        .game-title {
            text-align: center;
            font-size: 2rem;
            color: #f7971e;
            margin-bottom: 16px;
        }
        /* For Tic Tac Toe */
        .ttt-board {
            display: grid;
            grid-template-columns: repeat(3, 80px);
            grid-gap: 10px;
            justify-content: center;
            margin-bottom: 18px;
        }
        .ttt-cell {
            width: 80px;
            height: 80px;
            background: #f7971e;
            color: #fff;
            font-size: 2.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            border-radius: 10px;
            box-shadow: 0 2px 8px #0002;
            transition: background 0.15s;
        }
        .ttt-cell:hover {
            background: #ffd200;
            color: #243b55;
        }
        /* For Snake */
        #snake-canvas {
            background: #222d3a;
            display: block;
            margin: 0 auto 16px auto;
            border-radius: 12px;
            box-shadow: 0 2px 10px #0005;
        }
        /* For Memory */
        .memory-board {
            display: grid;
            grid-template-columns: repeat(4, 60px);
            gap: 12px;
            justify-content: center;
            margin-bottom: 18px;
        }
        .memory-card {
            width: 60px;
            height: 80px;
            background: #f7971e;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: #fff;
            cursor: pointer;
            user-select: none;
            box-shadow: 0 1px 6px #0002;
        }
        .memory-card.flipped, .memory-card.matched {
            background: #ffd200;
            color: #243b55;
        }
        /* For Rock Paper Scissors */
        .rps-btns {
            display: flex;
            justify-content: center;
            gap: 24px;
            margin-bottom: 18px;
        }
        .rps-btn {
            background: #f7971e;
            color: #fff;
            border: none;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            font-size: 1.5rem;
            cursor: pointer;
            transition: background 0.18s, transform 0.15s;
        }
        .rps-btn:hover {
            background: #ffd200;
            color: #243b55;
            transform: scale(1.1);
        }
        /* For Number Guess */
        .number-guess-input {
            width: 70px;
            font-size: 1.3rem;
            padding: 7px;
            border-radius: 6px;
            border: none;
            margin-right: 10px;
        }
        .number-guess-btn {
            padding: 8px 18px;
            border-radius: 7px;
            border: none;
            background: #f7971e;
            color: #fff;
            font-size: 1rem;
            cursor: pointer;
            font-weight: 600;
        }
        /* For Wordle */
        .wordle-board {
            display: grid;
            grid-template-rows: repeat(6, 1fr);
            gap: 7px;
            margin: 0 auto 20px;
            width: max-content;
        }
        .wordle-row {
            display: grid;
            grid-template-columns: repeat(5, 48px);
            gap: 7px;
        }
        .wordle-cell {
            width: 48px;
            height: 48px;
            background: #f7971e;
            color: #fff;
            font-size: 2rem;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 7px;
            text-transform: uppercase;
            font-weight: bold;
        }
        .wordle-cell.correct {
            background: #6aaa64;
        }
        .wordle-cell.present {
            background: #c9b458;
        }
        .wordle-cell.absent {
            background: #787c7e;
        }
        .wordle-input-row {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            gap: 7px;
        }
        .wordle-input {
            width: 48px;
            font-size: 2rem;
            text-align: center;
            border-radius: 7px;
            border: 2px solid #ffd200;
            margin-right: 4px;
            background: #fff;
            color: #243b55;
        }
        .wordle-submit-btn {
            padding: 8px 16px;
            border-radius: 7px;
            border: none;
            background: #f7971e;
            color: #fff;
            font-size: 1rem;
            cursor: pointer;
            font-weight: 600;
        }
        /* Misc */
        .center {
            text-align: center;
        }
        .msg {
            background: #ffd200;
            color: #243b55;
            border-radius: 8px;
            padding: 8px 0;
            margin: 14px 0 0 0;
            font-weight: 600;
        }
    </style>
</head>
<body>
    <header>🎮 Colorful Gaming Hub 🎮</header>
    <nav>
        <button onclick="showGame('ttt')" id="btn-ttt" class="active">Tic Tac Toe</button>
        <button onclick="showGame('snake')" id="btn-snake">Snake</button>
        <button onclick="showGame('memory')" id="btn-memory">Memory</button>
        <button onclick="showGame('rps')" id="btn-rps">Rock Paper Scissors</button>
        <button onclick="showGame('guess')" id="btn-guess">Number Guess</button>
        <button onclick="showGame('wordle')" id="btn-wordle">Wordle</button>
    </nav>
    <main>
        <!-- Tic Tac Toe -->
        <section id="game-ttt">
            <div class="game-title">Tic Tac Toe</div>
            <div class="center">Player <span id="ttt-turn">X</span>'s turn</div>
            <div class="ttt-board" id="ttt-board"></div>
            <div class="msg" id="ttt-msg"></div>
            <div class="center"><button onclick="initTicTacToe()">Restart</button></div>
        </section>
        <!-- Snake -->
        <section id="game-snake" class="hidden">
            <div class="game-title">Snake</div>
            <div class="center">Use Arrow Keys to Play</div>
            <canvas id="snake-canvas" width="320" height="320"></canvas>
            <div class="center">Score: <span id="snake-score">0</span></div>
            <div class="center"><button onclick="initSnake()">Restart</button></div>
        </section>
        <!-- Memory -->
        <section id="game-memory" class="hidden">
            <div class="game-title">Memory</div>
            <div class="memory-board" id="memory-board"></div>
            <div class="msg" id="memory-msg"></div>
            <div class="center"><button onclick="initMemory()">Restart</button></div>
        </section>
        <!-- Rock Paper Scissors -->
        <section id="game-rps" class="hidden">
            <div class="game-title">Rock Paper Scissors</div>
            <div class="rps-btns">
                <button class="rps-btn" onclick="playRPS('rock')">✊</button>
                <button class="rps-btn" onclick="playRPS('paper')">✋</button>
                <button class="rps-btn" onclick="playRPS('scissors')">✌️</button>
            </div>
            <div class="center" id="rps-result"></div>
        </section>
        <!-- Number Guess -->
        <section id="game-guess" class="hidden">
            <div class="game-title">Number Guess (1-100)</div>
            <div class="center">
                <input type="number" id="guess-input" class="number-guess-input" min="1" max="100" />
                <button class="number-guess-btn" onclick="submitGuess()">Guess</button>
            </div>
            <div class="msg" id="guess-msg"></div>
            <div class="center"><button onclick="initGuess()">Restart</button></div>
        </section>
        <!-- Wordle -->
        <section id="game-wordle" class="hidden">
            <div class="game-title">Wordle</div>
            <div class="wordle-board" id="wordle-board"></div>
            <div class="wordle-input-row" id="wordle-input-row"></div>
            <div class="msg" id="wordle-msg"></div>
            <div class="center"><button onclick="initWordle()">Restart</button></div>
        </section>
    </main>
    <script>
        // Navigation
        function showGame(game) {
            ['ttt','snake','memory','rps','guess','wordle'].forEach(g => {
                document.getElementById('game-'+g).classList.add('hidden');
                document.getElementById('btn-'+g).classList.remove('active');
            });
            document.getElementById('game-'+game).classList.remove('hidden');
            document.getElementById('btn-'+game).classList.add('active');
        }
        // --- TIC TAC TOE ---
        let tttBoard, tttTurn, tttOver;
        function initTicTacToe() {
            tttBoard = Array(9).fill('');
            tttTurn = 'X';
            tttOver = false;
            document.getElementById('ttt-turn').textContent = tttTurn;
            document.getElementById('ttt-msg').textContent = '';
            let html = '';
            for (let i=0;i<9;i++) {
                html += `<div class="ttt-cell" onclick="tttMove(${i})" id="ttt-cell-${i}"></div>`;
            }
            document.getElementById('ttt-board').innerHTML = html;
        }
        function tttMove(i) {
            if (tttBoard[i] || tttOver) return;
            tttBoard[i] = tttTurn;
            document.getElementById('ttt-cell-'+i).textContent = tttTurn;
            if (checkTTTWin(tttTurn)) {
                document.getElementById('ttt-msg').textContent = `Player ${tttTurn} wins!`;
                tttOver = true;
            } else if (tttBoard.every(c => c)) {
                document.getElementById('ttt-msg').textContent = 'Draw!';
                tttOver = true;
            } else {
                tttTurn = tttTurn === 'X' ? 'O' : 'X';
                document.getElementById('ttt-turn').textContent = tttTurn;
            }
        }
        function checkTTTWin(p) {
            const wins = [
                [0,1,2],[3,4,5],[6,7,8],
                [0,3,6],[1,4,7],[2,5,8],
                [0,4,8],[2,4,6]
            ];
            return wins.some(w => w.every(i => tttBoard[i]===p));
        }
        // --- SNAKE ---
        let snake, snakeDir, snakeApple, snakeScore, snakeInterval, snakeOver;
        function initSnake() {
            clearInterval(snakeInterval);
            snake = [{x:8, y:8}];
            snakeDir = {x:0, y:-1};
            snakeApple = {x: Math.floor(Math.random()*16), y: Math.floor(Math.random()*16)};
            snakeScore = 0;
            snakeOver = false;
            document.getElementById('snake-score').textContent = snakeScore;
            drawSnake();
            snakeInterval = setInterval(moveSnake, 150);
        }
        function drawSnake() {
            let ctx = document.getElementById('snake-canvas').getContext('2d');
            ctx.clearRect(0,0,320,320);
            ctx.fillStyle = '#6aaa64';
            snake.forEach(seg => ctx.fillRect(seg.x*20+2, seg.y*20+2, 16, 16));
            ctx.fillStyle = '#ffd200';
            ctx.fillRect(snakeApple.x*20+6, snakeApple.y*20+6, 8, 8);
        }
        function moveSnake() {
            if (snakeOver) return;
            let head = {x: snake[0].x+snakeDir.x, y: snake[0].y+snakeDir.y};
            if (head.x<0||head.x>15||head.y<0||head.y>15||snake.some(s=>s.x===head.x&&s.y===head.y)) {
                snakeOver = true;
                clearInterval(snakeInterval);
                alert("Game Over! Score: " + snakeScore);
                return;
            }
            snake.unshift(head);
            if (head.x===snakeApple.x && head.y===snakeApple.y) {
                snakeScore++;
                document.getElementById('snake-score').textContent = snakeScore;
                do {
                    snakeApple = {x: Math.floor(Math.random()*16), y: Math.floor(Math.random()*16)};
                } while (snake.some(s=>s.x===snakeApple.x && s.y===snakeApple.y));
            } else {
                snake.pop();
            }
            drawSnake();
        }
        document.addEventListener('keydown', function(e){
            if (document.getElementById('game-snake').classList.contains('hidden')) return;
            if (e.key==="ArrowUp" && snakeDir.y!==1) snakeDir={x:0,y:-1};
            else if (e.key==="ArrowDown" && snakeDir.y!==-1) snakeDir={x:0,y:1};
            else if (e.key==="ArrowLeft" && snakeDir.x!==1) snakeDir={x:-1,y:0};
            else if (e.key==="ArrowRight" && snakeDir.x!==-1) snakeDir={x:1,y:0};
        });
        // --- MEMORY GAME ---
        const emojis = ['🐶','🐱','🐼','🐸','🦄','🐵','🐙','🦊'];
        let memoryCards, memoryFlipped, memoryMatched, memoryLock;
        function initMemory() {
            memoryCards = shuffle([...emojis,...emojis]);
            memoryFlipped = [];
            memoryMatched = [];
            memoryLock = false;
            let html = '';
            for (let i=0;i<16;i++)
                html += `<div class="memory-card" onclick="flipMemory(${i})" id="memory-card-${i}"></div>`;
            document.getElementById('memory-board').innerHTML = html;
            document.getElementById('memory-msg').textContent = '';
        }
        function flipMemory(i) {
            if (memoryLock || memoryMatched.includes(i) || memoryFlipped.includes(i)) return;
            document.getElementById('memory-card-'+i).textContent = memoryCards[i];
            document.getElementById('memory-card-'+i).classList.add('flipped');
            memoryFlipped.push(i);
            if (memoryFlipped.length===2) {
                memoryLock = true;
                setTimeout(() => {
                    let [a,b]=memoryFlipped;
                    if (memoryCards[a]===memoryCards[b]) {
                        memoryMatched.push(a,b);
                        document.getElementById('memory-card-'+a).classList.add('matched');
                        document.getElementById('memory-card-'+b).classList.add('matched');
                        if (memoryMatched.length===16)
                            document.getElementById('memory-msg').textContent = 'You matched all pairs!';
                    } else {
                        document.getElementById('memory-card-'+a).textContent = '';
                        document.getElementById('memory-card-'+b).textContent = '';
                        document.getElementById('memory-card-'+a).classList.remove('flipped');
                        document.getElementById('memory-card-'+b).classList.remove('flipped');
                    }
                    memoryFlipped = [];
                    memoryLock = false;
                }, 850);
            }
        }
        function shuffle(a) {
            for (let i=a.length-1; i>0; i--) {
                let j=Math.floor(Math.random()*(i+1));
                [a[i],a[j]]=[a[j],a[i]];
            }
            return a;
        }
        // --- ROCK PAPER SCISSORS ---
        function playRPS(user) {
            const ai = ['rock','paper','scissors'][Math.floor(Math.random()*3)];
            let result;
            if (user===ai) result = "It's a tie!";
            else if ((user==="rock"&&ai==="scissors")||(user==="paper"&&ai==="rock")||(user==="scissors"&&ai==="paper"))
                result = "You win!";
            else result = "You lose!";
            document.getElementById('rps-result').innerHTML = `You: <b>${iconRPS(user)}</b><br>AI: <b>${iconRPS(ai)}</b><br>${result}`;
        }
        function iconRPS(x) {
            return x==="rock"?"✊":x==="paper"?"✋":"✌️";
        }
        // --- NUMBER GUESS ---
        let guessNumber, guessTries;
        function initGuess() {
            guessNumber = Math.floor(Math.random()*100)+1;
            guessTries = 0;
            document.getElementById('guess-input').value = '';
            document.getElementById('guess-msg').textContent = '';
        }
        function submitGuess() {
            let val = parseInt(document.getElementById('guess-input').value);
            if (isNaN(val) || val<1 || val>100) {
                document.getElementById('guess-msg').textContent = "Enter a number 1-100";
                return;
            }
            guessTries++;
            if (val === guessNumber) {
                document.getElementById('guess-msg').textContent = `🎉 Correct! You took ${guessTries} tries.`;
            } else if (val < guessNumber) {
                document.getElementById('guess-msg').textContent = "Try higher!";
            } else {
                document.getElementById('guess-msg').textContent = "Try lower!";
            }
        }
        // --- WORDLE ---
        const wordleWords = [
            "apple", "crazy", "brave", "eagle", "grape", "light", "night", "spice", "train", "charm",
            "plane", "proud", "smile", "tiger", "trend", "flame", "prize", "sound", "sweet", "shark"
        ];
        let wordleAnswer, wordleGuesses, wordleCurrent, wordleOver;
        function initWordle() {
            wordleAnswer = wordleWords[Math.floor(Math.random()*wordleWords.length)];
            wordleGuesses = [];
            wordleCurrent = "";
            wordleOver = false;
            document.getElementById('wordle-msg').textContent = '';
            drawWordleBoard();
            drawWordleInput();
        }
        function drawWordleBoard() {
            let html = '';
            for (let r=0; r<6; r++) {
                html += `<div class="wordle-row">`;
                let guess = wordleGuesses[r] || "";
                let colors = wordleGuesses[r] ? wordleColors(wordleGuesses[r]) : [];
                for (let c=0; c<5; c++) {
                    let letter = guess[c]||'';
                    let cls = colors[c]||'';
                    html += `<div class="wordle-cell${cls?' '+cls:''}">${letter}</div>`;
                }
                html += `</div>`;
            }
            document.getElementById('wordle-board').innerHTML = html;
        }
        function drawWordleInput() {
            let html = '';
            if (!wordleOver && wordleGuesses.length<6) {
                for (let i=0;i<5;i++)
                    html += `<input maxlength="1" class="wordle-input" id="wordle-inp-${i}" oninput="autoWordleInput(${i})" />`;
                html += `<button class="wordle-submit-btn" onclick="submitWordle()">Submit</button>`;
            }
            document.getElementById('wordle-input-row').innerHTML = html;
            if (!wordleOver && wordleGuesses.length<6)
                document.getElementById('wordle-inp-0').focus();
        }
        function autoWordleInput(i) {
            let val = document.getElementById('wordle-inp-'+i).value;
            if (val.length===1 && i<4) document.getElementById('wordle-inp-'+(i+1)).focus();
        }
        function submitWordle() {
            let guess = '';
            for (let i=0;i<5;i++) guess += (document.getElementById('wordle-inp-'+i).value||'').toLowerCase();
            if (guess.length!==5 || !/^[a-z]{5}$/.test(guess)) {
                document.getElementById('wordle-msg').textContent = "Enter a 5-letter word";
                return;
            }
            wordleGuesses.push(guess);
            drawWordleBoard();
            if (guess === wordleAnswer) {
                document.getElementById('wordle-msg').textContent = "🎉 You guessed right!";
                wordleOver = true;
                drawWordleInput();
            } else if (wordleGuesses.length===6) {
                document.getElementById('wordle-msg').textContent = `The word was: ${wordleAnswer.toUpperCase()}`;
                wordleOver = true;
                drawWordleInput();
            } else {
                document.getElementById('wordle-msg').textContent = '';
                drawWordleInput();
            }
        }
        function wordleColors(guess) {
            let answer = wordleAnswer.split('');
            let colors = Array(5).fill('absent');
            let used = Array(5).fill(false);
            // Green
            for (let i=0;i<5;i++)
                if (guess[i]===answer[i]) { colors[i]='correct'; used[i]=true; }
            // Yellow
            for (let i=0;i<5;i++) {
                if (colors[i]==='correct') continue;
                for (let j=0;j<5;j++) {
                    if (!used[j] && guess[i]===answer[j]) {
                        colors[i]='present'; used[j]=true;
                        break;
                    }
                }
            }
            return colors;
        }
        // --- INIT ---
        initTicTacToe();
        initSnake();
        initMemory();
        initGuess();
        initWordle();
        showGame('ttt');
    </script>
</body>
</html>
