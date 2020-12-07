# aksFileUpload.min.js
File upload tool

**[View the Demo on CodePen &rarr;](https://codepen.io/ahmetaksungur/pen/oNxqNpx)**

## Getting Started

Compiled and production-ready code can be found in the `dist` directory.

### 1. Include aksFileUpload.min.js on your site.

**Direct Download**

You can [download the files directly from GitHub](https://github.com/Ahmetaksungur/aksfileupload/archive/master.zip).

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

**NPM**

```bash
npm i aksfileupload
```


### 2. Initialize aksFileUpload.min.js

```html
<aks-file-upload></aks-file-upload>
<p id="uploadfile" type="json"></p>
```

```js
$(function () {
  $("aks-file-upload").aksFileUpload({
    fileUpload: "#uploadfile",
    dragDrop: true,
    maxSize: "90 GB",
    multiple: true,
    maxFile: 50
  });
});
```

## License

The code is available under the [MIT License](https://github.com/Ahmetaksungur/aksfileupload/blob/master/LICENSE).
