# Avatar Upload

by [Dan Harper](http://danharper.me)

## Usage

### 1. Include Files
Include the `avatar.js` and `avatar.css` files in your document.

### 2. Wrap a Replacable Image
Insert the current image (or a placeholder) in the page, inside a div with a custom class (eg. `avatar-upload`):

```html
<div class="avatar-upload">
    <img src="placekitten.jpg">
</div>
```

### 3. Set your max images widths
You must set a max width, otherwise images will fill the container. eg.

```css
.avatar-upload {
    width: 200px;
    height: 200px;
}

.avatar-upload img {
    max-width: 200px;
    max-height: 200px;
}
```

### 4. Boot the module
Now boot the module, providing it with the element containing the image to replace & the URL to upload to.

```js
new AvatarUpload({
    el: document.querySelector('.avatar-upload'),
    uploadUrl: ''
});
```

This will swap the contents of your `.avatar-upload` element with the uploader's markup. The image currently set won't appear any different. But you can now click the image to swap it out!

You can optionally provide the following configuration settings to the module:

* `el` **[required]** The element containing the current replaceable image
* `uploadUrl` **[required]** Where to sent the new image to
* `uploadMethod` The HTTP method to use when uploading (defaults to `POST`)
* `uploadData` An object of additional data to send with the upload
* `onProgress` A function to be called continuously as the upload progresses - takes one argument, the current upload percentage completion
* `onSuccess` A function to be called when the upload completes successfully - takes one argument, the response from the server
* `onError` A function to be called when the upload fails - takes one argument, the error response from the server
* `pretentUpload` If `true`, no upload will be performed, it will be faked through a `setInterval`, pretending to upload - useful for testing initial set up

## Credit

Kitten image in demo courtesy of [Paul Reynolds](http://www.flickr.com/photos/bigtallguy/148771151/) via [placekitten](http://placekitten.com/)
