# Rails 5 Setup

[Github](https://gist.github.com/ssaunier/a32538935e6384af4c29)

## Attachinary Setup

First add the following gems to your `Gemfile`:

```ruby
# Gemfile
gem "attachinary"
gem "jquery-fileupload-rails"
gem "coffee-rails"
```

Then open the terminal and launch:

```bash
bundle install
rails attachinary:install:migrations
rails db:migrate
```

Open your `config/application.rb` and add this line after all the `require`:

```ruby
require "attachinary/orm/active_record"
```

Open the `config/routes.rb` file and add this as first line in the `draw` block:

```ruby
mount Attachinary::Engine => "/attachinary"
```

Open `app/views/layout/application.html.erb` and append this line after the main `javascript_include_tag`:

```erb
<%= cloudinary_js_config %>
```

Open `app/assets/javascripts/application.js` and append these lines before the `require_tree`:

```js
//= require jquery-fileupload/basic
//= require cloudinary/jquery.cloudinary
//= require attachinary
```

Create a file `app/assets/javascripts/init_attachinary.js` and copy-paste those lines:

```
$(document).ready(function() {
  $('.attachinary-input').attachinary();
});
```

# Usage for Rails 5

## One picture per model

You need to update the model:

```ruby
class Product < ApplicationRecord
  has_attachment :photo
  
  # [...]
end
```

And the form (`simple_form` gem used):

```erb
<%= f.input :photo, as: :attachinary %>
```

For non simple_form:

    <%= f.attachinary_file_field :photo %>

And the controller for strong params:

```ruby
def product_params
  params.require(:product).permit(:name, :description, :photo)
end
```

To display the product photo in the view, add:

```erb
<% if @product.photo? %>
  <%= cl_image_tag @product.photo.path %>
<% end %>
```

## Multiple pictures per model

You need to update the model:

```ruby
class Product < ApplicationRecord
  has_attachments :photos, maximum: 2  # Be carefule with `s`
  
  # [...]
end
```

And the form (`simple_form` gem used):

```erb
<%= f.input :photos, as: :attachinary %>
```
I change with this (as previous Rails 4)

	<%= f.attachinary_file_field :photos %>

And the controller for strong params:

```ruby
def product_params
  params.require(:product).permit(:name, :description, photos: [])
end
```

To display the product photos in the view, add:

```erb
<% @product.photos.each do |photo| %>
  <%= cl_image_tag photo.path %>
<% end %>
```

## Bonus - Devise

If you want to add an `avatar` to the `User` model, you need to sanitize regarding the strong params:

```ruby
# app/controllers/application_controller
class ApplicationController < ActionController::Base
  before_action :configure_permitted_parameters, if: :devise_controller?

  def configure_permitted_parameters
    devise_parameter_sanitizer.permit(:sign_up,        keys: [:avatar])
    devise_parameter_sanitizer.permit(:account_update, keys: [:avatar])
  end
end
```

## Add more than one images

Controller:

    private
    def category_params
      params.require(:category).permit(:xxx, :xxx, photos:[], photos_two:[], photos_three:[])
    end

Model:

    has_attachments :photos # maximum: 5  # Be carefule with `s`
    has_attachments :photo_two    
    has_attachments :photo_three

View:

    <h3 class="text-center">Photo Two</h3>
    <!--display here-->
    <% @category.photos_two.each do |photo_two| %>
        <%= cl_image_tag photo_two.path, { size: '350x350', :crop => :fill } %>
    <% end %>
    
Form Upload!:

    <%= f.label :edit_photo_two  %>
    <%= f.attachinary_file_field :photos_two %>

> Becareful with and without 's' :)            