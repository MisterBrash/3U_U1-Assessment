###### ICS3 - Mr. Brash 🐿️

### A little update on file paths

While discussing how to add images to our pages and link to other pages on our sites, you were told to use the slash "/" at the beginning of your filename:

```HTML
<img src="/images/pic.jpg">
```

*Normally* this would be correct, *if* we owned our own domain on the Internet. ***But***, we are using *GitHub* to host our websites, which includes a folder name for the repository, ruining our "root folder".

Instead of:
>https://&lt;username&gt;.github.io/<site name>

your site is actually:
>https://&lt;username&gt;.github.io/&lt;repo name&gt;/&lt;site name&gt;


There are two ways to fix this:
1. ❌ Include the repo folder name: `<img src="/1-8-my-repo-name/images/pic.jpg">` (but then the preview tool in VSCode won't work)
2. ✔️ Utilize *relative file paths* with `./` for "current folder" and `../` for "one folder back". This takes a bit of practice.

Let's look at a site like this:
```txt
<repo name>/index.html
           /html/biography.html
           /images/logo.png
```

Inside the `biography.html` page, we want to add the `logo.png`. The `biography.html` page is inside the `html` folder but the logo picture is inside the `images` folder. We need to **go back one folder** and *then* into the `images` folder:

```html
<img src="../images/logo.png">
```

There are some images and pages in this repo demonstrating this.

<hr>

# 1.8 - Style (Cascading Style Sheets)

There are 3 (three) ways to include *style* in your HTML.

### 1. Inline Style 🤮
##### (aka the *messy* wrong way)

We can add style to *one* tag, using the `style=""` attribute, separating style commands with a semicolon (`;`):
```HTML
<p id="intro" style="text-align:center;color:purple;font-size:1em;">
  Lipsem orem, blah blah blah.
</p>
```
<p id="intro" style="text-align:center;color:purple;font-size:1.5em;">
  Lipsem orem, blah blah blah.
</p>


### 2. Head Style 🙈
##### (aka the *clean* wrong way)

Inside the `<head>` of the document, we can use the `style` tag do *define* styles for our tags:

```HTML
<head>
  <title>1.8 - CSS</title>
  <style>

    body {
      font-size: 100%;
      margin: 10px;
    }

    p {
      text-align:center;
      color:purple;
      font-size:1.5em;
    }

  </style>

  <p id="intro">
    Lipsem orem, blah blah blah.
  </p>

</head>
```

### 3. Using a Separate .css file ✔ 👍

Inside a separate file, you can define your styles and then load the file into your HTML with [the `<link>` tag](https://www.w3schools.com/tags/tag_link.asp):

```HTML
<link rel="stylesheet" href="./css/main_style.css">
```

In the above example the `rel` attribute tells the browser the *relationship* between this document at the linked file.

The `.css` file will contain all the style definitions you would like for this particular them/page/usage. You can also create as many `.css` files as you like and load them on any `.html` document you like.

**Example .css file:**

```CSS
/* Elements */
body {
  font-size: 100%;
  margin: 10px;
}

p {
  text-align:center;
  color:purple;
  font-size:1.5em;
}

/* IDs */
#intro_paragraph {
  text-align: left;
  color: black;
  font-size:1em;
}

/* Classes */
.container {
  margin: 20px;
  background-color: grey;
}
```

### Learning style commands and options can take *weeks*. I highly recommend you [learn as you go](https://www.w3schools.com/css/).

<br>
<br>

🐿️
