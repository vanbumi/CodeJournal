# Format for Rupiah Currency

	<%= number_to_currency(product.price, precision: 0, unit: "Rp. ", separator: "", delimiter: ".") %>

#### Result => Rp. 75.000

## Sample Case

    <h4 class="pull-right"><%= number_to_currency(product.price, precision: 0, unit: "Rp. ", separator: "", delimiter: ".") %></h4><br>
    <h4><a href="#"><%= product.name %></a></h4>
