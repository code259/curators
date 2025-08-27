---
layout: post
title: Functional Breakout - Lesson 1: Paddle Basics
author: Nikhil, Rohan, Pranav, Aditya, Shriya, Samhita
permalink: /function_breakout_lesson1
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

.nav-link.disabled {
    background: #cbd5e0;
    color: #a0aec0;
    cursor: not-allowed;
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

.code-section {
    margin: 30px 0;
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

pre {
    background: #1e1e1e;
    color: #d4d4d4;
    padding: 20px;
    border-radius: 8px;
    overflow-x: auto;
    margin: 15px 0;
}

code {
    font-family: 'Consolas', 'Monaco', 'Courier New', monospace;
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

.quiz-section {
    margin: 40px 0;
    padding: 30px;
    background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
    border-radius: 15px;
    color: white;
    text-align: center;
}

.whiteboard-section {
    margin: 40px 0;
    padding: 30px;
    background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
    border-radius: 15px;
    color: white;
    text-align: center;
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
        <h1 class="lesson-title">🛠️ Lesson 1: Paddle Basics</h1>
        <p class="lesson-subtitle">Learn to create and control the game paddle with keyboard input</p>
    </div>

    <div class="navigation-bar">
        <a href="/function_breakout" class="nav-link">← Back to Hub</a>
        <div style="color: #666; font-weight: 600;">Lesson 1 of 3</div>
        <a href="/function_breakout_lesson2" class="nav-link">Next: Ball Physics →</a>
    </div>

    <div class="lesson-goals">
        <h2 class="goals-title">🎯 Learning Goals</h2>
        <p>In this lesson, you'll learn how to:</p>
        <ul>
            <li>Draw a paddle rectangle on the canvas</li>
            <li>Handle keyboard input for left/right movement</li>
            <li>Update paddle position with boundary checking</li>
            <li>Create smooth, responsive controls</li>
        </ul>
    </div>

    <div class="code-section">
        <h2 class="section-title">🎨 Step 1: Make the Paddle</h2>
        <p>We start by drawing a rectangle at the bottom of the canvas to represent our paddle.</p>

        <pre><code>let paddleHeight = 10;
let basePaddleWidth = 75;
let paddleWidth = basePaddleWidth;
let paddleX = (canvas.width - paddleWidth) / 2;

function drawPaddle() {
  ctx.beginPath();
  ctx.rect(paddleX, canvas.height - paddleHeight, paddleWidth, paddleHeight);
  ctx.fillStyle = "#0095DD";
  ctx.fill();
  ctx.closePath();
}</code></pre>

        <p><strong>Key Concepts:</strong></p>
        <ul>
            <li><code>paddleX</code> - Horizontal position (starts centered)</li>
            <li><code>canvas.height - paddleHeight</code> - Positions paddle at bottom</li>
            <li><code>ctx.rect()</code> - Draws a rectangle shape</li>
            <li><code>ctx.fill()</code> - Fills the shape with color</li>
        </ul>
    </div>

    <div class="code-section">
        <h2 class="section-title">⌨️ Step 2: Move the Paddle</h2>
        <p>Now we add keyboard input to move the paddle left and right with arrow keys.</p>

        <pre><code>let rightPressed = false;
let leftPressed = false;

document.addEventListener("keydown", keyDownHandler);
document.addEventListener("keyup", keyUpHandler);

function keyDownHandler(e) {
  if (e.key === "Right" || e.key === "ArrowRight") rightPressed = true;
  else if (e.key === "Left" || e.key === "ArrowLeft") leftPressed = true;
}

function keyUpHandler(e) {
  if (e.key === "Right" || e.key === "ArrowRight") rightPressed = false;
  else if (e.key === "Left" || e.key === "ArrowLeft") leftPressed = false;
}

function updatePaddle() {
  if (rightPressed && paddleX < canvas.width - paddleWidth) paddleX += 7;
  else if (leftPressed && paddleX > 0) paddleX -= 7;
}</code></pre>

        <p><strong>Key Concepts:</strong></p>
        <ul>
            <li><strong>Event Listeners:</strong> Detect when keys are pressed/released</li>
            <li><strong>Boolean Flags:</strong> Track current key states</li>
            <li><strong>Boundary Checking:</strong> Prevent paddle from going off-screen</li>
            <li><strong>Movement Speed:</strong> <code>+= 7</code> controls how fast the paddle moves</li>
        </ul>

        <div class="explore-section">
            <div class="explore-title">🔍 Explore & Experiment:</div>
            <ul>
                <li>Change the movement speed from <code>7</code> to different values</li>
                <li>Modify the paddle width and height</li>
                <li>Try different colors by changing <code>"#0095DD"</code></li>
                <li>Add additional keys like WASD for movement</li>
            </ul>
        </div>
    </div>

    <div class="demo-container">
        <h3 class="demo-title">🎮 Interactive Demo: Paddle Movement</h3>
        <p style="text-align: center; color: #666; margin-bottom: 20px;">
            Use the <strong>left and right arrow keys</strong> to move the paddle!
        </p>

        <label class="toggle-label">
            <input type="checkbox" id="toggle-paddle"> Show Code
        </label>

        <div id="wrap-paddle">
            <canvas id="paddleDemo" width="400" height="200" style="background:white; border:2px solid #333; display:block; margin:0 auto; border-radius: 8px;"></canvas>
        </div>

        <pre id="code-paddle" style="display:none;"><code>const pdCanvas = document.getElementById("paddleDemo");
const pdCtx = pdCanvas.getContext("2d");
let pdX = (pdCanvas.width - 75) / 2;
let pdRight = false, pdLeft = false;

document.addEventListener("keydown", e => {
  if (e.key === "ArrowRight") pdRight = true;
  if (e.key === "ArrowLeft") pdLeft = true;
});
document.addEventListener("keyup", e => {
  if (e.key === "ArrowRight") pdRight = false;
  if (e.key === "ArrowLeft") pdLeft = false;
});

function drawPaddleDemo() {
  pdCtx.clearRect(0,0,pdCanvas.width,pdCanvas.height);
  pdCtx.fillStyle = "#0095DD";
  pdCtx.fillRect(pdX, pdCanvas.height-10, 75, 10);
  if (pdRight && pdX < pdCanvas.width-75) pdX += 5;
  if (pdLeft && pdX > 0) pdX -= 5;
  requestAnimationFrame(drawPaddleDemo);
}
drawPaddleDemo();</code></pre>

        <script>
        const pdCanvas = document.getElementById("paddleDemo");
        const pdCtx = pdCanvas.getContext("2d");
        let pdX = (pdCanvas.width - 75) / 2;
        let pdRight = false, pdLeft = false;

        document.addEventListener("keydown", e => {
            if (e.key === "ArrowRight") pdRight = true;
            if (e.key === "ArrowLeft") pdLeft = true;
        });
        document.addEventListener("keyup", e => {
            if (e.key === "ArrowRight") pdRight = false;
            if (e.key === "ArrowLeft") pdLeft = false;
        });

        function drawPaddleDemo() {
            pdCtx.clearRect(0,0,pdCanvas.width,pdCanvas.height);
            pdCtx.fillStyle = "#0095DD";
            pdCtx.fillRect(pdX, pdCanvas.height-10, 75, 10);
            if (pdRight && pdX < pdCanvas.width-75) pdX += 5;
            if (pdLeft && pdX > 0) pdX -= 5;
            requestAnimationFrame(drawPaddleDemo);
        }
        drawPaddleDemo();

        // Toggle functionality
        (function(){
            const toggle = document.getElementById("toggle-paddle");
            const wrap = document.getElementById("wrap-paddle");
            const code = document.getElementById("code-paddle");

            toggle.checked = false;
            toggle.addEventListener("change", () => {
                if (toggle.checked) {
                    wrap.style.display = "none";
                    code.style.display = "block";
                } else {
                    code.style.display = "none";
                    wrap.style.display = "block";
                }
            });
        })();
        </script>
    </div>

    <div class="quiz-section">
        <h3 style="margin-bottom: 15px;">📝 Knowledge Check</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Test your understanding of paddle basics and keyboard input!</p>
        <a href="#quiz" class="action-button" onclick="showQuiz1()">Take Quiz</a>
    </div>

    <div class="whiteboard-section">
        <h3 style="margin-bottom: 15px;">🎨 Sketch Your Understanding</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Draw the paddle movement system or design your own paddle variations!</p>
        <a href="#whiteboard" class="action-button" onclick="showWhiteboard1()">Open Whiteboard</a>
    </div>

    <div style="text-align: center; margin-top: 40px; padding: 25px; background: linear-gradient(135deg, #00b894 0%, #00a085 100%); border-radius: 12px; color: white;">
        <h3 style="margin-bottom: 15px;">🎉 Great Job!</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">You've mastered paddle creation and movement. Ready to add some ball physics?</p>
        <a href="/function_breakout_lesson2" style="display: inline-block; padding: 15px 30px; background: white; color: #00b894; border-radius: 25px; text-decoration: none; font-weight: 600; transition: all 0.3s ease;">
            Continue to Lesson 2: Ball Physics →
        </a>
    </div>
</div>

<script>
function showQuiz1() {
    alert("Quiz functionality coming soon! For now, try modifying the demo code above.");
}

function showWhiteboard1() {
    alert("Whiteboard functionality coming soon! For now, try sketching paddle movement on paper.");
}
</script>