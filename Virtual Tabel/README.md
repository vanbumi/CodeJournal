# Work with Virtual Table Database

Case on book

page 152

	$ rails g scaffold Provinsi provinsi_nama:string

	$ rails g scaffold Kabupaten provinsi_id:integer kabupaten_nama:string

Or

	$ rails g model Provinsi provinsi_nama:string

	$ rails g model Kabkot provinsi_id:integer kabkot_id:integer kabkot_nama:string

Description on tabel

tabel Provinsis
	field: id 
	field: provinsi_name

tabel Kabkots
	field: id
	field: provinsi_id
	field: kabkot_id
	field: kabkot_nama

Question: 

Dalam membuat virtual tabel antara Provinsi & Kabkot, pada saat generate model perlu membuat kabkot_id, padahal bila membuat scaffold kabkot, id sudah otomatis di generate.

## Generate Virtual Table	

	$ rails g migration CreateVKabkots

	class CreateVKabkots < ActiveRecord::Migration
		def change 
			self.connection.execute %Q(
				create view v_kabkots as

			select
				kabkots.id, --------------> read: table: kabkots, field: id
				kabkots.provinsi_id, -----> read: table:kabkots, field: provinsi_id
				provinsis.provinsi_nama, -> join table provinsis, field: provinsi_nama
				kabkots.kabkot_id, -------> still no idea why need generate this field?
				kabkots.kabkot_nama ------> read: table kabkots, field: kabkot_nama
			from
				kabkots
				left join provinsis on kabkots.provinsi_id = provinsis.id
			)
		end
	end