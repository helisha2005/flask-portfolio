# flask-portfolio
from flask import Flask, render_template



app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

if __name__ == '__main__':
    app.run(debug=True)

index.html
{% extends 'base.html' %}

{% block content %}
<section>
    <h2>About Me</h2>
    <p>Hello! I'm a developer .</p>
</section>

<section>
    <h2>Projects</h2>
    <ul>
        <li><strong>Project 1:</strong> flask</li>
        <li><strong>Project 2:</strong> api</li>
        <!-- Add more projects -->
    </ul>
</section>

<section>
    <h2>Contact</h2>
    <p>Email: abc2025@gmail.com</p>

  base.html
  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Portfolio</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='styles.css') }}">
</head>
<body>
    <header>
        <h1>My Portfolio</h1>
        <nav>
            <a href="/">Home</a>
            <!-- Add more navigation links if needed -->
        </nav>
    </header>
    <main>
        {% block content %}{% endblock %}
    </main>
    <footer>
        <p>&copy; 2025 </p>
    </footer>
</body>
</html>



styles.css

body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background: #f4f4f4;
    color: #333;
}

header, footer {
    background: #333;
    color: #fff;
    padding: 1rem;
    text-align: center;
}

nav a {
    color: #fff;
    margin: 0 1rem;
    text-decoration: none;
}

main {
    padding: 2rem;
}

section {
    margin-bottom: 2rem;
}

</section>
{% endblock %}
