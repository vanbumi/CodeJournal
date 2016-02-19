# AngularJS

## How to create a module

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
	});

