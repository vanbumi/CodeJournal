## Project Video Tutorial React Rails (RR)

### Langkah-langkah

Membuat rails app baru

	rails new rr_app

Referensikan react-lib dan react-dom di application layout	

	<script src="https://fb.me/react-15.1.0.js"></script>
	<script src="https://fb.me/react-dom-15.1.0.js"></script

Membuat Controller Tutorial

	rails g controller tutorial index	

View tutorial#index

Referensikan:

	<script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.14.6/react.js"></script>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.14.6/react-dom.js"></script>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.23/browser.min.js"></script>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/marked/0.3.2/marked.min.js"></script>

Membuat Div:

	<div id="container">
	    <!-- This element's contents will be replaced with your component. -->
	</div>

Di javascript file:

	var Hello = React.createClass({
	  render: function() {
	    return <div>Hello {this.props.name}</div>;
	  }
	});

	ReactDOM.render(
	  <Hello name="World" />,
	  document.getElementById('container')
	);

Tes di browser localhost:3000

