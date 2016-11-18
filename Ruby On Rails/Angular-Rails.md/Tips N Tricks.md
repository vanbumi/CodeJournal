# Tips N Tricks

### Add item into list by **$scope. .push**

	$scope.addPost = function(){
		if(!$scope.title || $scope.title === '') {return;}
		$scope.posts.push({
	    title: $scope.title,
	    link: $scope.link,
	    upvotes: 0
	  });
		$scope.title = '';
	  $scope.link = '';
	};

### ng-hide

Directive **ng-hide**, used which hides elements when an Angular expression evaluates to true.

### Using a Service

In Angular, services are declared much like controllers. Inside app.js/scripts.js (you name it)

#### My First Service... Is Really a Factory

	angular.module('flapperNews', [])
	.factory('posts', [function(){
	  // service body
	}])

> MainCtrl controller should appear below this):

	.controller('MainCtrl', function($scope) {

		....