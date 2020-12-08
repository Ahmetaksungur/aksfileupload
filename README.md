# aksFileUpload.js
File upload tool

![aksFileUpload.js-ahmet-aksungur](https://github.com/Ahmetaksungur/aksfileupload/blob/main/aksfileuplaod.gif?raw=true)

**[View the Demo on CodePen &rarr;](https://codepen.io/collection/APgoJG)**

## Getting Started

Compiled and production-ready code can be found in the `dist` directory.

### 1. Include aksFileUpload.min.js on your site.

**Direct Download**

You can [download the files directly from GitHub](https://github.com/Ahmetaksungur/aksfileupload/archive/main.zip).

```html
<link type="text/css" rel="stylesheet" href="dist/aksFileUpload.min.css">
```

```html
<script src="dist/aksFileUpload.min.js"></script>
```

**CDN**

```html
<link type="text/css" rel="stylesheet" href="https://unpkg.com/aksfileupload@1.0.0/dist/aksFileUpload.min.css">
```

```html
<script src="https://unpkg.com/aksfileupload@1.0.0/dist/aksFileUpload.min.js"></script>
```
---

```html
<link type="text/css" rel="stylesheet" href="https://cdn.jsdelivr.net/npm/aksfileupload@1.0.0/dist/aksFileUpload.min.css">
```

```html
<script src="https://cdn.jsdelivr.net/npm/aksfileupload@1.0.0/dist/aksFileUpload.min.js"></script>
```

**jQuery**

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
```
---

**NPM**

```bash
npm i aksfileupload
```


## Document aksFileUpload.js

```html
<div id="aks-file-upload"></div>
<p id="uploadfile" type="json"></p>
```

```js
$(function () {
  $("#aks-file-upload").aksFileUpload({
    fileUpload: "#uploadfile", // With target [input]file or [type]json you can save the data of loaded items
    fileType: ["pdf", "docx", "rtf", "jpg", "jpeg", "png"], // allowed file formats
    dragDrop: true, // drag & drop upload
    maxSize: "90 GB", // maximum uploaded file size
    multiple: true, // multiple file upload
    maxFile: 50, // maximum number of uploaded files
    maxFileError: "File exceeds upload limit. - Max limit:", // error text
    maxSizeError: "File exceeds size. - Max limit:", // error text
    fileTypeError: "Disallowed file format.", // error text
    label: "Drag & Drop your files or Browse" // label text
  });
});
```

### Ajax Upload

```html
<div id="aks-file-upload"></div>
<p id="uploadfile" type="json"></p>
```

```js
$(function () {
  $("#aks-file-upload").aksFileUpload({
    fileUpload: "#uploadfile", // With target [input]file or [type]json you can save the data of loaded items
    fileType: ["pdf", "docx", "rtf", "jpg", "jpeg", "png"], // allowed file formats
    dragDrop: true, // drag & drop upload
    maxSize: "90 GB", // maximum uploaded file size
    multiple: true, // multiple file upload
    maxFile: 50, // maximum number of uploaded files
    // ajax file upload
    ajaxUpload: true, 
          ajax: {
            directlyLoad: false,  // direct loading file permit
            url: "upload.php",
            type: "POST",
            contentType: false, 
            processData: false,  
            cache: false,
            async: true,
            enctype: "multipart/form-data"
          },


  });
});
```
##### upload.php
```php
<?php

if(isset($_FILES['file']['name'])){

   /* Getting file name */
   $filename = $_FILES['file']['name'];

   /* Location */
   $location = "upload/".$filename;
   $imageFileType = pathinfo($location,PATHINFO_EXTENSION);
   $imageFileType = strtolower($imageFileType);

   $response = 0;
      /* Upload file */
      if(move_uploaded_file($_FILES['file']['tmp_name'],$location)){
         $response = $location;
      }
   echo $response;
   exit;
}

echo 0;
```




## License

The code is available under the [MIT License](https://github.com/Ahmetaksungur/aksfileupload/blob/master/LICENSE).
