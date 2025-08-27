---
layout: post
title: Functional Breakout - Lesson 2: Ball Physics & Collision
author: Nikhil, Rohan, Pranav, Aditya, Shriya, Samhita
permalink: /function_breakout_lesson2
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

.physics-explanation {
    background: #f0f8ff;
    padding: 20px;
    border-radius: 10px;
    margin: 20px 0;
    border-left: 4px solid #2196f3;
}

.physics-title {
    color: #1976d2;
    font-weight: 600;
    margin-bottom: 10px;
}

.concept-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    margin: 30px 0;
}

.concept-card {
    background: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    border-top: 4px solid #667eea;
}

.concept-title {
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
        <h1 class="lesson-title">⚾ Lesson 2: Ball Physics & Collision</h1>
        <p class="lesson-subtitle">Master ball movement, bouncing, and collision detection</p>
    </div>

    <div class="navigation-bar">
        <a href="/function_breakout_lesson1" class="nav-link">← Lesson 1: Paddle</a>
        <div style="color: #666; font-weight: 600;">Lesson 2 of 3</div>
        <a href="/function_breakout_lesson3" class="nav-link">Lesson 3: Power-ups →</a>
    </div>

    <div class="lesson-goals">
        <h2 class="goals-title">🎯 Learning Goals</h2>
        <p>In this lesson, you'll learn how to:</p>
        <ul>
            <li>Create a bouncing ball with realistic physics</li>
            <li>Implement collision detection with walls and paddle</li>
            <li>Understand velocity vectors and movement</li>
            <li>Combine ball physics with paddle interaction</li>
        </ul>
    </div>

    <div class="concept-grid">
        <div class="concept-card">
            <h3 class="concept-title">🌐 Velocity Vectors</h3>
            <p>Ball movement uses X and Y velocity components that determine speed and direction.</p>
        </div>
        <div class="concept-card">
            <h3 class="concept-title">🔄 Collision Detection</h3>
            <p>Check when the ball hits walls or paddle, then reverse appropriate velocity components.</p>
        </div>
        <div class="concept-card">
            <h3 class="concept-title">🎯 Game Loop Integration</h3>
            <p>Update ball position each frame and handle all interactions smoothly.</p>
        </div>
    </div>

    <div class="demo-container">
        <h3 class="demo-title">🎮 Demo 1: Ball Bouncing</h3>
        <p style="text-align: center; color: #666; margin-bottom: 20px;">
            Watch the ball bounce around with realistic physics!
        </p>

        <label class="toggle-label">
            <input type="checkbox" id="toggle-ball"> Show Code
        </label>

        <div id="wrap-ball">
            <canvas id="ballDemo" width="400" height="200" style="background:white; border:2px solid #333; display:block; margin:0 auto; border-radius: 8px;"></canvas>
        </div>

        <pre id="code-ball" style="display:none;"><code>const bCanvas = document.getElementById("ballDemo");
const bCtx = bCanvas.getContext("2d");
let bx = bCanvas.width/2, by = bCanvas.height/2;
let bvx = 2, bvy = 2, br = 8;

function drawBallDemo() {
  bCtx.clearRect(0,0,bCanvas.width,bCanvas.height);
  
  // Draw ball
  bCtx.beginPath();
  bCtx.arc(bx, by, br, 0, Math.PI*2);
  bCtx.fillStyle = "#DD0000";
  bCtx.fill();
  bCtx.closePath();
  
  // Update position
  bx += bvx; 
  by += bvy;
  
  // Bounce off walls
  if (bx+br > bCanvas.width || bx-br < 0) bvx = -bvx;
  if (by+br > bCanvas.height || by-br < 0) bvy = -bvy;
  
  requestAnimationFrame(drawBallDemo);
}
drawBallDemo();</code></pre>

        <script>
        const bCanvas = document.getElementById("ballDemo");
        const bCtx = bCanvas.getContext("2d");
        let bx = bCanvas.width/2, by = bCanvas.height/2, bvx = 2, bvy = 2, br = 8;

        function drawBallDemo() {
            bCtx.clearRect(0,0,bCanvas.width,bCanvas.height);
            bCtx.beginPath();
            bCtx.arc(bx, by, br, 0, Math.PI*2);
            bCtx.fillStyle = "#DD0000";
            bCtx.fill();
            bCtx.closePath();
            bx += bvx; by += bvy;
            if (bx+br > bCanvas.width || bx-br < 0) bvx = -bvx;
            if (by+br > bCanvas.height || by-br < 0) bvy = -bvy;
            requestAnimationFrame(drawBallDemo);
        }
        drawBallDemo();

        (function(){
            const toggle = document.getElementById("toggle-ball");
            const wrap = document.getElementById("wrap-ball");
            const code = document.getElementById("code-ball");
            toggle.checked = false;
            toggle.addEventListener("change", () => {
                if (toggle.checked) { wrap.style.display = "none"; code.style.display = "block"; }
                else { code.style.display = "none"; wrap.style.display = "block"; }
            });
        })();
        </script>
    </div>

    <div class="physics-explanation">
        <div class="physics-title">🔬 Physics Breakdown</div>
        <ul>
            <li><strong>Position:</strong> <code>bx, by</code> - Current ball location</li>
            <li><strong>Velocity:</strong> <code>bvx, bvy</code> - Speed and direction per frame</li>
            <li><strong>Collision:</strong> When <code>bx + radius > canvas.width</code>, reverse X velocity</li>
            <li><strong>Smooth Animation:</strong> <code>requestAnimationFrame()</code> for 60fps updates</li>
        </ul>
    </div>

    <div class="demo-container">
        <h3 class="demo-title">🎮 Demo 2: Paddle + Ball Interaction</h3>
        <p style="text-align: center; color: #666; margin-bottom: 20px;">
            <strong>Use arrow keys</strong> to move the paddle and bounce the ball!
        </p>

        <label class="toggle-label">
            <input type="checkbox" id="toggle-combo"> Show Code
        </label>

        <div id="wrap-combo">
            <canvas id="comboDemo" width="400" height="200" style="background:white; border:2px solid #333; display:block; margin:0 auto; border-radius: 8px;"></canvas>
        </div>

        <pre id="code-combo" style="display:none;"><code>const cCanvas = document.getElementById("comboDemo");
const cCtx = cCanvas.getContext("2d");
let cx = cCanvas.width/2, cy = cCanvas.height-30;
let cvx = 2, cvy = -2, cr = 8;
let cpX = (cCanvas.width - 75)/2, cRight = false, cLeft = false;

document.addEventListener("keydown", e => {
  if (e.key === "ArrowRight") cRight = true;
  if (e.key === "ArrowLeft") cLeft = true;
});

document.addEventListener("keyup", e => {
  if (e.key === "ArrowRight") cRight = false;
  if (e.key === "ArrowLeft") cLeft = false;
});

function drawComboDemo() {
  cCtx.clearRect(0,0,cCanvas.width,cCanvas.height);
  
  // Draw ball
  cCtx.beginPath();
  cCtx.arc(cx, cy, cr, 0, Math.PI*2);
  cCtx.fillStyle = "#DD0000";
  cCtx.fill();
  cCtx.closePath();
  
  // Draw paddle
  cCtx.fillStyle = "#0095DD";
  cCtx.fillRect(cpX, cCanvas.height-10, 75, 10);
  
  // Update ball
  cx += cvx; cy += cvy;
  
  // Ball collisions
  if (cx+cr > cCanvas.width || cx-cr < 0) cvx = -cvx;
  if (cy-cr < 0) cvy = -cvy;
  else if (cy+cr > cCanvas.height-10 && cx > cpX && cx < cpX+75) cvy = -cvy;
  else if (cy+cr > cCanvas.height) { cx = cCanvas.width/2; cy = cCanvas.height-30; cvy = -2; }
  
  // Update paddle
  if (cRight && cpX < cCanvas.width-75) cpX += 5;
  if (cLeft && cpX > 0) cpX -= 5;
  
  requestAnimationFrame(drawComboDemo);
}
drawComboDemo();</code></pre>

        <script>
        const cCanvas = document.getElementById("comboDemo");
        const cCtx = cCanvas.getContext("2d");
        let cx = cCanvas.width/2, cy = cCanvas.height-30, cvx = 2, cvy = -2, cr = 8;
        let cpX = (cCanvas.width - 75)/2, cRight = false, cLeft = false;

        document.addEventListener("keydown", e => {
            if (e.key === "ArrowRight") cRight = true;
            if (e.key === "ArrowLeft") cLeft = true;
        });
        document.addEventListener("keyup", e => {
            if (e.key === "ArrowRight") cRight = false;
            if (e.key === "ArrowLeft") cLeft = false;
        });

        function drawComboDemo() {
            cCtx.clearRect(0,0,cCanvas.width,cCanvas.height);
            cCtx.beginPath();
            cCtx.arc(cx, cy, cr, 0, Math.PI*2);
            cCtx.fillStyle = "#DD0000";
            cCtx.fill();
            cCtx.closePath();
            cCtx.fillStyle = "#0095DD";
            cCtx.fillRect(cpX, cCanvas.height-10, 75, 10);
            cx += cvx; cy += cvy;
            if (cx+cr > cCanvas.width || cx-cr < 0) cvx = -cvx;
            if (cy-cr < 0) cvy = -cvy;
            else if (cy+cr > cCanvas.height-10 && cx > cpX && cx < cpX+75) cvy = -cvy;
            else if (cy+cr > cCanvas.height) { cx = cCanvas.width/2; cy = cCanvas.height-30; cvy = -2; }
            if (cRight && cpX < cCanvas.width-75) cpX += 5;
            if (cLeft && cpX > 0) cpX -= 5;
            requestAnimationFrame(drawComboDemo);
        }
        drawComboDemo();

        (function(){
            const toggle = document.getElementById("toggle-combo");
            const wrap = document.getElementById("wrap-combo");
            const code = document.getElementById("code-combo");
            toggle.checked = false;
            toggle.addEventListener("change", () => {
                if (toggle.checked) { wrap.style.display = "none"; code.style.display = "block"; }
                else { code.style.display = "none"; wrap.style.display = "block"; }
            });
        })();
        </script>
    </div>

    <div class="physics-explanation">
        <div class="physics-title">🎯 Collision Detection Logic</div>
        <pre><code>// Paddle collision check
if (cy + cr > cCanvas.height - 10 &&    // Ball reaches paddle level
    cx > cpX &&                         // Ball is within paddle left edge
    cx < cpX + 75) {                    // Ball is within paddle right edge
    cvy = -cvy;                         // Reverse Y velocity (bounce up)
}</code></pre>
        <p>This creates realistic paddle bouncing by checking both position and boundaries!</p>
    </div>

    <div class="quiz-section">
        <h3 style="margin-bottom: 15px;">📝 Physics Challenge</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Test your understanding of ball physics and collision detection!</p>
        <a href="#quiz" class="action-button" onclick="showQuiz2()">Take Quiz</a>
    </div>

    <div class="whiteboard-section">
        <h3 style="margin-bottom: 15px;">🎨 Design Ball Trajectories</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Sketch different ball paths and collision scenarios!</p>
        <a href="#whiteboard" class="action-button" onclick="showWhiteboard2()">Open Whiteboard</a>
    </div>

    <div style="text-align: center; margin-top: 40px; padding: 25px; background: linear-gradient(135deg, #00b894 0%, #00a085 100%); border-radius: 12px; color: white;">
        <h3 style="margin-bottom: 15px;">🚀 Physics Mastered!</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">You now understand ball movement and collisions. Ready to add some exciting power-ups?</p>
        <a href="/function_breakout_lesson3" style="display: inline-block; padding: 15px 30px; background: white; color: #00b894; border-radius: 25px; text-decoration: none; font-weight: 600; transition: all 0.3s ease;">
            Continue to Lesson 3: Power-ups & Polish →
        </a>
    </div>
</div>

<script>
function showQuiz2() {
    alert("Quiz functionality coming soon! Try experimenting with the ball velocity values in the demos above.");
}

function showWhiteboard2() {
    alert("Whiteboard functionality coming soon! For now, try drawing different collision scenarios on paper.");
}
</script>