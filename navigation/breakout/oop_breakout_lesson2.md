---
layout: post
title: OOP Breakout - Lesson 2: Attributes vs Methods
author: Nikhil, Rohan, Pranav, Aditya, Shriya, Samhita
permalink: /oop_breakout_lesson2
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

.attributes-methods {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    gap: 30px;
    margin: 30px 0;
}

.attribute-card, .method-card {
    padding: 25px;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

.attribute-card {
    background: linear-gradient(135deg, #ffeaa7 0%, #fab1a0 100%);
    border-left: 5px solid #e17055;
}

.method-card {
    background: linear-gradient(135deg, #74b9ff 0%, #0984e3 100%);
    border-left: 5px solid #0984e3;
    color: white;
}

.card-title {
    font-size: 1.3em;
    margin-bottom: 15px;
    font-weight: 600;
}

.attribute-card .card-title {
    color: #2d3436;
}

.method-card .card-title {
    color: white;
}

.code-example {
    background: #1e1e1e;
    color: #d4d4d4;
    padding: 20px;
    border-radius: 8px;
    overflow-x: auto;
    margin: 15px 0;
}

.explanation-box {
    background: #f0f8ff;
    padding: 20px;
    border-radius: 10px;
    margin: 20px 0;
    border-left: 4px solid #2196f3;
}

.explanation-title {
    color: #1976d2;
    font-weight: 600;
    margin-bottom: 10px;
}

.method-categories {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    margin: 30px 0;
}

.category-card {
    background: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    border-top: 4px solid #667eea;
}

.category-title {
    color: #2c3e50;
    font-size: 1.1em;
    margin-bottom: 10px;
    font-weight: 600;
}

.try-it-box {
    background: #fff3cd;
    padding: 20px;
    border-radius: 10px;
    margin: 25px 0;
    border-left: 4px solid #ffc107;
}

.try-it-title {
    color: #856404;
    font-weight: 600;
    margin-bottom: 10px;
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
    
    .attributes-methods {
        grid-template-columns: 1fr;
    }
}
</style>

<div class="lesson-container">
    <div class="lesson-header">
        <h1 class="lesson-title">🎯 Lesson 2: Attributes vs Methods</h1>
        <p class="lesson-subtitle">Understanding the Paddle class: what objects have vs what they do</p>
    </div>

    <div class="navigation-bar">
        <a href="/oop_breakout_lesson1" class="nav-link">← Lesson 1: Classes</a>
        <div style="color: #666; font-weight: 600;">OOP Lesson 2 of 3</div>
        <a href="/oop_breakout_lesson3" class="nav-link">Lesson 3: Constructors →</a>
    </div>

    <div class="lesson-goals">
        <h2 class="goals-title">🎯 Learning Goals</h2>
        <p>In this lesson, you'll learn:</p>
        <ul>
            <li>The difference between attributes (data) and methods (functions)</li>
            <li>How the Paddle class stores state and behavior</li>
            <li>Different types of methods: rendering, movement, and utility</li>
            <li>How to organize code using object-oriented principles</li>
        </ul>
    </div>

    <div class="attributes-methods">
        <div class="attribute-card">
            <h3 class="card-title">📊 Attributes (Properties)</h3>
            <p><strong>What objects HAVE</strong> - the data stored on an object</p>
            <ul style="margin-top: 15px;">
                <li>Position and size</li>
                <li>Current state</li>
                <li>Configuration values</li>
                <li>Input states</li>
            </ul>
        </div>
        <div class="method-card">
            <h3 class="card-title">⚡ Methods (Functions)</h3>
            <p><strong>What objects DO</strong> - functions attached to the class</p>
            <ul style="margin-top: 15px;">
                <li>Draw themselves</li>
                <li>Update position</li>
                <li>Handle interactions</li>
                <li>Reset or modify state</li>
            </ul>
        </div>
    </div>

    <h2 class="section-title">📊 Paddle Attributes: What It Has</h2>
    <p>Attributes are the data on an object - things the object <em>has</em>. Each <code>this.something = ...</code> creates an attribute:</p>

    <pre class="code-example"><code>constructor(x, y, canvasWidth, canvasHeight) {
    super(x, y);
    this.canvasWidth = canvasWidth;   // Attribute: canvas bounds
    this.canvasHeight = canvasHeight; // Attribute: canvas bounds
    this.baseWidth = 75;              // Attribute: default size
    this.width = this.baseWidth;      // Attribute: current size (can change)
    this.height = 10;                 // Attribute: height
    this.color = "#0095DD";           // Attribute: color
    this.speed = 7;                   // Attribute: movement speed
    this.leftPressed = false;         // Attribute: input state
    this.rightPressed = false;        // Attribute: input state
}</code></pre>

    <div class="explanation-box">
        <div class="explanation-title">💡 Understanding Attributes</div>
        <p>Attributes store the <strong>current state</strong> of the paddle. They can change during gameplay (like <code>width</code> when powered up) or stay constant (like <code>baseWidth</code>). Think of them as variables that belong to this specific paddle instance.</p>
    </div>

    <h2 class="section-title">⚡ Paddle Methods: What It Does</h2>
    <p>Methods are <strong>functions attached to the class</strong> that use or change those attributes. They define what the object can <em>do</em>:</p>

    <div class="method-categories">
        <div class="category-card">
            <h3 class="category-title">🎨 Rendering Methods</h3>
            <p>Handle visual display of the paddle</p>
        </div>
        <div class="category-card">
            <h3 class="category-title">🏃 Movement Methods</h3>
            <p>Update position and handle input</p>
        </div>
        <div class="category-card">
            <h3 class="category-title">🛠️ Utility Methods</h3>
            <p>Reset, power-ups, and game mechanics</p>
        </div>
    </div>

    <h3 style="color: #667eea; margin: 25px 0 15px;">🎨 Rendering Method</h3>
    <pre class="code-example"><code>draw(ctx) {
    ctx.beginPath();
    ctx.rect(this.x, this.canvasHeight - this.height, this.width, this.height);
    ctx.fillStyle = this.color;
    ctx.fill();
    ctx.closePath();
}</code></pre>
    <p>The <code>draw</code> method uses drawing APIs and current attributes to render the paddle.</p>

    <h3 style="color: #667eea; margin: 25px 0 15px;">🏃 Movement Methods</h3>
    <pre class="code-example"><code>update() {
    if (this.rightPressed && this.x < this.canvasWidth - this.width) {
        this.x += this.speed;
    } else if (this.leftPressed && this.x > 0) {
        this.x -= this.speed;
    }
}</code></pre>
    <p>The <code>update</code> method reads input states and moves the paddle within bounds.</p>

    <h3 style="color: #667eea; margin: 25px 0 15px;">🛠️ Utility Methods</h3>
    <pre class="code-example"><code>setPosition(x) {
    if (x > 0 && x < this.canvasWidth) {
        this.x = x - this.width / 2;
    }
}

reset() {
    this.x = (this.canvasWidth - this.width) / 2;
    this.width = this.baseWidth;
}

applyPowerUp(type) {
    if (type === "wide") {
        this.width = this.baseWidth + 40;
    }
}

resetPowerUp() {
    this.width = this.baseWidth;
}</code></pre>

    <div class="explanation-box">
        <div class="explanation-title">🎯 Method Benefits</div>
        <p>These methods encapsulate paddle behavior in a clean, organized way. Instead of having paddle logic scattered throughout the game, everything paddle-related is contained within the Paddle class.</p>
    </div>

    <div class="try-it-box">
        <div class="try-it-title">🚀 Try This Exercise:</div>
        <p>Add a new method <code>shrink()</code> that sets <code>this.width = this.baseWidth - 25</code>, and call it from a new "shrink" power-up type. This demonstrates how methods can modify attributes to change object behavior!</p>
    </div>

    <div class="quiz-section">
        <h3 style="margin-bottom: 15px;">📝 Attributes vs Methods Quiz</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Test your understanding of object properties and behaviors!</p>
        <a href="#quiz" class="action-button" onclick="showQuizOOP2()">Take Quiz</a>
    </div>

    <div class="whiteboard-section">
        <h3 style="margin-bottom: 15px;">🎨 Design Object Structure</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Draw a class diagram showing attributes inside and methods outside!</p>
        <a href="#whiteboard" class="action-button" onclick="showWhiteboardOOP2()">Open Whiteboard</a>
    </div>

    <div style="text-align: center; margin-top: 40px; padding: 25px; background: linear-gradient(135deg, #00b894 0%, #00a085 100%); border-radius: 12px; color: white;">
        <h3 style="margin-bottom: 15px;">🎓 Data & Behavior Mastered!</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">You now understand how objects store data and define behavior. Ready to explore constructors and the Ball class?</p>
        <a href="/oop_breakout_lesson3" style="display: inline-block; padding: 15px 30px; background: white; color: #00b894; border-radius: 25px; text-decoration: none; font-weight: 600; transition: all 0.3s ease;">
            Continue to Lesson 3: Constructors & Ball Class →
        </a>
    </div>
</div>

<script>
function showQuizOOP2() {
    alert("Quiz functionality coming soon! Think about: What are attributes of the Paddle? Which methods modify paddle state?");
}

function showWhiteboardOOP2() {
    alert("Whiteboard functionality coming soon! Try drawing a class box with attributes listed inside and methods listed outside.");
}
</script>