# AngularJS

## Basic

Script	

	var app = angular.module('myApp', []);
	app.controller('myCtrl', function($scope) {
	    $scope.firstName= "John";
	    $scope.lastName= "Doe";
	});

html

	<html ng-app="myApp">
		<head>
			<title>Angular Aye</title>
			<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.5.8/angular.min.js"></script>
		</head>
		<body ng-controller="myCtrl">
			<p>
				Your Firstname : {{ firsName }}
			</p>
			<p>
				Your Lastname : {{ lastName }}
			</p>
		</body>
	</html>


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


