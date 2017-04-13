# Building a Basic VR Theme

- [Getting Started](#getting-started)
- [Directory Structure of the Starter Theme](#directory-strucuture)
- [Theme Configuration (config.php)](#theme-configuration)
- [View Templates](#view-templates)


<a name="getting-started"></a>
### Getting Started

We are going to build a basic VR Theme which you can use with your IdeaSpaceVR installation. As an example we use the <a href="https://github.com/IdeaSpaceVR/Starter-Theme" target="_blank">Starter Theme</a>. You can <a href="https://github.com/IdeaSpaceVR/Starter-Theme/releases">download the theme here</a>. 

<iframe width="100%" height="300" allowfullscreen frameborder="0" src="https://www.ideaspacevr.org/theme-preview/starter-theme"></iframe>

This theme shows some text which is animated and the text is managed by IdeaSpaceVR. For the theme development you can use a local IdeaSpaceVR installation (on your PC, using <a href="https://www.mamp.info/en/" target="_blank">MAMP</a>) and a text editor. <a href="https://www.ideaspacevr.org/download" target="_blank">Download the latest IdeaSpaceVR release here</a>. After installing IdeaSpaceVR, extract and copy the Starter Theme files into your `/themes` directory. It should look like that: `/themes/starter-theme`. 


<a name="directory-strucuture"></a>
### Directory Structure of the Starter Theme 

- `starter-theme/config.php`

  This is the central configuration file for your theme. It contains all meta information about the theme (name, description, etc.) as well as the definition of the content types and field types. These determine the composition of the content. For example a content type called "blog post" would consist of - let's say two fields: a title and a text field. The fields would have the type textfield and textarea respectively.  

- `starter-theme/css/style.css`

  The CSS file contains styles for the 2D elements of a VR Theme: for example an introduction box explaining how to navigate the theme in virtual reality.

- `starter-theme/functions.php`

  This file contains all event listeners for your theme: for example an event listener can be set up in order to generate a preview image with lower resolution. To keep things simple there are no event listeners for the Starter Theme. 

- `starter-theme/js/aframe.min.js`

  The A-Frame JavaScript library for WebVR. In general you are free to use any WebVR JavaScript library, for example: React VR. 

- `starter-theme/js/aframe-layout-component.min.js`

  An A-Frame JavaScript layout component for extending the base A-Frame library. This component is used for positioning the text messages in the Starter Theme.

- `starter-theme/screenshot.png`

  This image is a screenshot taken from the theme. It is shown along with the theme description when installing a theme. 

- `starter-theme/views/index.blade.php`

  This is the main view template file. It loads all JavaScript WebVR libraries. IdeaSpaceVR uses <a href="https://laravel.com/docs/5.2/blade" target="_blank">Laravel's Blade templates</a>. 

- `starter-theme/views/scene.blade.php`

  This is the scene template file. It contains all theme-specific JavaScript WebVR code as well as Blade template code. 

- `starter-theme/views/assets.blade.php`

  This is the assets template file. Load assets like images, videos, etc. which are referenced in your scene template file. The Starter Theme does not load any assets.


<a name="theme-configuration"></a>
### Theme Configuration (config.php)

    return [

      '#theme-name' => 'Starter Theme',
      '#theme-key' => 'starter-theme',
      '#theme-version' => '1.0',
      '#ideaspace-version' => '>=1.0.0',
      '#theme-description' => 'Getting Started with VR Theme development.',
      '#theme-author-name' => 'IdeaSpaceVR',
      '#theme-author-email' => 'info@ideaspacevr.org',
      '#theme-homepage' => 'https://www.ideaspacevr.org/themes',
      '#theme-keywords' => 'starter theme, simple',
      '#theme-compatibility' => 'Google Cardboard, Daydream, Oculus, Samsung Gear VR, no headset',
      '#theme-view' => 'scene',

      '#content-types' => [

        'messages' => [
          '#label' => 'Messages',
          '#description' => 'Write some messages and view them in VR.',
          '#max-values' => 'infinite',
          '#fields' => [

            'message-text' => [
              '#label' => 'Message',
              '#description' => 'Enter some text.',
              '#help' => '',
              '#type' => 'textfield',
              '#maxlength' => 200,
              '#contentformat' => 'text',
              '#required' => true,
            ],

          ], /* fields */

        ], /* messages */

      ], /* content types */

    ];

The config.php file consists of two parts: 

- General information about the theme (name, description, etc.)

  Most of these parameters should be self-explanatory. IMPORTANT: the `#theme-key` must not contain spaces or any special characters! For separation of words simply use `-`, for example `starter-theme`. Additionally give your theme a version number (`#theme-version`) as well as specify the minimum IdeaSpaceVR version which your theme needs to run on (`#ideaspace-version`). 

- Content type configuration

  This part of the file defines which content the user can enter, upload or configure when a new space is created or edited.

  ![IdeaSpaceVR - Building Basic VR Theme](/assets/documentation/images/building-basic-vr-theme-1.png "IdeaSpaceVR - Building Basic VR Theme") {.img-responsive}

  The Edit Space page shows a `Message` area with an `Add Message` button as well as a list with existing messages. This area is a content type as defined in the `config.php` file. The following Add Message screenshot shows two text fields. The first text field is a default text field and defined by IdeaSpaceVR. The second Message text field is defined in the `config.php` file. 


  ![IdeaSpaceVR - Building Basic VR Theme](/assets/documentation/images/building-basic-vr-theme-2.png "IdeaSpaceVR - Building Basic VR Theme") {.img-responsive}

  The theme configuration file (`config.php`) can define one or many content types. And each content type can define one or many fields. Each field is described by a `#type` and other parameters. Take a look at <a href="content-types-and-field-types">Content Types and Field Types</a> which lists all available fields and types. 

  Looking at our Starter Theme, the content type `messages` has `#label`, `#description`, `#max-values` (set to `infinite`: we want to allow an infinite number of messages) and `#fields`. 

  The content type `messages` defines just one field called `message-text`. This field has `#label`, `#description`, `#help`, `#type`, `#maxlength`, `#contentformat` and `#required` (which is set to true, so this field is mandatory to fill out before saving the message).   

  To summarize we can say that the `config.php` file and its content type definitions are the backend part of a theme which stores content in the database. The next step is to get the content from the database into a virtual reality scene. And that's where Views Templates come into play. 


<a name="view-templates"></a>
### View Templates 

All view template files are located in the `views` directory. There are three files: `index.blade.php`, `scene.blade.php` and `assets.blade.php`. If you are more comfortable with <a href="https://laravel.com/docs/5.2/blade" target="_blank">Blade templates</a>, you are free to organize your view template files as you wish. IdeaSpaceVR does not impose any restriction to template file organization. Larger VR Theme projects may find it convenient to split up different parts of the theme into different view template files.  

<br>

#### index.blade.php

The main view template is `index.blade.php`. It loads all JavaScript WebVR libraries and it includes a section by using `@yield('scene')`. `@yield` is a Blade template engine directive which includes a section called `scene`. The section is defined in the template file `scene.blade.php`.  

    <!DOCTYPE html>
    <html>
    <head>
    <title>@yield('title')</title>

    <link rel="shortcut icon" type="image/png" href="{{ url('favicon.ico') }}"/>

    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">
    <!-- Fullscreen Landscape on iOS -->
    <meta name="apple-mobile-web-app-capable" content="yes">

    <meta name="abstract" content="@yield('title')" />
    <meta name="description" content="@yield('title')" />
    <meta name="keywords" content="" />
    <meta name="copyright" content="" />
    <meta name="robots" content="follow, index" />

    <meta http-equiv="origin-trial" data-feature="WebVR" data-expires="04/11/17" content="{{ $origin_trial_token }}">

    <meta property="og:site_name" content="@yield('title')" />
    <meta property="og:image:secure_url" content="{{ url($theme_dir . '/screenshot.png') }}"/>
    <meta property="og:image" content="{{ url($theme_dir . '/screenshot.png') }}" />
    <meta property="og:description" content="@yield('title')" />
    <meta property="og:title" content="@yield('title')" />
    <meta property="og:type" content="website" />
    <meta property="og:url" content="{{ \Request::url() }}" />

    <link rel="stylesheet" href="{{ url($theme_dir . '/css/style.css') }}">
    <script src="{{ url($theme_dir . '/js/aframe.min.js') }}"></script>
    <script src="{{ url($theme_dir . '/js/aframe-layout-component.min.js') }}"></script>
    </head>
    <body>

    @yield('scene')

    </body>
    </html>


<br>

#### scene.blade.php

The `scene.blade.php` file contains the Blade template directives `@extends` and `@section`. `@extends('theme::index')` defines that it is extending the index view template. The HTML code between `@section('scene')` and `@endsection` contains the WebVR A-Frame code which renders the virtual reality scene. 

`@include('theme::assets')` includes assets for A-Frame which are defined in a file called `assets.blade.php`. In our Starter Theme we do not use assets like images, videos or 3D models, therefore we can ignore this directive.

As you can see, we are looping through the `$content['messages']` PHP array. `messages` is the name of our content type as defined in the `config.php` file. 

IMPORTANT: any content type name defined in `config.php` is available as a PHP array in the theme variable `$content` within the view templates.   

If you already entered some text messages in IdeaSpaceVR, you can loop through the PHP array `$content['messages']` by using the Blade `@foreach` and `@endforeach` directives. 

The text content can be retrieved by using this statement: `{{ $message['message-text']['#value'] }}`. The curly brackets are just a Blade template directive similar to `<?php ?>`.

By looping through the PHP array, we generate an `a-text` entity and assign the text value to the value parameter of the entity. How A-Frame works is not part of this guide. A-Frame offers <a href="https://aframe.io/docs" target="_blank">an excellent documentation online</a>.

    @extends('theme::index')

    @section('title', $space_title)

    @section('scene')

    <a-scene>

      @include('theme::assets')

      <a-entity layout="type: line; margin: 1.4" position="-2.4 -1 0" rotation="-60 0 90">

      @foreach ($content['messages'] as $message)

          <a-text position="0 0 0" rotation="0 0 -90" color="#ffd536" value="{{ $message['message-text']['#value'] }}"></a-text>

      @endforeach

          <a-animation attribute="position" to="-2.4 50 -100" dur="700000" easing="linear"></a-animation>

      </a-entity>

      <a-sky color="#000000"></a-sky>

    </a-scene>

    @endsection 

These are the basic concepts of building a VR Theme. Preview the <a href="https://www.ideaspacevr.org/theme-preview/starter-theme" target="_blank">Starter Theme in fullscreen here</a>.



