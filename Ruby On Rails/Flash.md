# Rails Flash  

    class PostsController < ActionController::Base

      def create
        # save post
        flash[:notice] = "Post successfully created"
        redirect_to @post
      end

      def show
        # doesn't need to assign the flash notice to the template, that's done automatically
      end

    end

show.html.erb
    
      <% if flash[:notice] %>
        <div class="notice"><%= flash[:notice] %></div>
      <% end %>

## Devise Flash

[How To: Integrate I18n Flash Messages with Devise and Bootstrap](https://github.com/plataformatec/devise/wiki/How-To:-Integrate-I18n-Flash-Messages-with-Devise-and-Bootstrap)      