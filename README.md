# Photor
this photo library

# Today I present to you my new library

With it you can manage your photos, namely:

* Removing the white background;
* Removing the black background;
* Change the pixel colors of your photo;

# How to USE?
1 Library connection:
```<script src="https://googleapis.volodya-bot-developer.repl.co/libs/photor.min.js"></script>```
2 Using the library:
  * First method - Removing the black background:
  HTML:
  ```
  <!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>replit</title>
  <link href="style.css" rel="stylesheet" type="text/css" />
</head>

<body>
	Result:
  <img id="k" src="s.jpg"><br>
  Original:
	<img src="s.jpg">
	<script src="https://googleapis.volodya-bot-developer.repl.co/libs/photor.min.js"></script>
  <script src="script.js"></script>
</body>

</html>
  ```
  JS(script.js):
  ```
  const p = new RemoveBG();
  let image = document.querySelector("#k");
  //Removing the black background
  image.src = p.removeBlack(image, "png");
  ```
  Result:
  ![This is an image](https://googleapis.volodya-bot-developer.repl.co/tres.png)
  ![This is an image](https://googleapis.volodya-bot-developer.repl.co/rest.png)
  * Second method - Removing the white background:
  HTML:
  ```
  <!DOCTYPE html>
  <html>

  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>replit</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
  </head>

  <body>
    Result:
    <img id="k" src="w.jpg"><br>
    Original:
    <img src="w.jpg">
    <script src="https://googleapis.volodya-bot-developer.repl.co/libs/photor.min.js"></script>
    <script src="script.js"></script>
  </body>

  </html>
  ```
  JS(script.js):
  ```
  const p = new RemoveBG();
  let image = document.querySelector("#k");
  //Removing the white background
  image.src = p.removeWhite(image, "png");
  ```
  Result:
  ![This is an image](https://googleapis.volodya-bot-developer.repl.co/rerest.png)
  * And method - change the pixel colors of your photo
  HTML:
  ```
  <!DOCTYPE html>
  <html>

  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>replit</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
  </head>

  <body>
    Result:
    <img id="k" src="tel.png"><br>
    Original:
    <img src="tel.png">
    <script src="https://googleapis.volodya-bot-developer.repl.co/libs/photor.min.js"></script>
    <script src="script.js"></script>
  </body>

  </html>
  ```
  JS(script.js):
  ```
  const p = new RemoveBG();
  let image = document.querySelector("#k");
  //change the pixel colors
  image.src = p.changePixels(image, 41, 169, 235, 158, 49, 216, "png");
  ```
  Result:
  ![This is an image](https://googleapis.volodya-bot-developer.repl.co/super.png)
