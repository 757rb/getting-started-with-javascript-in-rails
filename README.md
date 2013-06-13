
# Getting Started with JavaScript in Rails

* Really... Getting started with JavaScript "& Rails"
* Different levels of usage from beginner to advanced.
* Review some anti-patterns and best practices.

http://www.procata.com/blog/archives/2005/05/10/expert-programmers/


## Level 1

#### The Beginner

* Putting JavaScript at the end of the page in a `<script>` tag.
* Writing everything in [`jQuery.ready()`](http://api.jquery.com/ready/).

```erb
<%= form_for @user do |f| %>
  <%= f.text_field :name %><br />
  <%= f.text_field :email %><br />
  <%= f.submit %>
<% end %>
<script type="text/javascript">
  $(function(){
    $('#user').submit(function(e){
      var email = $('#user_email').val();
      if (email.length === 0) {
        e.preventDefault();
        alert('Please enter your email.');
      };
    })
  })
</script>
```

* Example could include any complex form behavior. 
  1) Show or hide sections.
  2) Dynamic elements based on a select.
  3) Etc...
* The anonymous function to `jQuery()` is shorthand for `$(document).ready()`.
* All logic in anonymous functions and handlers.
* Even simple example demonstrates complexity and right drift.


## Level 2

#### The Advanced Beginner

* JavaScript is all loaded in the head.
* Naming functions, but still using top level scope.
* Basic scope separation of concerns.

```erb
<head>
  <script type="text/javascript" src="/assets/application.js"></script>
</head>
<%= form_for @user do |f| %>
  ...
<% end %>
<script type="text/javascript">
  $(function(){ $('#user').submit(submitUserForm); })
</script>
```

```javascript
function fieldPresent(sel) {
  var val = $(sel).val();
  var present = val !== null && val !== undefined && val.length !== 0
  return present;
}
function submitUserForm(e) {
  if (fieldPresent('#user_email')) {
    e.preventDefault();
    alert('Please enter your email.');
  };
}
```

* Still uses document ready to start the process off.
* Very functional and stateless.
* Perhaps you may even namespace 


## Level 3

#### Competent

* All your JavaScript is at the bottom of the page.
* Can safely ignore 

## Level 4

#### Proficient

* Now using CoffeeScript.
* Class encapsulates a specific DOM tree concern.
* Single instance instantiation solves per-page-specific.


## Level 5

#### Expert

* Using a MV* framework. 