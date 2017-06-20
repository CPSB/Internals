# [THEMING]: Blade backend library. 

Source: [Laravel documentation](https://laravel.com/docs/4.2/templates#blade-templating)

## Defining blade in the controller. 

You can simply define the blade view with `return $this->blade->render('<view name>', (array) $variables);`.

**Example:**

```php 
class UsersController extends CI_Controller 
{
  /**
   * Show the users controller 
   */
  public function showProfile() 
  {
    $data['title'] = 'Users controller.'; 
    $data['users'] = ['name' => 'John', 'lastname' => 'Doe']; 
    
    return $this->blade->render('users/profile', $data);
  }
}
```

## Blade templating. 

Blade is a simple, yet powerfule templating engine normally provided with Laravel. Unlike controller layouts, 
Blade is driven by *tezmplate inheritance* and *sections*. All blade templates should use the `.blade.php` extension.

```blade
<!-- Stored in application/views -->

<html>
  <body>
    @section('sidebar')
      This is the master sidebar.
    @show 
    
    <div class="container">
      @yield('content')
    </div>
  </body>
</html>
```

Note that views which `extend` a Blade layout simply override sections from the layout. 
Content dof the layout can be included in a child view using the `@parent` directive in a 
section, allowing you to append to the contents of a layout section, such as a sidebar or footer. 

Sometimes, such as when you are not sure if a section has been defined, you may wish 
to pass a default value to the `@yield` directive. You may pass the default value as the second argument:

 ```blade
 @yield('section', 'Default content')
 ```
 
 ## Other blade control structures
 
**Echoing data**

```blade 
Hello, {{ $data }}

the current UNIX timestamp is {{ time() }}
```

**Echoing data aftr checking for existence**

Sometimes you may wish to echo a variable, but you aren't sure if the variable has been set. Basically, wou want to do this: 

```blade
{{ isset($name) ? $name : 'Default' }}
```

However, instead of writing a ternary statement, Blade allows you to use the following convenient short-cut:

```blade
{{ $name or 'Default' }}
```

**Displaying raw text with curly braces**

If you need to display a string that is wrapped in curly braces, you may escape the Blade behavior by prefixing your text with an 
`@` symbol:

```blade
@{{ This will not be processed by Blade }}
```

Of course, all user supplied data should be escaped or purified. To escape the output, 
you may use the triple curly brace syntax:

```blade
Hello, {{{ $name }}}.
```

If you don't want the data to be escaped, you may use double curly-braces:

```blade
Hello, {{ $name }}.
```

**Note:**  Be very careful when echoing content that is supplied by users of your application. 
Always use the triple curly brace syntax to escape any HTML entities in the content.

### If statements 

```blade
@if (count($records) === 1)
    I have one record!
@elseif (count($records) > 1)
    I have multiple records!
@else
    I don't have any records!
@endif

@unless (Auth::check())
    You are not signed in.
@endunless
```

### Loops 

```blade
@for ($i = 0; $i < 10; $i++)
    The current value is {{ $i }}
@endfor

@foreach ($users as $user)
    <p>This is user {{ $user->id }}</p>
@endforeach

@forelse($users as $user)
    <li>{{ $user->name }}</li>
@empty
    <p>No users</p>
@endforelse

@while (true)
    <p>I'm looping forever.</p>
@endwhile
```

### Including sub-views: 

```blade
@include('view.name')
```

You may also pass an array of data to the included view:


```blade
@include('view.name', array('some'=>'data'))
```

### Overwriting sections: 

To overwrite a section entirely, yyou may use the `overwrite` statement: 

```blade
@extends('list.item.container')

@section('list.item.content')
    <p>This is an item of type {{ $item->type }}</p>
@overwrite
```

### Comments 

```blade
{{-- This comment will not be in the rendered HTML --}}
```
