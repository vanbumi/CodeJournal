# Carousel on Rails

#### Try this
http://stackoverflow.com/questions/30446181/rails-each-method-with-changing-html-bootstrap-carousel

    <!-- Indicators -->
    <ol class="carousel-indicators">
        <% @slides.each_with_index do |slide, i| %>
            <li data-target="#mycarousel" data-slide-to=#{i) class="#{'active' if i == 0}"></li>
        <% end %>
    </ol>

    <!-- Wrapper for slides -->
    <div class="carousel-inner">
        <% @slides.each_with_index do |slide, i| %>
            <div class="item #{'active' if i == 0}">
                <%= image_tag('user/' + slide.image_file_name , class: 'fill img-responsive') %>
                <div class="carousel-caption">
                    <h2>Caption 1</h2>
                </div>
            </div>
        <% end %>
    </div> 

#### Also try this
 
Heres what worked:

    <% @gallery.images.each_with_index do |image, index| %>
        <li> <a id="carousel-selector-<%=index%>" class="<%= 'selected' if index == 0 %>">
            <%= image_tag image.photo.url(:thumb), class: 'img-responsive' %>
            </a>
        </li>
    <% end%>

And if anyone is searching for a solution for .carousel-inner div (pretty much the same):

    <div class="carousel-inner">
        <% @gallery.images.each_with_index do |image, index| %>
            <div class="item <%= 'active' if index == 0%>" data-slide-number="<%= index %>">
              <%= image_tag image.photo.url(:large), class: 'img-responsive' %>
            </div>
        <% end%>
    </div> 

#### Example case on dearmombaby

    <!-- Start Carousel Slider -->
    <div id="slider">
        <div id="carousel-example-generic" class="carousel slide" data-ride="carousel">
            <!-- Indicators -->
            <ol class="carousel-indicators">
                <li data-target="#carousel-example-generic" data-slide-to="0" class="active"></li>
                <li data-target="#carousel-example-generic" data-slide-to="1"></li>
                <li data-target="#carousel-example-generic" data-slide-to="2"></li>
            </ol>

            <!-- Wrapper for slides -->
            <div class="carousel-inner" role="listbox">

                <% @slider_galeries.each_with_index do |slider_galery, index| %>
                    <div class="item <%= 'active' if index == 0 %>" data-slide-to="<%= index %>" >
                        <% slider_galery.img_sliders.each do |image| %>
                            <%= cl_image_tag(image.path, { size: '', crop: :fit }) %>
                        <% end %>
                        <div class="carousel-caption">
                            <%= slider_galery.description %>
                        </div>                  
                    </div>
                <% end %>
            </div>

            <!-- Controls -->
            <a class="left carousel-control" href="#carousel-example-generic" role="button" data-slide="prev">
                <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
                <span class="sr-only">Previous</span>
            </a>
            <a class="right carousel-control" href="#carousel-example-generic" role="button" data-slide="next">
                <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
                <span class="sr-only">Next</span>
            </a>
        </div>
    </div>
    <!-- End Carousel Slider -->       