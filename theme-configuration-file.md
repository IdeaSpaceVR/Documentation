# Theme Configuration File

The theme configuration file `config.php` is central to a theme. It contains content type and field definitions which define the "backend" part of a theme which stores content in the database. It consists of two parts: general information about a theme and content type and field configuration.
<br>
<br>

- [General information about the theme](#general-information-theme)
- [Content type and field configuration](#content-type-field-configuration)
- [Example: IdeaSpace 360 theme](#example-ideaspace-360-theme)
- [Internationalization (i18n)](#internationalization)


<a name="general-information-theme"></a>
### General information about the theme

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#theme-name</td><td>Name of the theme, for example 'IdeaSpace 360'.</td>
</tr>
<tr>
  <td>#theme-key</td><td>The theme key which is used - for example - in event listeners: 'ideaspace-360-photo-sphere-viewer'. It must not contain spaces or any special characters.</td>
</tr>
<tr>
  <td>#theme-version</td><td>Example: '1.0'.</td>
</tr>
<tr>
  <td>#ideaspace-version</td><td>The minimum required IdeaSpaceVR version to run this theme. Example: '>=1.0.0'.</td>
</tr>
<tr>
  <td>#theme-description</td><td>A descriptive text.</td>
</tr>
<tr>
  <td>#theme-author-name</td><td>The name of the author.</td>
</tr>
<tr>
  <td>#theme-author-email</td><td>The e-mail address of the author.</td>
</tr>
<tr>
  <td>#theme-homepage</td><td>The website URL of the theme.</td>
</tr>
<tr>
  <td>#theme-keywords</td><td>Keywords, comma separated. Example: 'photo sphere, gaze input navigation, mobile, 360, photography'.</td>
</tr>
<tr>
  <td>#theme-view</td><td>The main view template file. Example: 'scene' which translates to scene.blade.php.</td>
</tr>
</tbody>
</table>


<a name="content-type-field-configuration"></a>
### Content type and field configuration

  This part of the file defines which content the user can enter, upload or configure when a new space is created or edited.

  ![IdeaSpaceVR - Building Basic VR Theme](/assets/documentation/images/building-basic-vr-theme-1.png "IdeaSpaceVR - Building Basic VR Theme") {.img-responsive}

  The theme configuration file (`config.php`) can define one or many content types. And each content type can define one or many fields. Each field is described by a `#type` and other parameters. Take a look at <a href="field-type-reference">Field Type Reference</a> which lists all available fields and types.


<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#label</td><td>Label of the content type.</td>
</tr>
<tr>
  <td>#description</td><td>The description of the content type.</td>
</tr>
<tr>
  <td>#max-values</td><td>How many items of this content type can be created. Possible values are 'infinite' or a number.</td>
</tr>
<tr>
  <td>#fields</td><td>Fields configuration. See <a href="field-type-reference">Field Type Reference</a>.</td>
</tr>
</tbody>
</table>


<a name="example-ideaspace-360-theme"></a>
### Example: IdeaSpace 360 theme

```
return [

  '#theme-name' => 'IdeaSpace 360',
  '#theme-key' => 'ideaspace-360-photo-sphere-viewer',
  '#theme-version' => '1.0',
  '#ideaspace-version' => '>=1.0.0',
  '#theme-description' => 'Photo sphere viewer with navigation menu in VR. Attach text annotations to your photo spheres.',
  '#theme-author-name' => 'IdeaSpaceVR',
  '#theme-author-email' => 'info@ideaspacevr.org',
  '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
  '#theme-keywords' => 'photo sphere, gaze input navigation, mobile, 360, photography',
  '#theme-view' => 'scene',

  '#content-types' => [

    'text-notes' => [
      '#label' => 'Text Notes',
      '#description' => 'Manage your text notes which are attached to your photo spheres.',
      '#max-values' => 'infinite',
      '#fields' => [

        'note' => [
          '#label' => 'Text Note',
          '#description' => 'Enter some text.',
          '#help' => 'The text note can be attached to a photo sphere.',
          '#type' => 'textfield',
          '#maxlength' => 140,
          '#contentformat' => 'text',
          '#required' => true,
        ],

      ], /* fields */
    ], /* notes */

    'photo-spheres' => [
      '#label' => 'Photo Spheres',
      '#description' => 'Manage your photo spheres.',
      '#max-values' => 'infinite',
      '#fields' => [

        'title' => [
          '#label' => 'Photo Sphere Title',
          '#description' => 'Enter a title.',
          '#help' => 'Enter a title for this photo sphere (optional). The title is shown after the photo sphere has been loaded.',
          '#type' => 'textfield',
          '#maxlength' => 140,
          '#contentformat' => 'text',
          '#required' => false,
        ],

        'photo-sphere' => [
          '#label' => 'Photo Sphere',
          '#description' => 'Upload a photo sphere image.',
          '#help' => 'Photo sphere image in equirectangular projection format.',
          '#type' => 'photosphere',
          '#required' => true,
          '#file-extension' => ['jpg', 'png'],
        ],

        'attach-text-notes' => [
          '#label' => 'Info Notes',
          '#description' => 'Add some text notes to the photo sphere.',
          '#help' => 'Add some contextual information by attaching text notes to your photo sphere.',
          '#type' => 'position',
          '#maxnumber' => 10,
          '#required' => false,
          '#content-type-reference' => 'text-notes',
          '#field-reference' => 'photo-sphere',
        ],

      ], /* fields */

    ], /* photo-spheres */

  ], /* content types */

];
```

There are two content types defined: `text-notes` and `photo-spheres`. Text notes can be attached to photo spheres. The field `attach-text-notes` (part of content type `photo-spheres`) defines that items of the content type `text-notes` can be positioned and attached to photo spheres. 

Take a look at <a href="content-types-and-field-types">Content Types and Field Types</a> which lists all available fields and types.



<a name="internationalization"></a>
### Internationalization of a theme

Theme labels, description and help texts defined in the theme `config.php` file can be translated into other languages. In order to accomplish this we put all text in external language files inside the `lang` directory of the theme and we just use a unique key for each text in the `config.php` file. Each of these keys reference a text inside a language file. We have one language file per language, for example one for english, one for german or french.

If you switch the language for your IdeaSpaceVR installation (in Settings), the theme translations are shown according to the selected language when creating or editing a space.


#### `lang` directory structure 

```
lang/en/
lang/de/
lang/fr/
etc.
```

Each language has its own directory within the `lang` directory. And each language has its own language files, for example:

`lang/en/my_texts.php` or

`lang/de/my_texts.php`


#### Key example

Keys reference texts in language files.

`my_texts.text_notes`

The first part of the key (`my_texts`) is the file name of the language file (in `lang/en/my_texts.php`). The second part of the key (`text_notes`) is the variable name in the language file.

This is a `config.php` example using language keys:

```
return [

  '#theme-name' => 'IdeaSpace 360',
  '#theme-key' => 'ideaspace-360-photo-sphere-viewer',
  '#theme-version' => '1.0',
  '#ideaspace-version' => '>=1.0.0',
  '#theme-description' => 'Photo sphere viewer with navigation menu in VR. Attach text annotations to your photo spheres.',
  '#theme-author-name' => 'IdeaSpaceVR',
  '#theme-author-email' => 'info@ideaspacevr.org',
  '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
  '#theme-keywords' => 'photo sphere, gaze input navigation, mobile, 360, photography',
  '#theme-view' => 'scene',

  '#content-types' => [

    'text-notes' => [
      '#label' => 'my_texts.text_notes',
      '#description' => 'my_texts.text_notes_description',
      '#max-values' => 'infinite',
      '#fields' => [

        'note' => [
          '#label' => 'my_texts.text_note',
          '#description' => 'my_texts.enter_some_text',
          '#help' => 'my_texts.text_note_help',
          '#type' => 'textfield',
          '#maxlength' => 140,
          '#contentformat' => 'text',
          '#required' => true,
        ],

      ], /* fields */

    ], /* notes */

	] /* content types */

];
```

Let's look into the `lang/en/my_texts.php` language file:

```
<?php

return [

	'text_notes' => 'Text Notes',
	'text_notes_description' => 'Manage your text notes which are attached to your photo spheres.',
	'text_note' => 'Text Note',
	'enter_some_text' => 'Enter some text.',
	'text_note_help' => 'The text note can be attached to a photo sphere.',

];
```

That's where the texts are referenced.

If we wanted to have a german translation we would add a `lang/de/my_texts.php` file:

```
<?php

return [

  'text_notes' => 'Text Notizen',
  'text_notes_description' => 'Organisiere deine Text Notizen fuer deine 360 Grad Fotos.',
  'text_note' => 'Text Notiz',
  'enter_some_text' => 'Schreibe einen Text.',
  'text_note_help' => 'Die Text Notiz kann an einem 360 Grad Foto plaziert werden.',

];
```







