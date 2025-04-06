<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multi-Application Webpage</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background: #35424a;
            color: white;
            padding: 20px 0;
            text-align: center;
        }
        nav {
            margin: 20px 0;
        }
        nav a {
            margin: 0 15px;
            text-decoration: none;
            color: #35424a;
        }
        .container {
            width: 80%;
            margin: auto;
            overflow: hidden;
        }
        section {
            background: white;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        footer {
            background: #35424a;
            color: white;
            text-align: center;
            padding: 10px 0;
            position: relative;
            bottom: 0;
            width: 100%;
        }
        .todo-list {
            list-style-type: none;
            padding: 0;
        }
        .todo-list li {
            padding: 5px;
            border-bottom: 1px solid #ccc;
        }
    </style>
</head>
<body>

<header>
    <h1>Multi-Application Webpage</h1>
</header>

<nav>
    <div class="container">
        <a href="#calculator">Calculator</a>
        <a href="#todo">To-Do List</a>
        <a href="#weather">Weather Widget</a>
        <a href="#contact">Contact Form</a>
    </div>
</nav>

<div class="container">
    <section id="calculator">
        <h2>Calculator</h2>
        <input type="text" id="calcInput" placeholder="Enter calculation">
        <button onclick="calculate()">Calculate</button>
        <p id="calcResult"></p>
    </section>

    <section id="todo">
        <h2>To-Do List</h2>
        <input type="text" id="todoInput" placeholder="Add a new task">
        <button onclick="addTodo()">Add</button>
        <ul class="todo-list" id="todoList"></ul>
    </section>

    <section id="weather">
        <h2>Weather Widget</h2>
        <input type="text" id="cityInput" placeholder="Enter city name">
        <button onclick="getWeather()">Get Weather</button>
        <p id="weatherResult"></p>
    </section>

    <section id="contact">
        <h2>Contact Form</h2>
        <form onsubmit="submitForm(event)">
            <input type="text" placeholder="Your Name" required><br><br>
            <input type="email" placeholder="Your Email" required><br><br>
            <textarea placeholder="Your Message" required></textarea><br><br>
            <button type="submit">Send Message</button>
        </form>
    </section>
</div>

<footer>
    <p>&copy; 2023 Multi-Application Webpage</p>
</footer>

<script>
    // Calculator Function
    function calculate() {
        const input = document.getElementById('calcInput').value;
        try {
            const result = eval(input);
            document.getElementById('calcResult').innerText = "Result: " + result;
        } catch (error) {
            document.getElementById('calcResult').innerText = "Error in calculation.";
        }
    }

    // To-Do List Functionality
    function addTodo() {
        const todoInput = document.getElementById('todoInput');
        const todoText = todoInput.value.trim();
        if (todoText) {
            const li = document.createElement('li');
            li.textContent = todoText;
            document.getElementById('todoList').appendChild(li);
