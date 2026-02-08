# Ex.05 Design a Website for Server Side Processing
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
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculate Lamp Filament Power</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 20px;
            background-color: #f5f5f5;
            color: #333;
        }

        h1 {
            text-align: center;
        }

        form {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        label, input {
            margin: 10px;
        }

        button {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 16px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }

        h2 {
            text-align: center;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Calculate Lamp Filament Power</h1>
    <form id="powerForm">
        <label for="intensity">Intensity (I in Amperes):</label>
        <input type="number" id="intensity" name="intensity" step="0.01" required>
        <br>
        <label for="resistance">Resistance (R in Ohms):</label>
        <input type="number" id="resistance" name="resistance" step="0.01" required>
        <br>
        <button type="button" onclick="calculatePower()">Calculate Power</button>
    </form>
    <h2 id="result"></h2>
    <script>
        function calculatePower() {
            const intensity = parseFloat(document.getElementById('intensity').value);
            const resistance = parseFloat(document.getElementById('resistance').value);

            if (isNaN(intensity) || isNaN(resistance)) {
                alert('Please enter valid numbers for both intensity and resistance.');
                return;
            }

            const power = Math.pow(intensity, 2) * resistance;
            document.getElementById('result').innerText = `Power (P) = ${power.toFixed(2)} watts`;
        }
    </script>
</body>
</html>
```
# SERVER SIDE PROCESSING:
![Screenshot 2024-12-05 211907](https://github.com/user-attachments/assets/63c6a226-ff91-422e-aee9-bf91d4915a66)

# HOMEPAGE:
![Screenshot 2024-12-05 211925](https://github.com/user-attachments/assets/c54263a9-67b5-4c78-a788-cb9827162df9)

# RESULT:
The program for performing server side processing is completed successfully.
