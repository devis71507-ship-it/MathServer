# Ex.05 Design a Website for Server Side Processing
## Date:

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
html
<!DOCTYPE html>
<html>
<head>
    <title>BMI Calculator</title>
</head>
<body>
    <form method="POST">
  {% csrf_token %}
  <label>Height (cm):</label>
  <input type="text" name="height"><br>
  <label>Weight (kg):</label>

  <input type="text" name="weight"><br>

  <button type="submit">Calculate</button>
</form>

{% if BMI %}
  <h3>Your BMI is: {{ BMI }}</h3>
{% endif %}
</body>
</html>
urls.py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.calculator, name='calculator'),
]

from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('mathapp.urls')),  
]

views.py
from django.shortcuts import render

def calculator(request):
    power = None

    if request.method == 'POST':
        try:
            intensity = float(request.POST.get('intensity'))
            resistance = float(request.POST.get('resistance'))
            power = round(intensity ** 2 * resistance, 2)
        except (TypeError, ValueError):
            power = "Invalid input. Please enter numeric values."

    return render(request, 'math.html', {'power': power})

 ```   


## SERVER SIDE PROCESSING:

<img width="1920" height="1080" alt="Screenshot (28)" src="https://github.com/user-attachments/assets/1c133720-a789-40d5-89b1-2f5a88059510" />



## HOMEPAGE:
<img width="1920" height="1080" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/14ff40a3-7b41-480a-bab2-c733a03fcaba" />

<img width="1920" height="1080" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/fbdb409b-115e-4120-9db7-9468f85f858a" />


## RESULT:
The program for performing server side processing is completed successfully.
