---
layout: post
title: Functional Breakout - Game & Lessons
author: Nikhil, Rohan, Pranav, Aditya, Shriya, Samhita
permalink: /function_breakout
---

<style>
.functional-hub {
    max-width: 1000px;
    margin: 0 auto;
    padding: 20px;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.hub-header {
    text-align: center;
    margin-bottom: 40px;
}

.hub-title {
    color: #2c3e50;
    font-size: 2.2em;
    margin-bottom: 15px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

.hub-description {
    color: #7f8c8d;
    font-size: 1.1em;
    line-height: 1.6;
    max-width: 600px;
    margin: 0 auto;
}

.navigation-flow {
    margin: 40px 0;
    padding: 30px;
    background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
    border-radius: 15px;
    border-left: 5px solid #667eea;
}

.flow-title {
    font-size: 1.3em;
    color: #2c3e50;
    margin-bottom: 20px;
    text-align: center;
}

.lesson-path {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    gap: 15px;
}

.lesson-node {
    background: white;
    padding: 15px 20px;
    border-radius: 25px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    text-decoration: none;
    color: #2c3e50;
    font-weight: 600;
    transition: all 0.3s ease;
    border: 2px solid transparent;
}

.lesson-node:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
    border-color: #667eea;
    color: #667eea;
}

.lesson-node.current {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
}

.arrow {
    font-size: 1.5em;
    color: #667eea;
}

.game-section {
    margin: 40px 0;
    padding: 30px;
    background: linear-gradient(135deg, #ffeaa7 0%, #fab1a0 100%);
    border-radius: 15px;
    text-align: center;
}

.game-title {
    font-size: 1.4em;
    color: #2d3436;
    margin-bottom: 15px;
}

.game-description {
    color: #636e72;
    margin-bottom: 25px;
    line-height: 1.6;
}

.play-button {
    display: inline-block;
    padding: 15px 30px;
    background: linear-gradient(135deg, #fd79a8 0%, #e84393 100%);
    color: white;
    text-decoration: none;
    border-radius: 30px;
    font-weight: 600;
    font-size: 1.1em;
    transition: all 0.3s ease;
    box-shadow: 0 5px 15px rgba(232, 67, 147, 0.3);
}

.play-button:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 25px rgba(232, 67, 147, 0.4);
    color: white;
}

.learning-objectives {
    margin: 40px 0;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
}

.objective-card {
    background: white;
    padding: 25px;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    border-left: 4px solid #667eea;
}

.objective-title {
    font-size: 1.2em;
    color: #2c3e50;
    margin-bottom: 10px;
    font-weight: 600;
}

.objective-list {
    list-style: none;
    padding: 0;
}

.objective-list li {
    margin: 8px 0;
    padding-left: 20px;
    position: relative;
    color: #5a6c7d;
}

.objective-list li::before {
    content: '•';
    position: absolute;
    left: 0;
    color: #667eea;
    font-weight: bold;
    font-size: 1.2em;
}

@media (max-width: 768px) {
    .lesson-path {
        flex-direction: column;
    }
    
    .arrow {
        transform: rotate(90deg);
    }
    
    .hub-title {
        font-size: 1.8em;
    }
}
</style>

<div class="functional-hub">
    <div class="hub-header">
        <h1 class="hub-title">🛠️ Functional Breakout</h1>
        <p class="hub-description">
            Master game development fundamentals using functional programming. Learn to build interactive games step-by-step with hands-on coding, interactive demos, and comprehensive exercises.
        </p>
    </div>

    <div class="navigation-flow">
        <h2 class="flow-title">📚 Learning Path</h2>
        <div class="lesson-path">
            <a href="/function_breakout_lesson1" class="lesson-node">
                Lesson 1: Paddle Basics
            </a>
            <span class="arrow">→</span>
            <a href="/function_breakout_lesson2" class="lesson-node">
                Lesson 2: Ball Physics
            </a>
            <span class="arrow">→</span>
            <a href="/function_breakout_lesson3" class="lesson-node">
                Lesson 3: Power-ups & Polish
            </a>
        </div>
    </div>

    <div class="game-section">
        <h2 class="game-title">🎮 Play the Full Game</h2>
        <p class="game-description">
            Ready to test your skills? Play the complete functional breakout game with all the features you'll learn to build in the lessons.
        </p>
        <a href="/full_breakout" class="play-button">🕹️ Play Now</a>
    </div>

    <div class="learning-objectives">
        <div class="objective-card">
            <h3 class="objective-title">🎯 What You'll Learn</h3>
            <ul class="objective-list">
                <li>Canvas drawing and animation</li>
                <li>Keyboard input handling</li>
                <li>Collision detection basics</li>
                <li>Game state management</li>
                <li>Event-driven programming</li>
            </ul>
        </div>

        <div class="objective-card">
            <h3 class="objective-title">🛠️ Skills You'll Build</h3>
            <ul class="objective-list">
                <li>JavaScript fundamentals</li>
                <li>DOM manipulation</li>
                <li>Mathematical concepts in games</li>
                <li>Debugging techniques</li>
                <li>Code organization</li>
            </ul>
        </div>

        <div class="objective-card">
            <h3 class="objective-title">🎨 Interactive Features</h3>
            <ul class="objective-list">
                <li>Live coding demonstrations</li>
                <li>Progressive complexity demos</li>
                <li>Hands-on quizzes</li>
                <li>Digital whiteboard exercises</li>
                <li>Customization challenges</li>
            </ul>
        </div>
    </div>

    <div style="text-align: center; margin-top: 40px; padding: 25px; background: linear-gradient(135deg, #00b894 0%, #00a085 100%); border-radius: 12px; color: white;">
        <h3 style="margin-bottom: 10px;">🚀 Ready to Start?</h3>
        <p style="margin-bottom: 20px; opacity: 0.9;">Begin your functional programming journey with hands-on game development!</p>
        <a href="/function_breakout_lesson1" style="display: inline-block; padding: 12px 25px; background: white; color: #00b894; border-radius: 25px; text-decoration: none; font-weight: 600; transition: all 0.3s ease;">
            Start Lesson 1 →
        </a>
    </div>
</div>