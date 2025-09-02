# Czehamford
from flask import Flask, render_template_string

app = Flask(__name__)

# Navigation template (reusable)
nav = """
<nav>
    <a href="/">Home</a> |
    <a href="/about">About</a> |
    <a href="/portfolio">Portfolio</a>
</nav>
<hr>
"""

@app.route("/")
def home():
    return render_template_string(f"""
        <html>
            <head><title>Home - Mini Portfolio</title></head>
            <body>
                {nav}
                <h1>welcome to my protfolio</h1>
                <p>Czehamford Hall</p>
            </body>
        </html>
    """)

@app.route("/about")
def about():
    return render_template_string(f"""
        <html>
            <head><title>About - Mini Portfolio</title></head>
            <body>
                {nav}
                <h1>About Me</h1>
                <p>This is the about page.</p>
            </body>
        </html>
    """)

@app.route("/portfolio")
def portfolio():
    return render_template_string(f"""
        <html>
            <head><title>Portfolio - Mini Portfolio</title></head>
            <body>
                {nav}
                <h1>My Portfolio</h1>
                <p>This is the portfolio page.</p>
            </body>
        </html>
    """)

if __name__ == "__main__":
    app.run(debug=True)
