# AngularJS

<!-- ## How to create a module

### Use angular object's module() method to create a module

	var myApp = angular.module("myModule", []);
	
### How to create controller

	var myController = function($scope) {
	    $scope.message = "Angular JS Tutorial";
	};

### How to register the controller with the module

	myApp.controller("nameOfController", nameOfcontroller function);

	-> myApp.controller("myController", mycontroller);

### Or other option do this:

	myApp.controller("myController", function($scope) {
	    $scope.message = "Angular JS Tutorial";
	}); -->

+ [indonesian-currency-on-angular](http://stackoverflow.com/questions/32967366/indonesian-currency-on-angular)

or

Custom Format Rupiah (Angularjs Filter)
	
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



