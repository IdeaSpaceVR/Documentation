## Field Types

Use this reference for setting up your content type(s) and fields in your theme's `config.php` file. Additionally it shows how to access field content in view templates by accessing  the `$content` theme variable.

- [Textfield](#textfield)
- [Textarea](#textarea)
- [Image](#image)
- [Photosphere](#photosphere)
- [Audio](#audio)
- [Video](#video)
- [Videosphere](#videosphere)
- [Color](#color)
- [Date](#date)
- [Options Select](#options-select)
- [3D Model](#3dmodel)
- [Position](#position)
- [Rotation](#rotation)
- [Space Reference](#space-reference)
- [Painter](#painter)




<a name="textfield"></a>
### Textfield

Renders as a HTML text input field. If the `#contentformat` is `html/text`, selected text can be formatted. Possible textfield settings for `config.php`: 

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'textfield'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#maxlength</td><td>Between 1 and 524288</td><td>Integer</td><td>yes</td>
</tr>
<tr>
  <td>#contentformat</td><td>'html/text' or 'text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-textfield' => [
              '#label' => 'My Textfield',
              '#description' => 'Enter some text.',
              '#help' => 'Enter some text.',
              '#type' => 'textfield',
              '#maxlength' => 200,
              '#contentformat' => 'text',
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Textfield array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'textfield'</td>
</tr>
<tr>
  <td>#value</td><td>Text</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['textfield-key']['#value']` 




<a name="textarea"></a>
### Textarea

Renders as a HTML text area. If the `#contentformat` is `html/text`, selected text can be formatted. Possible textarea settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'textarea'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#rows</td><td>Between 1 and 20</td><td>Integer</td><td>yes</td>
</tr>
<tr>
  <td>#maxlength</td><td>Between 1 and 524288</td><td>Integer</td><td>yes</td>
</tr>
<tr>
  <td>#contentformat</td><td>'html/text' or 'text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-textarea' => [
              '#label' => 'My Textarea',
              '#description' => 'Enter some text.',
              '#help' => 'Enter some text.',
              '#type' => 'textarea',
              '#maxlength' => 20000,
              '#rows' => 10,
              '#contentformat' => 'html/text',
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Textarea array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'textarea'</td>
</tr>
<tr>
  <td>#value</td><td>Text</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['textarea-key']['#value']` 




<a name="image"></a>
### Image

Renders as an image upload button. It opens the Assets dialog window in order to upload an image file or insert an existing image file into the space. Possible image settings for `config.php`: 

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'image'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['jpg', 'png']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#content-preview-image</td><td>true or false. Rendered as thumbnail image in content overview lists.</td><td>Boolean</td><td>no</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-image' => [
              '#label' => 'My Image',
              '#description' => 'Choose an image.',
              '#help' => 'Choose an image.',
              '#type' => 'image',
              '#file-extension' => ['jpg', 'png'],
              '#content-preview-image' => true,
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Image array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'image'</td>
</tr>
<tr>
  <td>#caption</td><td>Caption Text</td>
</tr>
<tr>
  <td>#description</td><td>Description Text</td>
</tr>
<tr>
  <td>#width</td><td>Width Number</td>
</tr>
<tr>
  <td>#height</td><td>Height Number</td>
</tr>
<tr>
  <td>#uri #value</td><td>Image URI including protocol and domain name</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['image-key']['#uri']['#value']` 




<a name="photosphere"></a>
### Photosphere

Renders as an photo sphere upload button. It opens the Assets dialog window in order to upload an image (photo sphere) file or insert an existing image (photo sphere) file into the space. Possible photosphere settings for `config.php`: 

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'photosphere'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['jpg', 'png']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#content-preview-image</td><td>true or false. Rendered as thumbnail image in content overview lists.</td><td>Boolean</td><td>no</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-photosphere' => [
              '#label' => 'My Photosphere',
              '#description' => 'Choose an 360 image.',
              '#help' => 'Choose a 360 image.',
              '#type' => 'photosphere',
              '#file-extension' => ['jpg', 'png'],
              '#content-preview-image' => true,
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Photosphere array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'photosphere'</td>
</tr>
<tr>
  <td>#caption</td><td>Caption Text</td>
</tr>
<tr>
  <td>#description</td><td>Description Text</td>
</tr>
<tr>
  <td>#width</td><td>Width Number</td>
</tr>
<tr>
  <td>#height</td><td>Height Number</td>
</tr>
<tr>
  <td>#uri #value</td><td>Photosphere URI including protocol and domain name</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['photosphere-key']['#uri']['#value']` 




<a name="audio"></a>
### Audio

Renders as an audio file upload button. It opens the Assets dialog window in order to upload an audio file or insert an existing audio file into the space. Possible audio settings for `config.php`: 

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'audio'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['mp3', 'wav']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-audio' => [
              '#label' => 'My Audio',
              '#description' => 'Choose an audio file.',
              '#help' => 'Choose an audio file.',
              '#type' => 'audio',
              '#file-extension' => ['mp3', 'wav'],
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Audio array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'audio'</td>
</tr>
<tr>
  <td>#caption</td><td>Caption Text</td>
</tr>
<tr>
  <td>#description</td><td>Description Text</td>
</tr>
<tr>
  <td>#duration</td><td>Duration in seconds</td>
</tr>
<tr>
  <td>#uri #value</td><td>Audio URI including protocol and domain name</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['audio-key']['#uri']['#value']` 




<a name="video"></a>
### Video

Renders as a video file upload button. It opens the Assets dialog window in order to upload an video file or insert an existing video file into the space. Possible video settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'video'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['mp4']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-video' => [
              '#label' => 'My Video',
              '#description' => 'Choose a video file.',
              '#help' => 'Choose a video file.',
              '#type' => 'video',
              '#file-extension' => ['mp4'],
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Video array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'video'</td>
</tr>
<tr>
  <td>#caption</td><td>Caption Text</td>
</tr>
<tr>
  <td>#description</td><td>Description Text</td>
</tr>
<tr>
  <td>#width</td><td>Width Number</td>
</tr>
<tr>
  <td>#height</td><td>Height Number</td>
</tr>
<tr>
  <td>#duration</td><td>Duration in seconds</td>
</tr>
<tr>
  <td>#uri #value</td><td>Video URI including protocol and domain name</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['video-key']['#uri']['#value']` 




<a name="videosphere"></a>
### Videosphere

Renders as a video sphere file upload button. It opens the Assets dialog window in order to upload an video sphere file or insert an existing video sphere file into the space. Possible videosphere settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'videosphere'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['mp4']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-videosphere' => [
              '#label' => 'My Videosphere',
              '#description' => 'Choose a 360 video file.',
              '#help' => 'Choose a 360 video file.',
              '#type' => 'videosphere',
              '#file-extension' => ['mp4'],
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Videosphere array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'videosphere'</td>
</tr>
<tr>
  <td>#caption</td><td>Caption Text</td>
</tr>
<tr>
  <td>#description</td><td>Description Text</td>
</tr>
<tr>
  <td>#width</td><td>Width Number</td>
</tr>
<tr>
  <td>#height</td><td>Height Number</td>
</tr>
<tr>
  <td>#duration</td><td>Duration in seconds</td>
</tr>
<tr>
  <td>#uri #value</td><td>Videosphere URI including protocol and domain name</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['videosphere-key']['#uri']['#value']` 




<a name="color"></a>
### Color

Renders as an HTML color selector input field. Possible color settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'color'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#default_value</td><td>'#FF0000'. Color value.</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-color' => [
              '#label' => 'My Color',
              '#description' => 'Choose a color.',
              '#help' => 'Choose a color.',
              '#type' => 'color',
              '#default_value' => '#FFFFFF',
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Color array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'color'</td>
</tr>
<tr>
  <td>#value</td><td>Color value (hexadecimal)</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['color-key']['#value']` 




<a name="date"></a>
### Date

Renders as an HTML date selector input field. Possible date settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'date'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-date' => [
              '#label' => 'My Date',
              '#description' => 'Choose a date.',
              '#help' => 'Choose a date.',
              '#type' => 'date',
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Date array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'date'</td>
</tr>
<tr>
  <td>#value</td><td>Date value</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['date-key']['#value']` 




<a name="options-select"></a>
### Options Select

Renders as an HTML select input field. Possible options select settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'options-select'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#options</td><td>['red' => 'Red', 'green' => 'Green', 'blue' => 'Blue']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#default_value</td><td>'green'. Key value from #options.</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-options' => [
              '#label' => 'My Options',
              '#description' => 'Choose an option.',
              '#help' => 'Choose a option.',
              '#type' => 'options-select',
              '#options' => ['red' => 'Red Bike', 'green' => 'Green Bike', 'blue' => 'Blue Bike'],
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Options Select array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'options-select'</td>
</tr>
<tr>
  <td>#value</td><td>Selected option</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['options-select-key']['#value']` 




<a name="3dmodel"></a>
### 3D Model

Renders as a 3D model upload button. It opens the Assets dialog window in order to upload a 3D model file (or multiple files: the obj model format consists of obj, mtl and image texture files) or insert an existing 3D model into the space. Possible 3D model settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'model3d'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'. Rendered as placeholder.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['glb', 'gltf', 'obj', 'ply', 'dae']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-model' => [
              '#label' => 'My Model',
              '#description' => 'Upload a model.',
              '#help' => 'Upload a model.',
              '#type' => 'model3d',
							'#file-extension' => ['obj', 'ply', 'dae', 'glb', 'gltf'],
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

3D Model array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'model3d'</td>
</tr>
<tr>
  <td>#caption</td><td>Caption Text</td>
</tr>
<tr>
  <td>#description</td><td>Description Text</td>
</tr>
<tr>
  <td>#scale</td><td>Key value pairs. For example: ['#x' => 1, '#y' => 1, '#z' => 1]</td>
</tr>
<tr>
  <td>#rotation</td><td>Key value pairs. In degrees. For example: ['#x' => 90.0, '#y' => 45.0, '#z' => 0.0]</td>
</tr>
<tr>
  <td>#model</td><td>Array containing #uri #value and #uri #filetype keys and values. An *.obj file contains an additional entry for the *.mtl file.</td>
</tr>
</tbody>
</table>

Example:
 
`$content['content-type-key'][0]['model-key']['#model'][0]['#uri']['#value']` 

`$content['content-type-key'][0]['model-key']['#model'][0]['#uri']['#filetype']` 

Example for `obj` and `mtl` files:

`$content['content-type-key'][0]['model-key']['#model'][0]['#uri']['#value']`

`$content['content-type-key'][0]['model-key']['#model'][1]['#uri']['#value']`

`$content['content-type-key'][0]['model-key']['#model'][0]['#uri']['#filetype']`

`$content['content-type-key'][0]['model-key']['#model'][1]['#uri']['#filetype']`



<a name="position"></a>
### Position 

Renders as a button. It opens a dialog window in order to position, attach and detach content items (of a certain content type). The content positions and content item references can be inserted into a space. Possible position settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'position'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#maxnumber</td><td>Between 1 and infinite</td><td>Integer</td><td>yes</td>
</tr>
<tr>
  <td>#content-type-reference</td><td>'name-of-content-type'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#field-reference</td><td>'name-of-field'</td><td>String</td><td>no</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

`#content-type-reference` specifies WHAT should be positioned and attached in space. The content type you specify must exist in your theme (in `config.php` file). Examples for content types are: text-notes, blog-posts, images, videos, etc.

`#field-reference` specifies WHERE content items should be positioned and attached. The field name must exist in your theme (in `config.php` file) and within the same content type as the `position` field is in use. Examples for field references are: photo-sphere, video-sphere, 3d-model, etc. `#field-reference` is optional. If it is not specified, a grid is shown instead. 

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-position' => [
              '#label' => 'My Position',
              '#description' => 'Position the model.',
              '#help' => 'Position the model.',
              '#type' => 'position',
              '#maxnumber' => 'infinite',
              '#required' => true,
              '#content-type-reference' => 'model3d',
              '#field-reference' => 'my-model',
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```


Position array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'position'</td>
</tr>
<tr>
  <td>#caption</td><td>Caption Text</td>
</tr>
<tr>
  <td>#description</td><td>Description Text</td>
</tr>
<tr>
  <td>#positions</td><td>Array entries for positioned content items with key value pairs for #position (#x, #y, #z), #scale (#x, #y, #z), #rotation (#x, #y, #z), #content-id and referenced #content with its corresponding values.</td>
</tr>
</tbody>
</table>

Example:

`$content['content-type-key'][0]['position-key']['#positions'][0]['#position']['#x']`

`$content['content-type-key'][0]['position-key']['#positions'][0]['#position']['#y']`

`$content['content-type-key'][0]['position-key']['#positions'][0]['#position']['#z']`

`$content['content-type-key'][0]['position-key']['#positions'][0]['#content-id']`

`$content['content-type-key'][0]['position-key']['#positions'][..]['#position']['#x']`

Example: a reference to an image has been positioned:

`$content['content-type-key'][0]['position-key']['#positions'][0]['#content']['image-key']['#width']`

`$content['content-type-key'][0]['position-key']['#positions'][0]['#content']['image-key']['#height']`

`$content['content-type-key'][0]['position-key']['#positions'][0]['#content']['image-key']['#caption']`

`$content['content-type-key'][0]['position-key']['#positions'][0]['#content']['image-key']['#description']`

`$content['content-type-key'][0]['position-key']['#positions'][0]['#content']['image-key']['#uri']['#value']`



<a name="rotation"></a>
### Rotation 

Renders as a button. It opens a dialog window in order to rotate content items (of a certain content type). The content rotation can be inserted into a space. Possible rotation settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'rotation'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#field-reference</td><td>'name-of-field'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

`#field-reference` specifies the field name on which to enable the setting of a rotation. The field name must exist in your theme (in `config.php` file) and within the same content type as the `rotation` field is in use. Supported field types are: `video`, `videosphere`, `photosphere`, `image`, `model3d`.

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-rotation' => [
              '#label' => 'My Rotation',
              '#description' => 'Rotate the model.',
              '#help' => 'Rotate the model.',
              '#type' => 'rotation',
              '#maxnumber' => 'infinite',
              '#required' => true,
              '#field-reference' => 'my-model',
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```


Rotation array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'rotation'</td>
</tr>
<tr>
  <td>#rotation</td><td>Array entries with key value pairs for rotation (#x, #y, #z).</td>
</tr>
</tbody>
</table>

Example:

`$content['content-type-key'][0]['rotation-key']['#rotation']['#x']`

`$content['content-type-key'][0]['rotation-key']['#rotation']['#y']`

`$content['content-type-key'][0]['rotation-key']['#rotation']['#z']`


<a name="space-reference"></a>
### Space Reference

Renders as an HTML select input field. Possible space reference settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'space-reference'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#published</td><td>true or false. List only published spaces or all spaces.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'my-space-ref' => [
              '#label' => 'My Space Reference',
              '#description' => 'Select a space.',
              '#help' => 'Select a space.',
              '#type' => 'space-reference',
              '#required' => true,
              '#published' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

Space Reference array keys for accessing content in a View Template (for example: `scene.blade.php`):
 
<table class="table table-bordered">
<thead>
<tr>
  <th>Array Key</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#id</td><td>Field ID Number</td>
</tr>
<tr>
  <td>#content-id</td><td>Content ID Number</td>
</tr>
<tr>
  <td>#type</td><td>'space-reference'</td>
</tr>
<tr>
  <td>#space-title</td><td>The space title</td>
</tr>
<tr>
  <td>#space-uri</td><td>The space URI</td>
</tr>
<tr>
  <td>#space-id</td><td>The space id</td>
</tr>
</tbody>
</table>

Example:

`$content['content-type-key'][0]['space-reference-key']['#space-title']`


<a name="painter"></a>
### Painter 

Renders as a button which opens a dialog window containing a VR scene from this theme. When entering in VR mode, you have access to a tool to paint in this scene. Possible painter reference settings for `config.php`:

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#type</td><td>'painter'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#label</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'. Rendered as help text.</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#scene-template</td><td>Name of a view template which should embed the painter tool. Eg. 'scene-painter' - a scene without camera and laser-controls.</td><td>String</td><td>yes</td>
</tr>
</tbody>
</table>

Example `config.php`:

```
    return [

      '#theme-name' => 'Example Theme',
      '#theme-key' => 'example-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.2.0',
      '#theme-description' => 'Example.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'example, simple',
      '#theme-view' => 'scene',

      '#content-types' => [

        'my-content-type' => [
          '#label' => 'My Content Type',
          '#description' => 'Some description text.',
          '#max-values' => 'infinite',
          '#fields' => [

            'post-painter' => [
              '#label' => 'Paint on post',
              '#description' => 'Create a painting in your blog post',
              '#help' => 'VR controllers with 6-DOF (degrees of freedom) are needed',
              '#type' => 'painter',
              '#scene-template' => 'scene-painter', /* scene without camera and laser-controls */
              '#required' => false,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];
```

When creating the scene-template for painter, you have to include two statements in the template:

- inside the `<a-assets>` tags you have to include `@php painter_assets(); @endphp`

- after `<a-assets>` tags include this statement: @php painter_entities(); @endphp

These statements are necessary to make painter work in your template.


