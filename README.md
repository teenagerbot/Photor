# Photor
this photo library

# Today I present to you my new library
[Текст ссылки](#NEW FUNCTIONS)
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

# Explanation

* removeBlack(image, "png"):
* 	image - your photo tag (you don't need to specify a URL, just a tag, id or class);
* 	"png" - image extension(file type) which will then turn out;
* changePixels(image, 41, 169, 235, 158, 49, 216, "png"):
* 	image - your photo tag (you don't need to specify a URL, just a tag, id or class);
* 	41 - R;
* 	169 - G;
* 	235 - B;
* 	the top RGB palette for a specific color will be replaced with the next one:
* 	158 - R;
* 	49 - G;
* 	216 - B;
* 	that, blue will be replaced by violets

# Attention:

this method allows you to change the color of ONE pixel and only ONE time

# Using in PHP

if you want to upload the generated photo to the server via PHP, then you must write the following in the PHP file:

index.php:
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
    <form method="post" action="server.php" enctype="multipart/form-data">
      <input type="url" id="url" name="new_url"><br>
      <input type="text" id="name" name="new_name"><br>
      <input type="submit">
    </form>
    <script src="https://googleapis.volodya-bot-developer.repl.co/libs/photor.min.js"></script>
    <script src="script.js"></script>
  </body>

  </html>
```
script.js:
```
  const p = new RemoveBG();
  let image = document.querySelector("#k");
  image.src = p.removeWhite(image, "png");
  document.querySelector("#url").value = image.src;
  ```
server.php:
```
if (!empty($_POST["new_url"]) && !empty($_POST["new_name"])) {
    $enc = explode(",", $_POST["new_url"]);
    $enc = str_replace(" ", "+", $enc[1]);
    $ens = base64_decode($enc);
    $new_file = __DIR__."/".$_POST["new_name"].".png(or .jpg, .gif...)";
    file_put_contents($new_file, $ens);
}
```

# Using in NODE.js

if you want to upload the generated photo to the server via NODE.js, then you must write the following in the NODE.js file:

index.js:
```
"use stict";
const fs = require("fs");
//let data = "BLOB that you are transmitting through your transmission channel";
//for example:
let data = "data:image/png;base64,iVBOhRZ3xRG2cTWqS4nCkhgMyBUocVVqhV5hxV2x0cotYPRBtcSdXzAlbTUV...";
let buff = new Buffer(data, "base64");
fs.writeFileSync("hello.png", buff);
```

<a name="NEW FUNCTIONS"></a>

# Now this library has 5 more functions. Namely:
* red color removal
* removal of yellow
* blue color removal
* purple removal
* gray color removal
# to remove the red:
```
.removeRed(image, "png");
```

# to remove the yellow:
```
.removeYellow(image, "png");
```

# to remove the blue:
```
.removeBlue(image, "png");
```

# to remove the violet:
```
.removeViolet(image, "png");
```

# to remove the gray:
```
.removeGray(image, "png");
```
