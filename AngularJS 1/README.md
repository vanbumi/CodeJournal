# AngularJS

* [indonesian-currency-on-angular](http://stackoverflow.com/questions/32967366/indonesian-currency-on-angular)

or

* Custom Format Rupiah (Angularjs Filter)
	
		<script>
		    var app = angular.module('app', []);
		    app.filter('rupiah', function () {
		        return function (val) {
		            while (/(\d+)(\d{3})/.test(val.toString())){
		                val = val.toString().replace(/(\d+)(\d{3})/, '$1'+'.'+'$2');
		            }
		            var val = 'Rp' + val;
		            return val;
		        };
		    });
		</script> 	

* [50 Sample of Angular](https://github.com/curran/screencasts/tree/gh-pages/introToAngular)
* [JSONPlaceholder](https://jsonplaceholder.typicode.com/)


