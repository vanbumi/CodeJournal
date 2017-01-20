# How to create Users Upload Form File

## Steps 

### Copy edit.html.erb file and give name upload.html.erb

### Add Condition "params actions" in users form:

### Add new routes in routes.rb

	match "users/:id/upload", to: "users#upload", via: :get

### Update on users controller

	def upload

	end

### Add button



