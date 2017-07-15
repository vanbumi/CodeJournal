# Basic

	var app = angular.module('myApp', []);
	app.controller('myCtrl', function($scope) {
	    $scope.firstName= "John";
	    $scope.lastName= "Doe";
	});

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
	