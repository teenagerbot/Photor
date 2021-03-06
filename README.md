# Photor
this photo library

# Today I present to you my new library
* Version [1.0](#1.0)
* Version [1.1](#1.1)
* Version [1.2](#1.3)
* Version [1.3](#1.4)
* Version [1.4](#1.5)(best version)

With it you can manage your photos, namely:
<a name="1.0"></a> 
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
  const p = new Photor();
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
  const p = new Photor();
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
  const p = new Photor();
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
  const p = new Photor();
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

index.js(old version):
```
"use stict";
const fs = require("fs");
//let data = "BLOB that you are transmitting through your transmission channel";
//for example:
let data = "data:image/png;base64,iVBOhRZ3xRG2cTWqS4nCkhgMyBUocVVqhV5hxV2x0cotYPRBtcSdXzAlbTUV...";
let buff = new Buffer(data, "base64");
fs.writeFileSync("hello.png", buff);
```
index.js(new version):
```
Buffer.from(data.replace('data:...; base64,', ''), 'base64');
```
<a name="1.1"></a> 
# NEW FUNCTIONS

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

<a name="1.3"></a>

# Release

Remember I wrote in version 1.0 that we can only change ONE pixel at a time.
So, now you can change MULTIPLE colors for pixels at ONE time:

```
const p = new Photor();
let image = document.querySelector("#k");
image.src = p.changePixels(image, "jpg", [255, 242, 0, 255, 0, 0], [63, 63, 63, 255, 0, 0], [165, 63, 79, 255, 0, 0]);
```

# Explanation

[255, 242, 0, 255, 0, 0], [63, 63, 63, 255, 0, 0], [165, 63, 79, 255, 0, 0] - this is an array in which you can change the colors of the pixels
in this case, we change the color three times for different pixels (because we have three arrays)
for example: [255, 242, 0, 255, 0, 0]:
All the pixels that we are looking for with the color rgb (255, 242, 0), we change to the color rgb (255, 0, 0), that is, red

Original:
![This is an image](https://googleapis.volodya-bot-developer.repl.co/??????.png)
The colors of those areas that I showed with arrows, we will change to red

Result:
![This is an image](https://googleapis.volodya-bot-developer.repl.co/??????.png)

<a name="1.4"></a>

# Yahooo, 

Now it is possible to upload your generated photo and add to the site not so scary links like this one:
data\:image/png;...

now there is a new method for uploading photos, !!!attention:
all photos that you will process with the following method will be available on my server (all photos will be sent there in order to shorten the link to the image for you)

So the method itself:

```.downloadImage(source, "you_name_for_image");```

Example:

```
const p = new Photor();
let image = document.querySelector("#k");
let y = p.removeWhite(image, "gif");
let u = p.downloadImage(y, "aba.gif");
setTimeout(() => {
	image.src = u;
}, 2000);
```

y - the creepy link data\:image/png;...
aba.gif - new link

in order to insert a new link into the <img> tag, be sure to delay it, otherwise you will not see the result

delay:

```
setTimeout(() => {
	image.src = u;
}, 2000);
```

<a name="1.5"></a>
#  Version 1.4

There were many functions in the old versions of the library, but the problem was that when removing a white or black ... background, the program searched for all pixels with shades of white, black ..., and as a result, the picture after the operation was not always good, but today I will introduce you new functions that remove PURE white, black, red, blue and green colors.

```
const p = new Photor();
let image = document.querySelector("#k");
let y = p.removePureWhite(image, "png");
let u = p.downloadImage(y, "aba.png");
setTimeout(() => {
	image.src = u;
}, 2000);
```
Functions: 
- .removePureWhite()
- .removePureBlack()
- .removePureRed()
- .removePureGreen()
- .removePureBlue()

Now compare the result obtained with the old white background removal function and the new one:

Original:

<img src="https://user-images.githubusercontent.com/91476715/171877769-67da4079-3fbd-4b2c-b264-c4af020e227b.png" width="200px">

Old:

<img src="https://user-images.githubusercontent.com/91476715/171877258-20f9184e-3303-47b3-9aa3-38f156250f0d.png" width="200px">

New:

<img src="https://user-images.githubusercontent.com/91476715/171877443-beed95b2-2e69-4d71-a291-a2dc12a946f4.png" width="200px">
