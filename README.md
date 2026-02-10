# Ex.04 Design a Website for Server Side Processing
# Date:
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
views.py
```
from django.shortcuts import render
def power(request):
    power=''
    if request.method == "POST":
        intensity = float(request.POST.get("intensity"))
        resistance = float(request.POST.get("resistance"))
        power=intensity**2*resistance
        print(f"Intensity: {intensity}, Resistance: {resistance},Power:{power:.2f}")
    return render(request, 'pow.html', {'power':power})
```
urls.py
```
from django.contrib import admin
from django.urls import path
from mathapp import views



urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.power,name='power'),
]
```
pow.html
```
{% load static %}
<html>
<head>
    <title>Power Calculation</title>

    <style>
        body{
            text-align:center;
            background: linear-gradient(blue,white);
            font-family: Arial, sans-serif;
            padding-top:50px;
        }

        .container{
            width:350px;
            background:#fff0e0;
            padding:20px;
            border-radius:10px;
            margin:auto;
            border:2px solid #b5302c;
        }

        h1{
            color:#b5302c;
            font-size:28px;
        }

        label{
            color:#333;
            font-size:16px;
        }

        input{
            width:90%;
            padding:8px;
            margin-top:8px;
            margin-bottom:15px;
            border:1px solid #b5302c;
            border-radius:5px;
        }

        button{
            width:100%;
            padding:10px;
            background:#c43b34;
            color:white;
            border:none;
            border-radius:5px;
            cursor:pointer;
        }

        button:hover{
            background:#da4a44;
        }
    </style>

</head>

<body>

<div class="container">
<h1>Power Calculator</h1>

<form method="POST">
    {% csrf_token %}

    <label>Intensity:</label><br>
    <input type="number" name="intensity" required placeholder="Enter in cd"><br>

    <label>Resistance:</label><br>
    <input type="number" name="resistance" required placeholder="Enter in Ohms"><br>

    <button type="submit">Calculate</button><br><br>

    <label>Power:</label><br>
    <input type="text" value="{{ power }}" readonly> Watts

</form>
</div>

</body>
</html>
```
# SERVER SIDE PROCESSING:
![alt text](<Screenshot 2025-12-10 093150.png>)

# OUTPUT:
![alt text](<Screenshot 2025-12-10 094053.png>)

# RESULT:
The program for performing server side processing is completed successfully.
