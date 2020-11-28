# kuba20032003.github.io
#My site
<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
          integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
    <title>{{ title }}</title>
</head>
<body>


<nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="/">Navbar</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
            aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
            <li class="nav-item"><a class="nav-link" href="/">Главная</a></li>
            <li class="nav-item"><a class="nav-link" href="/">Добавить новость</a></li>
        </ul>
    </div>
</nav>

<div class="container mt-3">
    <h1>{{ title }}</h1>
    <div class="row">
        <div class="col-md-12">
            {% for item in news %}
            <div class="card mb-3">
                <div class="card-header">
                    <b> Категория:</b> {{ item.category }}
                </div>
                <div class="card-body">
                    <div class="media">
                        {% if item.photo %}
                        <img src="{{ item.photo.url }}" alt="" width="350" class="mr-3">
                        {% else %}
                        <img src="https://picsum.photos/id/1060/350/235/?blur=2" alt="" class="mr-3">
                        {% endif %}
                        <div class="media-body">
                            <h5 class="card-title">{{ item.title }}</h5>
                            <p class="card-text">{{ item.content|safe|linebreaks|truncatewords:50 }}</p>
                            <a href="#" class="btn btn-primary">Прочитать...</a>
                        </div>
                    </div>
                </div>
                <div class="card-footer text-muted">
                  <b>{ item.created_at|timesince}}</b>
                </div>
            </div>
            {% endfor %}
        </div>
    </div>
</div>


<script src="https://code.jquery.com/jquery-3.4.1.slim.min.js"
        integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n"
        crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
        integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo"
        crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"
        integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6"
        crossorigin="anonymous"></script>
</body>
</html>

