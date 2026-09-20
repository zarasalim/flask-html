# flask-html

Сайт можно посмотреть по http://127.0.0.1:5000


APP.PY

from flask import Flask, render_template

app = Flask(__name__)


@app.route("/")
def home():
    return render_template("index.html")


if __name__ == "__main__":
    app.run(debug=True)

INDEX.HTML

<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Моё Flask-приложение</title>

    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
</head>

<body>

    <h1>Моё Flask-приложение</h1>

    <p>
        Добро пожаловать на мой сайт!
        Это простое веб-приложение, созданное с помощью Flask.
    </p>

    <img src="{{ url_for('static', filename='image.png') }}"
         alt="Изображение">

</body>
</html>

STYLE.CSS

body {
    text-align: center;
}

h1 {
    font-family: Arial, sans-serif;
}

p {
    font-size: 20px;
}

img {
    display: block;
    margin: 20px auto;
    max-width: 500px;
}
