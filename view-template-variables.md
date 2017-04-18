# View Template Variables

- [View Templates](#view-templates)
- [JavaScript and JSON](#javascript-json)

<a name="view-templates"></a>
### View Templates

The following variables are exposed in the view templates (`index.blade.php`, `assets.blade.php`, `scene.blade.php`).

<table class="table table-bordered">
<thead>
<tr>
<th>Variable</th><td>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>$space_url</td><td>The URL used for this space.</td>
</tr>
<tr>
  <td>$space_title</td><td>The title of this space.</td>
</tr>
<tr>
  <td>$origin_trial_token</td><td>Origin Trial Token for enabling WebVR in Chrome browsers.</td>
</tr>
<tr>
  <td>$theme_dir</td><td>The directory path of the active theme for this space.</td>
</tr>
<tr>
  <td>$theme_view</td><td>The name of the theme view. Default value is: scene.</td>
</tr>
<tr>
  <td>$content</td><td>Content variable containing all content type and field related data entered by the user. A detailed description of field type $content array structures <a href="content-types-and-field-types">can be found here</a>.</td>
</tbody>
</table>

Example: `$content` variable structure for field type `textfield`: 

```
@foreach ($content['your-content-type-key'] as $textfield)

  {{ $textfield['your-textfield-key']['#id'] }}
  {{ $textfield['your-textfield-key']['#content-id'] }}
  {{ $textfield['your-textfield-key']['#type'] }}
  {{ $textfield['your-textfield-key']['#value'] }}

@endforeach
```

Example: `$content` variable structure for field type `photosphere`:

```
@foreach ($content['your-content-type-key'] as $photosphere)

  {{ $photosphere['your-photosphere-key']['#id'] }}
  {{ $photosphere['your-photosphere-key']['#content-id'] }}
  {{ $photosphere['your-photosphere-key']['#type'] }}
  {{ $photosphere['your-photosphere-key']['#caption'] }}
  {{ $photosphere['your-photosphere-key']['#description'] }}
  {{ $photosphere['your-photosphere-key']['#width'] }}
  {{ $photosphere['your-photosphere-key']['#height'] }}
  {{ $photosphere['your-photosphere-key']['#uri']['#value'] }}

@endforach
```

Example: `$content` variable structure for field type `position`:

```
@foreach ($content['your-content-type-key'] as $position)

  {{ $position['your-position-key']['#id'] }}
  {{ $position['your-position-key']['#content-id'] }}
  {{ $position['your-position-key']['#type'] }}

  @foreach ($position['your-position-key']['#positions'] as $position_item)

    {{ $position_item['#scale']['#x'] }}
    {{ $position_item['#scale']['#y'] }}
    {{ $position_item['#scale']['#z'] }}
    {{ $position_item['#rotation']['#x'] }}
    {{ $position_item['#rotation']['#y'] }}
    {{ $position_item['#rotation']['#z'] }}
    {{ $position_item['#position']['#x'] }}
    {{ $position_item['#position']['#y'] }}
    {{ $position_item['#position']['#z'] }}
    {{ $position_item['#position']['#content-id'] }}

  @endforeach

@endforeach
```


<a name="javascript-json"></a>
### JavaScript and JSON 

The view template variables are exposed via JavaScript and JSON as well. Example: you want to load assets in an A-Frame component.

```
<a-entity
  load-assets="url:{{ $space_url }}/content/your-content-type-key?per-page=3&page=1"
</a-entity>
```

`load-assets` is an A-Frame component with `url` as a parameter which returns a JSON structure. IdeaSpaceVR uses pagination in order to return chuncks of content. `per-page` parameter defines how many items should be returned 'per page'. `page` parameter defines at which page number we want to start the pagination.

In the `load-assets` component you can iterate through the JSON result. The JavaScript structure is the same structure as exposed in the view templates.

```
init: function() {

  this.xmlhttp = new XMLHttpRequest();
  this.xmlhttp.onreadystatechange = this.responseHandler.bind(this);

  /* this.data.url contains the URL as shown in the example above */
  this.xmlhttp.open('GET', this.data.url, true);

  this.xmlhttp.send();

},

responseHandler: function() {

  var obj = JSON.parse(this.xmlhttp.responseText);

  for (var i=0; i<obj['your-content-type-key'].length; i++) {

    var img = new Image();
    img.src = obj['your-content-type-key'][i]['your-photosphere-key']['#uri']['#value'];

  }

}
```







