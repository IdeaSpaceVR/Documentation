## Content Types and Field Types

A content type consists of one or many fields. A field is defined by a field type. An example for a content type is `blog post`. An example for a field is `text field`. Its field type is text field and it has a couple of other settings (`#maxlength`, `#description`, etc.). Another example would be `image upload field`. The field type would be `image`. 

Both, the text field and the image upload field are part of the content type `blog post`. A user can create one or many blog posts by entering text into the text field and upload an image. The `#required` setting of a field defines, if it is mandatory or optional. 

A VR Theme can define one or many content types in its configuration file `config.php`.

A detailed list of all field types can be found <a href="field-type-reference">here</a>.
