
# Getting Started with JavaScript in Rails

* Really... Getting started with JavaScript "& Rails"
* Different levels of usage from beginner to advanced.
* Review some anti-patterns and best practices.


## Level 1


#### The Beginner

* Putting JavaScript at the end of the page in a `<script>` tag.
* Writing everything in `jQuery.read()`.

```erb
<%= form_for @person do |f| %>
  <%= f.label :first_name %>:
  <%= f.text_field :first_name %><br />

  <%= f.label :last_name %>:
  <%= f.text_field :last_name %><br />

  <%= f.submit %>
<% end %>

```

