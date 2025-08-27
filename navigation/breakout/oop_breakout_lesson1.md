---
layout: post
title: OOP Breakout - Lesson 1: Classes & Inheritance
author: Nikhil, Rohan, Pranav, Aditya, Shriya, Samhita
permalink: /oop_breakout_lesson1
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

.concept-explanation {
    background: #f0f8ff;
    padding: 20px;
    border-radius: 10px;
    margin: 20px 0;
    border-left: 4px solid #2196f3;
}

.concept-title {
    color: #1976d2;
    font-weight: 600;
    margin-bottom: 10px;
}

.oop-concepts {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
    margin: 30px 0;
}

.concept-card {
    background: white;
    padding: 25px;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    border-top: 4px solid #667eea;
}

.card-title {
    color: #2c3e50;
    font-size: 1.2em;
    margin-bottom: 15px;
    font-weight: 600;
}

.card-content {
    color: #5a6c7d;
    line-height: 1.6;
}

.code-example {
    background: #1e1e1e;
    color: #d4d4d4;
    padding: 20px;
    border-radius: 8px;
    overflow-x: auto;
    margin: 15px 0;
}

.highlight-box {
    background: #fff3cd;
    padding: 20px;
    border-radius: 10px;
    margin: 20px 0;
    border-left: 4px solid #ffc107;
}

.highlight-title {
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
}
</style>

<div class="lesson-container">
    <div class="lesson-header">
        <h1 class="lesson-title">🏗️ Lesson 1: Classes & Inheritance</h1>
        <p class="lesson-subtitle">Understanding the Game class and how inheritance works in OOP</p>
    </div>

    <div class="navigation-bar">
        <a href="/breakout" class="nav-link">← Back to Hub</a>
        <div style="color: #666; font-weight: 600;">OOP Lesson 1 of 3</div>
        <a href="/oop_breakout_lesson2" class="nav-link">Next: Attributes vs Methods →</a>
    </div>

    <div class="lesson-goals">
        <h2 class="goals-title">🎯 Learning Goals</h2>
        <p>In this lesson, you'll learn:</p>
        <ul>
            <li>The difference between inheritance and composition</li>
            <li>How the GameObject base class provides shared functionality</li>
            <li>How Ball, Paddle, and Brick inherit from GameObject</li>
            <li>How the Game class uses composition to manage objects</li>
        </ul>
    </div>

    <div class="oop-concepts">
        <div class="concept-card">
            <h3 class="card-title">🧬 Inheritance</h3>
            <div class="card-content">
                <p>Inheritance lets a class reuse and extend behavior from a parent (base) class. Classes can inherit properties and methods, then override or add their own.</p>
            </div>
        </div>
        <div class="concept-card">
            <h3 class="card-title">🧩 Composition</h3>
            <div class="card-content">
                <p>Composition is when a class "has-a" relationship with other objects. The Game class doesn't inherit - it owns and manages Ball, Paddle, and Bricks.</p>
            </div>
        </div>
    </div>

    <h2 class="section-title">🔧 Base Class: GameObject</h2>
    <p>The <code>GameObject</code> class provides common functionality that all visual game objects need:</p>

    <pre class="code-example"><code>// Base GameObject class - provides common functionality
class GameObject {
    constructor(x, y) {
        this.x = x;
        this.y = y;
    }
    
    draw(ctx) {
        // Base draw method - to be overridden
    }
    
    update() {
        // Base update method - to be overridden
    }
}</code></pre>

    <div class="concept-explanation">
        <div class="concept-title">💡 Why Use a Base Class?</div>
        <p>This tiny class centralizes shared properties like position (<code>x</code>, <code>y</code>) and provides placeholder methods (<code>draw</code>, <code>update</code>) for subclasses to override. This eliminates code duplication and creates a consistent interface.</p>
    </div>

    <h2 class="section-title">🎯 Subclasses: Ball and Paddle Inherit</h2>
    <p>Visual objects in the game inherit from GameObject using the <code>extends</code> keyword:</p>

    <pre class="code-example"><code>// Ball inherits from GameObject
class Ball extends GameObject {
    constructor(x, y) {
        super(x, y);  // Call parent constructor
        this.radius = 8;
        this.dx = 2;
        this.dy = -2;
        this.color = "#DD0000";
    }
    
    draw(ctx) {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
        ctx.fillStyle = this.color;
        ctx.fill();
        ctx.closePath();
    }
    
    update() {
        this.x += this.dx;
        this.y += this.dy;
    }
}

// Paddle also inherits from GameObject
class Paddle extends GameObject {
    constructor(x, y, canvasWidth, canvasHeight) {
        super(x, y);  // Reuse parent constructor
        this.width = 75;
        this.height = 10;
        this.speed = 7;
        this.canvasWidth = canvasWidth;
        // ... more properties
    }
    
    draw(ctx) {
        ctx.fillStyle = "#0095DD";
        ctx.fillRect(this.x, this.y, this.width, this.height);
    }
}</code></pre>

    <div class="highlight-box">
        <div class="highlight-title">🔍 Key Inheritance Concepts:</div>
        <ul>
            <li><strong>extends:</strong> Creates an inheritance relationship</li>
            <li><strong>super():</strong> Calls the parent class constructor</li>
            <li><strong>Override:</strong> Subclasses provide their own <code>draw()</code> implementation</li>
            <li><strong>Shared Properties:</strong> All inherit <code>x</code> and <code>y</code> from GameObject</li>
        </ul>
    </div>

    <h2 class="section-title">🎮 The Conductor: Game Uses Composition</h2>
    <p>The <code>Game</code> class doesn't inherit from anything. Instead, it <em>owns</em> and <em>manages</em> game objects:</p>

    <pre class="code-example"><code>class Game {
    constructor(canvas) {
        this.canvas = canvas;
        this.ctx = canvas.getContext('2d');
        this.width = canvas.width;
        this.height = canvas.height;
        
        // Composition: Game HAS these objects
        this.ball = new Ball(this.width / 2, this.height - 30);
        this.paddle = new Paddle((this.width - 75) / 2, this.height - 10, 
                                this.width, this.height);
        this.bricks = [];
        this.powerUps = [];
        
        // Game state
        this.score = 0;
        this.lives = 3;
        this.level = 1;
    }
    
    update() {
        // Orchestrate all objects
        this.ball.update();
        this.paddle.update();
        this.handleCollisions();
        this.updatePowerUps();
    }
    
    draw() {
        // Draw all objects
        this.ctx.clearRect(0, 0, this.width, this.height);
        this.ball.draw(this.ctx);
        this.paddle.draw(this.ctx);
        this.drawBricks();
    }
}</code></pre>

    <div class="concept-explanation">
        <div class="concept-title">🎯 Composition in Action</div>
        <p>The <code>Game</code> class <em>owns</em> the objects and state (score, lives, level), initializes them, and coordinates them in the game loop. This is composition - the Game <em>has-a</em> ball, paddle, and bricks rather than <em>being-a</em> type of GameObject.</p>
    </div>

    <div class="highlight-box">
        <div class="highlight-title">🚀 Try This Exercise:</div>
        <p>Add a new subclass called <code>Particle extends GameObject</code> for visual effects, then let the <code>Game</code> class hold an array of particles. This demonstrates how inheritance (Particle shape) and composition (Game owning many particles) work together!</p>
    </div>

    <div class="quiz-section">
        <h3 style="margin-bottom: 15px;">📝 Inheritance Quiz</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Test your understanding of inheritance vs composition!</p>
        <a href="#quiz" class="action-button" onclick="showQuizOOP1()">Take Quiz</a>
    </div>

    <div class="whiteboard-section">
        <h3 style="margin-bottom: 15px;">🎨 Draw Class Relationships</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Sketch the inheritance hierarchy and composition relationships!</p>
        <a href="#whiteboard" class="action-button" onclick="showWhiteboardOOP1()">Open Whiteboard</a>
    </div>

    <div style="text-align: center; margin-top: 40px; padding: 25px; background: linear-gradient(135deg, #00b894 0%, #00a085 100%); border-radius: 12px; color: white;">
        <h3 style="margin-bottom: 15px;">🎓 Excellent Progress!</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">You now understand class relationships in OOP. Ready to dive deeper into attributes and methods?</p>
        <a href="/oop_breakout_lesson2" style="display: inline-block; padding: 15px 30px; background: white; color: #00b894; border-radius: 25px; text-decoration: none; font-weight: 600; transition: all 0.3s ease;">
            Continue to Lesson 2: Attributes vs Methods →
        </a>
    </div>
</div>

<script>
function showQuizOOP1() {
    alert("Quiz functionality coming soon! Think about: Which classes inherit from GameObject? What does the Game class compose?");
}

function showWhiteboardOOP1() {
    alert("Whiteboard functionality coming soon! Try drawing boxes for each class with arrows showing inheritance relationships.");
}
</script>