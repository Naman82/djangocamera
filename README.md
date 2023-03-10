# djangocamera

A library that makes it simple to use one function to integrate a camera with the Django framework on a website.
## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install foobar.

```bash
pip install djangocamera
```

## Usage

The `views.py` file, in the `app` directory:
```python
from django.shortcuts import render
from djangocamera.streaming import video_feed

# returns 'camera video'
def camera(request):
  return video_feed()

def index(request):
  return render(request,"index.html",{})
```
The `urls.py` file, in the `app` directory:
``` python
from django.urls import path
from . import views

urlpatterns = [
    path("camera/",views.camera,name="camera"),
    path("",views.index,name="index"),
]

```
The `index.html` file, in the templates directory:
```python
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <img src="{% url 'camera' %}" alt="#" >
</body>
</html>
```
## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)

