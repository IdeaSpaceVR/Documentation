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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
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
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Textfield array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#rows</td><td>Between 1 and 20</td><td>Number</td><td>yes</td>
</tr>
<tr>
  <td>#maxlength</td><td>Between 1 and 524288</td><td>Integer</td><td>yes</td>
</tr>
<tr>
  <td>#contentformat</td><td>'html/text' or 'text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Textarea array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['jpg', 'png']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Image array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['jpg', 'png']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Photosphere array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['mp3', 'wav']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Audio array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['mp4']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Video array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['mp4']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Videosphere array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Color array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Date array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#options</td><td>['red' => 'Red', 'green' => 'Green', 'blue' => 'Blue']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Options Select array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
</tr>
<tr>
  <td>#required</td><td>true or false</td><td>Boolean</td><td>yes</td>
</tr>
<tr>
  <td>#file-extension</td><td>['obj', 'ply', 'dae']</td><td>Array</td><td>yes</td>
</tr>
<tr>
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

3D Model array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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
  <td>#description</td><td>'Write some text'</td><td>String</td><td>yes</td>
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
  <td>#help</td><td>'Write some text'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

`#content-type-reference` specifies WHAT should be positioned and attached in space. The content type you specify must exist in your theme (in `config.php` file). Examples for content types are: text-notes, blog-posts, images, videos, etc.

`#field-reference` specifies WHERE content items should be positioned and attached. The field name must exist in your theme (in `config.php` file) and within the same content type as the `position` field is in use. Examples for field references are: photo-sphere, video-sphere, 3d-model, etc. `#field-reference` is optional. If it is not specified, a grid is shown instead. 


Position array keys for getting content in a View Template (for example: `scene.blade.php`):
 
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



