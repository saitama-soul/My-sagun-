# My-sagun-

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>For Sagun 💕</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,600;0,700;1,600&family=Lora:ital,wght@0,400;0,500;1,400&display=swap" rel="stylesheet">
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; user-select: none; }
        body { font-family: 'Lora', serif; overflow: hidden; height: 100vh; display: flex; align-items: center; justify-content: center; background: #fce4ec; }
        
        /* Backgrounds */
        #bg { position: fixed; inset: 0; background: linear-gradient(135deg, #fce4ec, #f3e5f5, #e3f2fd, #fce4ec); background-size: 400% 400%; animation: grad 15s ease infinite; transition: opacity 1s; z-index: 0; }
        #bg-sad { position: fixed; inset: 0; background: linear-gradient(135deg, #161625, #22223b, #161625); opacity: 0; transition: opacity 1s; z-index: 1; }
        @keyframes grad { 0% {background-position: 0% 50%} 50% {background-position: 100% 50%} 100% {background-position: 0% 50%} }

        /* Particles */
        canvas, #hearts-container { position: fixed; inset: 0; pointer-events: none; z-index: 2; }
        .fheart { position: absolute; bottom: -50px; opacity: 0; animation: floatUp linear forwards; }
        @keyframes floatUp { 0% { transform: translateY(0) scale(0.8); opacity: 0; } 10% { opacity: 0.8; } 100% { transform: translateY(-110vh) scale(1.2); opacity: 0; } }

        /* Card Setup */
        #stage { position: relative; z-index: 10; padding: 1.5rem; width: 100%; max-width: 550px; perspective: 1000px; }
        .glass-card { background: rgba(255, 255, 255, 0.45); backdrop-filter: blur(20px); border: 1px solid rgba(255, 255, 255, 0.6); border-radius: 24px; padding: 3rem 2rem; text-align: center; box-shadow: 0 15px 35px rgba(244, 114, 182, 0.2); transition: all 0.5s; position: relative; min-height: 300px; display: flex; flex-direction: column; justify-content: center; }
        .glass-card.sad-mode { background: rgba(30, 30, 45, 0.7); border-color: rgba(100, 100, 140, 0.3); box-shadow: 0 15px 35px rgba(0,0,0,0.5); color: #cbd5e1; }
        
        /* Scenes */
        .scene { display: none; opacity: 0; transition: opacity 0.5s; }
        .scene.active { display: block; opacity: 1; }

        /* Typography */
        h1, h2 { font-family: 'Playfair Display', serif; line-height: 1.3; color: #7c3f6b; margin-bottom: 1rem; }
        .glass-card.sad-mode h2 { color: #cbd5e1; }
        p { color: #9d6080; font-size: 1.1rem; margin-bottom: 2rem; }
        .glass-card.sad-mode p { color: #94a3b8; }
        .emoji-large { font-size: 4rem; display: block; margin-bottom: 1rem; animation: float 3s ease-in-out infinite; }
        @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }

        .redirect-note { font-size: 0.9rem !important; font-style: italic; color: #64748b !important; margin-top: 1rem; }
        .expanded-msg { font-size: 1.15rem; line-height: 1.7; color: #7c3f6b; margin-bottom: 1.5rem; font-style: italic; padding: 0 1rem; }

        /* Buttons */
        .btn-wrap { position: relative; display: flex; justify-content: center; gap: 1rem; align-items: center; min-height: 60px; }
        .btn { padding: 0.8rem 1.8rem; border-radius: 50px; font-family: inherit; font-size: 1rem; font-weight: bold; cursor: pointer; border: none; transition: all 0.3s cubic-bezier(0.25, 1, 0.5, 1); }
        .btn-yes { background: linear-gradient(135deg, #fb7185, #f472b6); color: white; box-shadow: 0 5px 15px rgba(251, 113, 133, 0.4); z-index: 5; }
        .btn-no { background: rgba(255,255,255,0.7); color: #9d6080; border: 1px solid #f472b6; position: relative; z-index: 4; }
        
        /* Button States */
        .btn-yes.bigger { transform: scale(1.3); box-shadow: 0 10px 25px rgba(251, 113, 133, 0.6); }
        .btn-no.tiny { transform: scale(0.6); opacity: 0.8; }
        .btn-yes.massive { transform: scale(1.6); width: 100%; padding: 1.2rem; animation: pulse 1.5s infinite; }
        @keyframes pulse { 0%, 100% { transform: scale(1.6); } 50% { transform: scale(1.65); box-shadow: 0 15px 40px rgba(251, 113, 133, 0.8); } }

        /* Timer */
        #timer { font-size: 4rem; font-family: 'Playfair Display', serif; color: #fb7185; font-weight: bold; }
        
        /* Typing */
        #typing-text { font-size: 1.2rem; line-height: 1.6; color: #7c3f6b; display: inline; }
        .cursor { display: inline-block; width: 2px; height: 1.2em; background: #fb7185; animation: blink 0.7s infinite; vertical-align: middle; }
        @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }

        /* Finale */
        .big-heart { font-size: 5rem; animation: beat 1s infinite; margin-bottom: 1rem; display: block; filter: drop-shadow(0 0 15px rgba(251,113,133,0.5)); }
        @keyframes beat { 0%, 100% { transform: scale(1); } 15% { transform: scale(1.2); } 30% { transform: scale(1); } 45% { transform: scale(1.15); } }
        
    </style>
</head>
<body>

    <div id="bg"></div>
    <div id="bg-sad"></div>
    <div id="hearts-container"></div>
    <canvas id="canvas"></canvas>

    <div id="stage">
        <div class="glass-card" id="card">
            
            <!-- SCENE 1, 4, 6: Main Question -->
            <div id="scene-question" class="scene active">
                <h1>I have a question<br>for you, <span style="color:#fb7185; font-style:italic;">Sagun</span>...</h1>
                <p id="question-sub">Think carefully before you answer 🌸</p>
                <div class="btn-wrap">
                    <button id="btn-yes" class="btn btn-yes">Yes, I love you!</button>
                    <button id="btn-no" class="btn btn-no">No, I don't.</button>
                </div>
            </div>

            <!-- SCENE 2 & 5: Sad Screens -->
            <div id="scene-sad" class="scene">
                <span class="emoji-large">😢</span>
                <h2 id="sad-text">Oh no... my heart is<br>shattered, Sagun. 💔</h2>
                <p id="sad-redirect" class="redirect-note">ok ok... taking you back in 3 seconds 🥰</p>
            </div>

            <!-- SCENE 3: Timer -->
            <div id="scene-timer" class="scene">
                <h2>Sorry to annoy you too much, but I'm not giving up...</h2>
                <div id="timer">6</div>
            </div>

            <!-- SCENE 7: Yes Eruption -->
            <div id="scene-yes" class="scene">
                <span class="emoji-large">🎉</span>
                <h2>Yay! This makes me so<br>incredibly happy, Sagun!</h2>
                <button id="btn-secret" class="btn btn-yes" style="margin-top: 1rem;">Click for a secret...</button>
            </div>

            <!-- SCENE 8: Appreciation -->
            <div id="scene-appreciation" class="scene">
                <div style="min-height: 120px; text-align: left; margin-bottom: 1.5rem;">
                    <span id="typing-text"></span><span class="cursor"></span>
                </div>
                <button id="btn-more" class="btn btn-yes" style="display: none; width: 100%;">One more thing...</button>
            </div>

            <!-- SCENE 8.5: The Apology -->
            <div id="scene-apology" class="scene">
                <h2>I'm sorry! 🥺</h2>
                <p>First of all, I'm sorry for annoying you so much with all those useless things I love you my sweetheart and thanks for understanding me... you know I just love you!</p>
                <button id="btn-real-msg" class="btn btn-yes" style="width: 100%;">Show me the real message 💕</button>
            </div>

            <!-- SCENE 9: Finale (Expanded) -->
            <div id="scene-finale" class="scene">
                <span class="big-heart">❤️</span>
                <p class="expanded-msg">You are my best friend, my safe place, and the most beautiful part of my life. Every single day with you is a gift, and I can't wait to spend the rest of my life making you smile.</p>
                <h2>One day, I'm gonna marry you, Sagun. 💍</h2>
            </div>

        </div>
    </div>

    <script>
        // --- Elements ---
        const card = document.getElementById('card');
        const bgSad = document.getElementById('bg-sad');
        const sQuestion = document.getElementById('scene-question');
        const sSad = document.getElementById('scene-sad');
        const sTimer = document.getElementById('scene-timer');
        const sYes = document.getElementById('scene-yes');
        const sApprec = document.getElementById('scene-appreciation');
        const sApology = document.getElementById('scene-apology');
        const sFinale = document.getElementById('scene-finale');
        
        const btnYes = document.getElementById('btn-yes');
        const btnNo = document.getElementById('btn-no');
        const subtitle = document.getElementById('question-sub');
        const sadText = document.getElementById('sad-text');
        const sadRedirect = document.getElementById('sad-redirect');
        const timerEl = document.getElementById('timer');
        
        let attempt = 1;

        // --- Helper: Switch Scenes ---
        function showScene(sceneToShow) {
            document.querySelectorAll('.scene').forEach(s => {
                s.style.opacity = '0';
                setTimeout(() => { s.classList.remove('active'); s.style.display = 'none'; }, 500);
            });
            setTimeout(() => {
                sceneToShow.style.display = 'block';
                setTimeout(() => { sceneToShow.classList.add('active'); sceneToShow.style.opacity = '1'; }, 50);
            }, 500);
        }

        function toggleSadTheme(isSad) {
            bgSad.style.opacity = isSad ? '1' : '0';
            isSad ? card.classList.add('sad-mode') : card.classList.remove('sad-mode');
        }

        // --- Runaway NO Button ---
        function runaway() {
            if(attempt >= 3) return;
            btnNo.style.position = 'fixed';
            const x = Math.random() * (window.innerWidth - btnNo.offsetWidth - 20) + 10;
            const y = Math.random() * (window.innerHeight - btnNo.offsetHeight - 20) + 10;
            btnNo.style.left = `${x}px`;
            btnNo.style.top = `${y}px`;
        }
        btnNo.addEventListener('mouseover', runaway);
        btnNo.addEventListener('touchstart', (e) => { e.preventDefault(); runaway(); });

        // --- Clicking NO ---
        btnNo.addEventListener('click', () => {
            if (attempt === 1) {
                // Scene 2: First Rejection
                sadText.innerHTML = "Oh no... my heart is<br>shattered, Sagun. 💔";
                sadRedirect.style.display = 'block'; // Show the "taking you back" text
                toggleSadTheme(true);
                showScene(sSad);
                
                setTimeout(() => {
                    // Scene 3: Timer
                    toggleSadTheme(false);
                    showScene(sTimer);
                    let left = 6;
                    timerEl.innerText = left;
                    const int = setInterval(() => {
                        left--;
                        timerEl.innerText = left;
                        if(left <= 0) {
                            clearInterval(int);
                            // Setup Scene 4 (Attempt 2)
                            attempt = 2;
                            btnYes.classList.add('bigger');
                            btnNo.classList.add('tiny');
                            btnNo.style.position = 'relative'; btnNo.style.left = 'auto'; btnNo.style.top = 'auto';
                            showScene(sQuestion);
                        }
                    }, 1000);
                }, 3000);
            } 
            else if (attempt === 2) {
                // Scene 5: Second Rejection
                sadText.innerHTML = "Still no?! You are<br>breaking my heart! 😭";
                sadRedirect.style.display = 'none'; // Hide redirect text this time
                toggleSadTheme(true);
                showScene(sSad);

                setTimeout(() => {
                    // Scene 6: Ultimatum (No button disappears, Yes takes over)
                    toggleSadTheme(false);
                    attempt = 3;
                    btnNo.style.display = 'none';
                    btnYes.classList.remove('bigger');
                    btnYes.classList.add('massive');
                    subtitle.innerHTML = "<strong style='font-size:1.3rem; color:#fb7185;'>You don't have any other choices! 🥺</strong>";
                    showScene(sQuestion);
                }, 3000);
            }
        });

        // --- Clicking YES ---
        btnYes.addEventListener('click', () => {
            // Scene 7: Yes Eruption
            btnNo.style.display = 'none';
            showScene(sYes);
            startParticles('confetti');
        });

        // --- Clicking Secret ---
        document.getElementById('btn-secret').addEventListener('click', () => {
            // Scene 8: Appreciation
            showScene(sApprec);
            startParticles('sparkles');
            
            setTimeout(() => {
                const text = "Thank you for always understanding me. Thank you for loving me through it all, and for caring for me so deeply.";
                const el = document.getElementById('typing-text');
                let i = 0;
                function type() {
                    if (i < text.length) {
                        el.innerHTML += text.charAt(i);
                        i++;
                        setTimeout(type, 60);
                    } else {
                        document.querySelector('.cursor').style.display = 'none';
                        const btnMore = document.getElementById('btn-more');
                        btnMore.style.display = 'block';
                        setTimeout(() => btnMore.style.opacity = '1', 50);
                    }
                }
                type();
            }, 800);
        });

        // --- Clicking "One more thing" ---
        document.getElementById('btn-more').addEventListener('click', () => {
            // Scene 8.5: The Apology
            showScene(sApology);
        });

        // --- Clicking "Show me the real message" ---
        document.getElementById('btn-real-msg').addEventListener('click', () => {
            // Scene 9: Finale
            showScene(sFinale);
            spawnHearts(150); // Endless floating hearts
        });


        // --- Particle Engine ---
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');
        let pArray = [];
        let mode = 'none'; // 'confetti' or 'sparkles'
        
        function resize() { canvas.width = window.innerWidth; canvas.height = window.innerHeight; }
        window.addEventListener('resize', resize); resize();

        function startParticles(newMode) {
            mode = newMode;
            pArray = [];
            for(let i=0; i<150; i++) {
                pArray.push({
                    x: canvas.width/2, y: canvas.height/2 + 50,
                    r: Math.random() * 6 + 2,
                    dx: Math.random() * 15 - 7.5,
                    dy: Math.random() * -15 - 5,
                    color: ['#fb7185', '#f472b6', '#c084fc', '#fcd34d', '#fff'][Math.floor(Math.random()*5)],
                    alpha: 1
                });
            }
            requestAnimationFrame(drawParticles);
        }

        function drawParticles() {
            if(mode === 'none') return;
            ctx.clearRect(0,0,canvas.width,canvas.height);
            pArray.forEach((p, i) => {
                if(mode === 'confetti') {
                    p.dy += 0.2; // Gravity
                    p.x += p.dx; p.y += p.dy;
                    ctx.fillStyle = p.color;
                    ctx.fillRect(p.x, p.y, p.r*2, p.r);
                } else if(mode === 'sparkles') {
                    p.alpha -= 0.005;
                    p.x += p.dx*0.2; p.y += p.dy*0.2;
                    ctx.globalAlpha = Math.max(0, p.alpha);
                    ctx.beginPath(); ctx.arc(p.x, p.y, p.r, 0, Math.PI*2);
                    ctx.fillStyle = '#fb7185'; ctx.fill();
                    ctx.globalAlpha = 1;
                }
                // Recycle
                if(p.y > canvas.height || p.alpha <= 0) {
                    pArray[i] = { x: Math.random()*canvas.width, y: -20, r: p.r, dx: Math.random()*4-2, dy: Math.random()*5+2, color: p.color, alpha: 1 };
                }
            });
            requestAnimationFrame(drawParticles);
        }

        // Floating Hearts
        const hContainer = document.getElementById('hearts-container');
        function spawnHearts(intervalMs) {
            const symbols = ['💕', '🌸', '✨', '💗', '💍'];
            setInterval(() => {
                const h = document.createElement('div');
                h.className = 'fheart';
                h.innerText = symbols[Math.floor(Math.random()*symbols.length)];
                h.style.left = Math.random() * 100 + 'vw';
                h.style.animationDuration = (Math.random() * 5 + 4) + 's';
                h.style.fontSize = (Math.random() * 1.5 + 1) + 'rem';
                hContainer.appendChild(h);
                setTimeout(() => h.remove(), 9000);
            }, intervalMs);
        }
        spawnHearts(1200); // Standard background hearts

    </script>
</body>
</html>
