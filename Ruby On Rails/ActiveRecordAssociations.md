
## Index View
 
  <tbody>
    <% @kab_kota.each do |kab_kotum| %>
      <tr>
        <td><%= kab_kotum.name %></td>
        <td><%= kab_kotum.provinsi.name if kab_kotum.provinsi %></td>
        <td><%= kab_kotum.description %></td>
        <td><%= link_to 'Show', kab_kotum %></td>
        <td><%= link_to 'Edit', edit_kab_kotum_path(kab_kotum) %></td>
        <td><%= link_to 'Destroy', kab_kotum, method: :delete, data: { confirm: 'Are you sure?' } %></td>
      </tr>
    <% end %>
  </tbody>