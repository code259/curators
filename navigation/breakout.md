---
layout: post
title: Breakout Lessons Hub
author: Nikhil, Rohan, Pranav, Aditya, Shriya, Samhita
permalink: /breakout
---

<style>
.lesson-hub {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.hub-title {
    text-align: center;
    color: #2c3e50;
    margin-bottom: 40px;
    font-size: 2.5em;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

.hub-subtitle {
    text-align: center;
    color: #7f8c8d;
    margin-bottom: 50px;
    font-size: 1.2em;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
}

.cards-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
    gap: 30px;
    margin-top: 40px;
}

.lesson-card {
    background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
    border-radius: 20px;
    padding: 30px;
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease;
    border: 1px solid rgba(255, 255, 255, 0.2);
    position: relative;
    overflow: hidden;
}

.lesson-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 4px;
    background: linear-gradient(90deg, #667eea, #764ba2);
}

.lesson-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
}

.card-header {
    margin-bottom: 20px;
}

.card-title {
    font-size: 1.8em;
    color: #2c3e50;
    margin-bottom: 10px;
    font-weight: 600;
}

.card-description {
    color: #5a6c7d;
    line-height: 1.6;
    margin-bottom: 25px;
}

.card-features {
    list-style: none;
    padding: 0;
    margin: 20px 0;
}

.card-features li {
    color: #34495e;
    margin: 8px 0;
    padding-left: 20px;
    position: relative;
}

.card-features li::before {
    content: '✓';
    position: absolute;
    left: 0;
    color: #27ae60;
    font-weight: bold;
}

.card-buttons {
    display: flex;
    gap: 15px;
    margin-top: 25px;
}

.btn {
    padding: 12px 24px;
    border: none;
    border-radius: 25px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    text-decoration: none;
    display: inline-block;
    text-align: center;
    flex: 1;
}

.btn-lesson {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
}

.btn-lesson:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(102, 126, 234, 0.4);
}

.btn-game {
    background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
    color: white;
}

.btn-game:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(245, 87, 108, 0.4);
}

.difficulty-badge {
    position: absolute;
    top: 15px;
    right: 15px;
    padding: 5px 12px;
    border-radius: 15px;
    font-size: 12px;
    font-weight: 600;
    text-transform: uppercase;
}

.difficulty-beginner {
    background: #2ecc71;
    color: white;
}

.difficulty-intermediate {
    background: #f39c12;
    color: white;
}

@media (max-width: 768px) {
    .cards-container {
        grid-template-columns: 1fr;
    }
    
    .card-buttons {
        flex-direction: column;
    }
    
    .hub-title {
        font-size: 2em;
    }
}
</style>

<div class="lesson-hub">
    <h1 class="hub-title">🎮 Breakout Game Learning Hub</h1>
    <p class="hub-subtitle">
        Master game development through two comprehensive learning paths. Start with functional programming fundamentals, then advance to object-oriented design patterns.
    </p>

    <div class="cards-container">
        <!-- Card 1: Functional Breakout -->
        <div class="lesson-card">
            <div class="difficulty-badge difficulty-beginner">Beginner</div>
            <div class="card-header">
                <h2 class="card-title">🛠️ Functional Breakout</h2>
                <p class="card-description">
                    Learn the fundamentals of game development using functional programming. Build your breakout game step-by-step with interactive demos and hands-on coding.
                </p>
            </div>
            
            <ul class="card-features">
                <li>Paddle movement and controls</li>
                <li>Ball physics and bouncing</li>
                <li>Power-ups and special effects</li>
                <li>Interactive quizzes and whiteboard</li>
            </ul>

            <div class="card-buttons">
                <a href="/function_breakout" class="btn btn-lesson">📚 Start Lessons</a>
                <a href="/function_breakout" class="btn btn-game">🎮 Play Game</a>
            </div>
        </div>

        <!-- Card 2: OOP Breakout -->
        <div class="lesson-card">
            <div class="difficulty-badge difficulty-intermediate">Intermediate</div>
            <div class="card-header">
                <h2 class="card-title">🏗️ OOP Breakout</h2>
                <p class="card-description">
                    Advance to object-oriented programming principles. Learn inheritance, composition, and encapsulation while building a sophisticated breakout game.
                </p>
            </div>
            
            <ul class="card-features">
                <li>Classes and inheritance patterns</li>
                <li>GameObject composition</li>
                <li>Advanced game mechanics</li>
                <li>Code architecture and design</li>
            </ul>

            <div class="card-buttons">
                <a href="/oop_breakout_lesson1" class="btn btn-lesson">📚 Start Lessons</a>
                <a href="/oop_breakout" class="btn btn-game">🎮 Play Game</a>
            </div>
        </div>
    </div>

    <div style="text-align: center; margin-top: 50px; padding: 30px; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); border-radius: 15px; color: white;">
        <h3 style="margin-bottom: 15px;">🎯 Learning Path Recommendation</h3>
        <p style="margin: 0; opacity: 0.9;">
            New to programming? Start with <strong>Functional Breakout</strong> to learn the basics. 
            Ready for advanced concepts? Jump into <strong>OOP Breakout</strong> for sophisticated design patterns.
        </p>
    </div>
</div>