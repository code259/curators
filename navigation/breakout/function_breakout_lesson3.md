---
layout: post
title: Functional Breakout - Lesson 3: Power-ups & Polish
author: Nikhil, Rohan, Pranav, Aditya, Shriya, Samhita
permalink: /function_breakout_lesson3
---

<style>
.lesson-container {
    max-width: 900px;
    margin: 0 auto;
    padding: 20px;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.lesson-header {
    text-align: center;
    margin-bottom: 40px;
    padding: 30px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    border-radius: 15px;
    color: white;
}

.lesson-title {
    font-size: 2.2em;
    margin-bottom: 10px;
}

.lesson-subtitle {
    font-size: 1.1em;
    opacity: 0.9;
}

.navigation-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 30px;
    padding: 15px;
    background: #f8f9fa;
    border-radius: 10px;
}

.nav-link {
    padding: 10px 20px;
    background: #667eea;
    color: white;
    text-decoration: none;
    border-radius: 20px;
    font-weight: 600;
    transition: all 0.3s ease;
}

.nav-link:hover {
    background: #5a67d8;
    transform: translateY(-2px);
    color: white;
}

.lesson-goals {
    background: #e8f5e8;
    padding: 25px;
    border-radius: 12px;
    margin: 30px 0;
    border-left: 5px solid #4caf50;
}

.goals-title {
    color: #2e7d32;
    font-size: 1.3em;
    margin-bottom: 15px;
    font-weight: 600;
}

.section-title {
    color: #2c3e50;
    font-size: 1.4em;
    margin-bottom: 20px;
    border-bottom: 2px solid #e0e6ed;
    padding-bottom: 10px;
}

.step-title {
    color: #667eea;
    font-size: 1.2em;
    margin: 25px 0 15px 0;
    font-weight: 600;
}

.demo-container {
    margin: 30px 0;
    padding: 25px;
    background: white;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    border: 1px solid #e0e6ed;
}

.demo-title {
    color: #2c3e50;
    font-size: 1.3em;
    margin-bottom: 20px;
    text-align: center;
}

.toggle-label {
    display: block;
    text-align: center;
    margin: 6px 0;
    color: #667eea;
    cursor: pointer;
    font-weight: 600;
}

.powerup-explanation {
    background: #fff8e1;
    padding: 20px;
    border-radius: 10px;
    margin: 20px 0;
    border-left: 4px solid #ffc107;
}

.powerup-title {
    color: #f57c00;
    font-weight: 600;
    margin-bottom: 10px;
}

.explore-section {
    background: #fff3cd;
    padding: 20px;
    border-radius: 10px;
    margin: 25px 0;
    border-left: 4px solid #ffc107;
}

.explore-title {
    color: #856404;
    font-weight: 600;
    margin-bottom: 10px;
}

.feature-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    margin: 30px 0;
}

.feature-card {
    background: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    border-top: 4px solid #ffc107;
}

.feature-title {
    color: #2c3e50;
    font-size: 1.1em;
    margin-bottom: 10px;
    font-weight: 600;
}

pre {
    background: #1e1e1e;
    color: #d4d4d4;
    padding: 20px;
    border-radius: 8px;
    overflow-x: auto;
    margin: 15px 0;
}

.quiz-section, .whiteboard-section {
    margin: 40px 0;
    padding: 30px;
    border-radius: 15px;
    color: white;
    text-align: center;
}

.quiz-section {
    background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
}

.whiteboard-section {
    background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
}

.action-button {
    display: inline-block;
    padding: 12px 25px;
    background: white;
    color: #667eea;
    text-decoration: none;
    border-radius: 25px;
    font-weight: 600;
    margin: 10px;
    transition: all 0.3s ease;
}

.action-button:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

@media (max-width: 768px) {
    .navigation-bar {
        flex-direction: column;
        gap: 10px;
    }
    
    .lesson-title {
        font-size: 1.8em;
    }
}
</style>

<div class="lesson-container">
    <div class="lesson-header">
        <h1 class="lesson-title">✨ Lesson 3: Power-ups & Polish</h1>
        <p class="lesson-subtitle">Add exciting power-ups, timers, and complete your breakout game</p>
    </div>

    <div class="navigation-bar">
        <a href="/function_breakout_lesson2" class="nav-link">← Lesson 2: Ball Physics</a>
        <div style="color: #666; font-weight: 600;">Lesson 3 of 3</div>
        <a href="/function_breakout" class="nav-link">Back to Hub</a>
    </div>

    <div class="lesson-goals">
        <h2 class="goals-title">🎯 Learning Goals</h2>
        <p>In this final lesson, you'll learn how to:</p>
        <ul>
            <li>Create special bricks that drop power-ups</li>
            <li>Implement falling power-up mechanics</li>
            <li>Add visual timers and UI elements</li>
            <li>Build a complete mini breakout game</li>
        </ul>
    </div>

    <div class="feature-grid">
        <div class="feature-card">
            <h3 class="feature-title">🎁 Power-up Drops</h3>
            <p>Special bricks randomly contain power-ups that fall when broken.</p>
        </div>
        <div class="feature-card">
            <h3 class="feature-title">⏱️ Timer System</h3>
            <p>Visual countdown shows how long power-ups remain active.</p>
        </div>
        <div class="feature-card">
            <h3 class="feature-title">🎮 Complete Game</h3>
            <p>Combine all elements into a fully playable breakout experience.</p>
        </div>
    </div>

    <h2 class="section-title">🎁 Step 1: Add Special Bricks</h2>
    <p>First, let's create bricks that have a chance to contain power-ups when broken.</p>

    <pre><code>let bricks = [];
const powerUpChance = 0.3; // 30% chance

for (let c = 0; c < brickColumnCount; c++) {
  bricks[c] = [];
  for (let r = 0; r < brickRowCount; r++) {
    const hasPowerUp = Math.random() < powerUpChance;
    bricks[c][r] = { 
      x: 0, 
      y: 0, 
      status: 1, 
      powerUp: hasPowerUp 
    };
  }
}</code></pre>

    <div class="powerup-explanation">
        <div class="powerup-title">💡 Power-up Logic</div>
        <p>When a brick with <code>powerUp: true</code> is hit, we spawn a falling power-up at that location:</p>
        <pre><code>if (b.powerUp) {
  powerUps.push({ 
    x: b.x + brickWidth/2, 
    y: b.y, 
    active: true 
  });
}</code></pre>
    </div>

    <h2 class="section-title">⚡ Step 2: Draw and Drop Power-ups</h2>
    <p>Create visually appealing power-ups that fall down and can be caught by the paddle.</p>

    <pre><code>let powerUps = [];
let activePowerUp = null;
let powerUpTimer = 0;
const powerUpDuration = 5000; // 5 seconds

function drawPowerUps() {
  for (let p of powerUps) {
    if (p.active) {
      // Draw glowing power-up
      ctx.beginPath();
      ctx.arc(p.x, p.y, 10, 0, Math.PI * 2);
      ctx.fillStyle = "gold";
      ctx.fill();
      ctx.closePath();

      // Add "P" text
      ctx.fillStyle = "black";
      ctx.font = "bold 14px Arial";
      ctx.textAlign = "center";
      ctx.fillText("P", p.x, p.y + 4);

      // Make it fall
      p.y += 1.5;

      // Check paddle collision
      if (p.y >= canvas.height - paddleHeight &&
          p.x > paddleX && p.x < paddleX + paddleWidth) {
        p.active = false;
        paddleWidth = basePaddleWidth + 40; // Widen paddle
        activePowerUp = "Wide Paddle";
        powerUpTimer = Date.now();
      }
    }
  }
}</code></pre>

    <h2 class="section-title">⏱️ Step 3: Show Timer</h2>
    <p>Add a visual timer to show how long the power-up effect lasts.</p>

    <pre><code>function drawPowerUpTimer() {
  if (activePowerUp) {
    let elapsed = Date.now() - powerUpTimer;
    let remaining = Math.max(0, powerUpDuration - elapsed);

    // Draw timer background
    ctx.fillStyle = "gray";
    ctx.fillRect(canvas.width - 20, 20, 10, 100);

    // Draw timer fill
    ctx.fillStyle = "lime";
    let fillHeight = (remaining / powerUpDuration) * 100;
    ctx.fillRect(canvas.width - 20, 120 - fillHeight, 10, fillHeight);

    // Reset when timer expires
    if (remaining <= 0) {
      activePowerUp = null;
      paddleWidth = basePaddleWidth;
    }
  }
}</code></pre>

    <div class="explore-section">
        <div class="explore-title">🔍 Explore & Experiment:</div>
        <ul>
            <li>Change the timer duration from 5 to 10 seconds</li>
            <li>Try different power-up effects (double speed, bigger ball)</li>
            <li>Add different colored power-ups for different effects</li>
            <li>Create power-ups that make the paddle smaller instead</li>
        </ul>
    </div>

    <div class="demo-container">
        <h3 class="demo-title">🎮 Demo: Complete Mini Breakout</h3>
        <p style="text-align: center; color: #666; margin-bottom: 20px;">
            <strong>Arrow keys</strong> to move, break bricks and catch power-ups!
        </p>

        <label class="toggle-label">
            <input type="checkbox" id="toggle-breakout"> Show Code
        </label>

        <div id="wrap-breakout">
            <canvas id="breakoutDemo" width="400" height="300" style="background:white; border:2px solid #333; display:block; margin:0 auto; border-radius: 8px;"></canvas>
        </div>

        <pre id="code-breakout" style="display:none;"><code>// Complete mini breakout with bricks and power-ups
const brCanvas = document.getElementById("breakoutDemo");
const brCtx = brCanvas.getContext("2d");

// Game variables
let brX = brCanvas.width/2, brY = brCanvas.height-30;
let brVX = 2, brVY = -2, brR = 8;
let brPX = (brCanvas.width-75)/2, brPW = 75, brPH = 10;
let brRight = false, brLeft = false;

// Bricks
let brBricks = [];
for(let c = 0; c < 5; c++) {
  brBricks[c] = [];
  for(let r = 0; r < 3; r++) {
    brBricks[c][r] = {status: 1};
  }
}

// Input handling
document.addEventListener("keydown", e => {
  if(e.key === "ArrowRight") brRight = true;
  if(e.key === "ArrowLeft") brLeft = true;
});
document.addEventListener("keyup", e => {
  if(e.key === "ArrowRight") brRight = false;
  if(e.key === "ArrowLeft") brLeft = false;
});

function drawBreakout() {
  brCtx.clearRect(0,0,brCanvas.width,brCanvas.height);
  
  // Draw ball
  brCtx.beginPath();
  brCtx.arc(brX, brY, brR, 0, Math.PI*2);
  brCtx.fillStyle = "#DD0000";
  brCtx.fill();
  brCtx.closePath();
  
  // Draw paddle
  brCtx.fillStyle = "#0095DD";
  brCtx.fillRect(brPX, brCanvas.height-brPH, brPW, brPH);
  
  // Draw bricks
  for(let c = 0; c < 5; c++) {
    for(let r = 0; r < 3; r++) {
      if(brBricks[c][r].status === 1) {
        let brickX = c * 75 + 10;
        let brickY = r * 20 + 30;
        brCtx.fillStyle = "#0095DD";
        brCtx.fillRect(brickX, brickY, 65, 15);
      }
    }
  }
  
  // Ball physics
  brX += brVX; brY += brVY;
  if(brX+brR > brCanvas.width || brX-brR < 0) brVX = -brVX;
  if(brY-brR < 0) brVY = -brVY;
  else if(brY+brR > brCanvas.height-brPH && brX > brPX && brX < brPX+brPW) brVY = -brVY;
  else if(brY+brR > brCanvas.height) { 
    brX = brCanvas.width/2; brY = brCanvas.height-30; brVY = -2; 
  }
  
  // Paddle movement
  if(brRight && brPX < brCanvas.width-brPW) brPX += 5;
  if(brLeft && brPX > 0) brPX -= 5;
  
  requestAnimationFrame(drawBreakout);
}
drawBreakout();</code></pre>

        <script>
        const brCanvas = document.getElementById("breakoutDemo");
        const brCtx = brCanvas.getContext("2d");
        let brX = brCanvas.width/2, brY = brCanvas.height-30, brVX = 2, brVY = -2, brR = 8;
        let brPX = (brCanvas.width-75)/2, brPW = 75, brPH = 10;
        let brRight = false, brLeft = false;

        let brBricks = [];
        for(let c = 0; c < 5; c++) {
            brBricks[c] = [];
            for(let r = 0; r < 3; r++) {
                brBricks[c][r] = {status: 1};
            }
        }

        document.addEventListener("keydown", e => {
            if(e.key === "ArrowRight") brRight = true;
            if(e.key === "ArrowLeft") brLeft = true;
        });
        document.addEventListener("keyup", e => {
            if(e.key === "ArrowRight") brRight = false;
            if(e.key === "ArrowLeft") brLeft = false;
        });

        function drawBreakout() {
            brCtx.clearRect(0,0,brCanvas.width,brCanvas.height);
            
            brCtx.beginPath();
            brCtx.arc(brX, brY, brR, 0, Math.PI*2);
            brCtx.fillStyle = "#DD0000";
            brCtx.fill();
            brCtx.closePath();
            
            brCtx.fillStyle = "#0095DD";
            brCtx.fillRect(brPX, brCanvas.height-brPH, brPW, brPH);
            
            for(let c = 0; c < 5; c++) {
                for(let r = 0; r < 3; r++) {
                    if(brBricks[c][r].status === 1) {
                        let brickX = c * 75 + 10;
                        let brickY = r * 20 + 30;
                        brCtx.fillStyle = "#0095DD";
                        brCtx.fillRect(brickX, brickY, 65, 15);
                        
                        // Collision detection
                        if(brX > brickX && brX < brickX+65 && brY > brickY && brY < brickY+15) {
                            brVY = -brVY;
                            brBricks[c][r].status = 0;
                        }
                    }
                }
            }
            
            brX += brVX; brY += brVY;
            if(brX+brR > brCanvas.width || brX-brR < 0) brVX = -brVX;
            if(brY-brR < 0) brVY = -brVY;
            else if(brY+brR > brCanvas.height-brPH && brX > brPX && brX < brPX+brPW) brVY = -brVY;
            else if(brY+brR > brCanvas.height) { brX = brCanvas.width/2; brY = brCanvas.height-30; brVY = -2; }
            
            if(brRight && brPX < brCanvas.width-brPW) brPX += 5;
            if(brLeft && brPX > 0) brPX -= 5;
            
            requestAnimationFrame(drawBreakout);
        }
        drawBreakout();

        (function(){
            const toggle = document.getElementById("toggle-breakout");
            const wrap = document.getElementById("wrap-breakout");
            const code = document.getElementById("code-breakout");
            toggle.checked = false;
            toggle.addEventListener("change", () => {
                if (toggle.checked) { wrap.style.display = "none"; code.style.display = "block"; }
                else { code.style.display = "none"; wrap.style.display = "block"; }
            });
        })();
        </script>
    </div>

    <div class="quiz-section">
        <h3 style="margin-bottom: 15px;">📝 Final Challenge</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Test your complete understanding of functional breakout game development!</p>
        <a href="#quiz" class="action-button" onclick="showQuiz3()">Take Final Quiz</a>
    </div>

    <div class="whiteboard-section">
        <h3 style="margin-bottom: 15px;">🎨 Design Your Game</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Sketch your own breakout game variations and power-up ideas!</p>
        <a href="#whiteboard" class="action-button" onclick="showWhiteboard3()">Open Whiteboard</a>
    </div>

    <div style="text-align: center; margin-top: 40px; padding: 25px; background: linear-gradient(135deg, #fd79a8 0%, #fdcb6e 100%); border-radius: 12px; color: white;">
        <h3 style="margin-bottom: 15px;">🎉 Congratulations!</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">You've completed the functional breakout track! Ready to explore object-oriented programming?</p>
        <div style="display: flex; gap: 15px; justify-content: center; flex-wrap: wrap;">
            <a href="/function_breakout" style="display: inline-block; padding: 12px 25px; background: white; color: #fd79a8; border-radius: 25px; text-decoration: none; font-weight: 600;">
                ← Back to Functional Hub
            </a>
            <a href="/oop_breakout_lesson1" style="display: inline-block; padding: 12px 25px; background: white; color: #fd79a8; border-radius: 25px; text-decoration: none; font-weight: 600;">
                Try OOP Track →
            </a>
        </div>
    </div>
</div>

<script>
function showQuiz3() {
    alert("Quiz functionality coming soon! Try creating your own power-up variations in the demo above.");
}

function showWhiteboard3() {
    alert("Whiteboard functionality coming soon! For now, try sketching your own game ideas on paper.");
}
</script>