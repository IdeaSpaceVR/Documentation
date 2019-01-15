## Field Groups

Field groups allow you to organize fields into groups which are rendered as collapsible boxes. Use field groups if you have a lot of input fields which can be organized into groups.   

<table class="table table-bordered">
<thead>
<tr>
  <th>Setting</th><th>Value(s)</th><th>Value Type</th><th>Mandatory</th>
</tr>
</thead>
<tbody>
<tr>
  <td>#field-groups</td><td>['key1' => 'Title 1', 'key2' => 'Title 2']</td><td>Key-value pairs</td><td>no</td>
</tr>
<tr>
  <td>#field-group</td><td>'key1'</td><td>String</td><td>no</td>
</tr>
</tbody>
</table>

Example `config.php` with two field-groups:

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

				'blog-posts' => [
					'#label' => 'Blog Posts',
					'#description' => 'Manage your blog posts.',
					'#max-values' => 'infinite',

					'#field-groups' => ['north' => 'North', 'south' => 'South'],

					'#fields' => [

						'post-title' => [
							'#label' => 'Title',
							'#description' => 'Write a text.',
							'#help' => 'Write a text.',
							'#type' => 'textfield',
							'#maxlength' => 1000,
							'#contentformat' => 'html/text',
							'#required' => true,
						],

						'post-audio' => [
							'#label' => 'Sound',
							'#description' => 'Add a background sound to your post.',
							'#help' => 'Add a background sound to your post.',
							'#type' => 'options-select',
							'#options' => ['birds' => 'Birds', 'ocean' => 'Ocean', 'street' => 'Street'],
							'#required' => false,
						],

						'post-text-north' => [
							'#label' => 'Text',
							'#description' => 'Write a text.',
							'#help' => 'Write a text.',
							'#type' => 'textarea',
							'#rows' => 10,
							'#maxlength' => 20000,
							'#contentformat' => 'html/text',
							'#required' => false,

							'#field-group' => 'north',
						],

						'post-image-north' => [
							'#label' => 'Image',
							'#description' => 'Add an image.',
							'#help' => 'Add an image.',
							'#type' => 'image',
							'#content-preview-image' => true,
							'#file-extension' => ['jpg', 'png', 'gif'],
							'#required' => false,

							'#field-group' => 'north',
						],

						'post-text-south' => [
							'#label' => 'Text',
							'#description' => 'Write a text.',
							'#help' => 'Write a text.',
							'#type' => 'textarea',
							'#rows' => 10,
							'#maxlength' => 20000,
							'#contentformat' => 'html/text',
							'#required' => false,

							'#field-group' => 'south',
						],

						'post-image-south' => [
							'#label' => 'Image',
							'#description' => 'Add an image.',
							'#help' => 'Add an image.',
							'#type' => 'image',
							'#content-preview-image' => true,
							'#file-extension' => ['jpg', 'png', 'gif'],
							'#required' => false,

							'#field-group' => 'south',
						],

					], /* fields */

				], /* blog-posts */

      ], /* content types */

    ];
```

