# Temperature Conversion Program 

### HTML 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temperature Conversion</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    
    <form>
        <h1>Temperature Conversion:</h1>
        <input type="number" id="textBox" value="0"><br>

        <input type="radio" id="toFarenheit" name="unit">
        <label for="toFarenheit">Celsius ➡️ Farenheit</label><br>

        <input type="radio" id="toCelsius" name="unit">
        <label for="toCelsius">Faranheit ➡️ Celsius</label><br>

        <button type="button" onclick="convert()">submit</button>
        <p id="result"></p>
    </form>

    <script src="script.js"></script>
</body>
</html>
```

### CSS

```css
body {
    font-family: Arial, Helvetica, sans-serif;
    background-color: hsl(0, 0%, 85%);
}

h1{
    color: hsl(235, 56%, 39%);
}

form{
    background-color: hsl(0, 0%, 100%);
    text-align: center;
    max-width: 350px;
    margin: auto;
    padding: 25px;
    border-radius: 10px;
    box-shadow: 5px 5px 15px hsla(0, 0%, 0%, 0.3);
}

#textBox {
    width: 50%;
    text-align: center;
    font-size: 2em;
    border: 2px solid hsla(0, 0%, 0%, 0.8);
    border-radius: 4px;
    margin-bottom: 15px;
}

label {
    font-size: 1.5em;
    font-weight: bold;
}

button {
    margin-top: 15px;
    background-color: hsl(0, 100%, 60%);
    font-size: 1.5rem;
    border: none;
    padding: 10px 15px;
    border-radius: 5px;
    color: white;
    cursor: pointer;
}

button:hover{
    background-color: hsl(0, 100%, 50%);
}

#result {
    font-size: 1.75em;
    font-weight: bold;
}
```

### Javascript

```javascript
const textBox = document.getElementById("textBox");
const toFarenheit = document.getElementById("toFarenheit");
const toCelsius = document.getElementById("toCelsius");
const result = document.getElementById("result");
let temp; 


function convert(){

    if(toFarenheit.checked){
        temp = Number(textBox.value);
        temp = temp * 9 / 5 + 32;
        result.textContent = temp.toFixed(1) + " F";
    }
    else if(toCelsius.checked){
        temp = Number(textBox.value);
        temp = (temp - 32) * (5 / 9);
        result.textContent = temp.toFixed(1) + " C";
    }
    else{
        result.textContent = "Select a unit";
    }
}
```
