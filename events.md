# Events

- [General](#general)
- [Image Manipulation Operations](#image-manipulation-operations)

<a name="general"></a>
### General

The current IdeaSpaceVR release only allows very basic event handling for `image` and `photosphere` field types. This is very helpful if you have to generate low resolution images, for example: preview images. The following event listener is defined in `functions.php` in the IdeaSpace 360 theme directory and it specifies a `resize` operation. 

```
Event::listen('ideaspace-360-photo-sphere-viewer.photo-spheres.photo-sphere', function($image) {

    /* remember power of two rule for image sizes */
    return [
        'photo-sphere-navigation-preview-image' => [
            'resize' => ['width' => 512, 'height' => null],
        ]
    ];
});
```

The `Event::listen` function must know which field it should be listening on. Specify it as follows, separated by a `.`:

`theme key` -> `content type` -> `field key`.

If you create a new space, add a photo sphere image and save the space, the event listener is executed and a low resolution version of that image is generated (512 pixels wide, keeping the aspect ratio). In view templates you can access the preview image URI as follows:

```
@foreach ($content['photo-spheres'] as $photo) 
  {{ $photo['photo-sphere']['photo-sphere-navigation-preview-image']['#uri']['#value'] }}
@endforeach
``` 

<a name="image-manipulation-operations"></a>
### Image Manipulation Operations
Currently, the following event operations for image manipulation are implemented:

<table class="table table-bordered">
<thead>
<tr>
  <th>Operation</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>resize</td><td>Resize an image specified by width and/or height. Set null on width or height to keep the aspect ratio of an image.</td>
</tr>
<tr>
  <td>greyscale</td><td>Convert an image into grayscale colors.</td>
</tr>
<tr>
  <td>crop</td><td>You can specify width and height as well as x and y parameters. X and y are optional.</td>
</tr>
<tr>
  <td>fit</td><td>Combine cropping and resizing to format an image in a smart way. The method will find the best fitting aspect ratio of your given width and height on the current image automatically, cut it out and resize it to the given dimension.</td>
</tr>
</tbody>
</table>




