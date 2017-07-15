# Getting Started React

## CDN
	
	<script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.14.6/react.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.14.6/react-dom.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.23/browser.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/marked/0.3.2/marked.min.js"></script>

## Simple React

	<h1>Basic React</h1>

	<div id="content"></div>

	<script type="text/babel">

		var DyosComponent = React.createClass({
			render: function() {
				return(
					<h2>Dyo to the best </h2>
				);
			}
		});
		ReactDOM.render(
			<DyosComponent />, 
			document.getElementById('content'));
		
	</script>

	
