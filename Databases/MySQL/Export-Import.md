# Save MySQL query results into a text or CSV file

[save-mysql-query-results-into-a-text-or-csv-file](http://www.tech-recipes.com/rx/1475/save-mysql-query-results-into-a-text-or-csv-file/)


	SELECT order_id,product_name,qty
	FROM orders
	WHERE foo = 'bar'
	INTO OUTFILE '/tmp/orders.csv'
	FIELDS TERMINATED BY ','
	ENCLOSED BY '"'
	LINES TERMINATED BY '\n';

This works but the title does not export

	SELECT `kuesioner_pbls`.`id`,`kuesioner_pbls`.`subbidang_id`,`kuesioner_pbls`.`provinsi_id`
		FROM `dbck_mysql`.`kuesioner_pbls`
		-- WHERE foo = 'bar'
		INTO OUTFILE '/tmp/coba.csv'
		FIELDS TERMINATED BY ','
		ENCLOSED BY '"'
		LINES TERMINATED BY '\n';

[exportimport](http://zetcode.com/databases/mysqltutorial/exportimport/)

Inport (masih bingung)

	mysql> LOAD DATA INFILE '/tmp/cars.csv' INTO TABLE Cars
    	FIELDS TERMINATED BY ',';


## This is what you looking for!

[Exporting data to CSV file using MySQL Workbench](http://www.mysqltutorial.org/mysql-export-table-to-csv/)

In case you don’t have access to the database server to get the exported CSV file, you can use MySQL Workbench to export the result set of a query to a CSV file in your local computer as follows:

* First, execute a query get its result set.
* Second, from the result panel, click “export recordset to an external file”. The result set is also known as a recordset.
* Third, a new dialog displays. It asks you for a filename and file format. Enter the file name, choose CSV as the file format and click Save button. 

![wb](http://res.cloudinary.com/medio/image/upload/v1480698991/workbench-exportinport_gtci5h.png)   	