# React Learning Sources

#### [Getting Start](https://github.com/vanbumi/CodeJournal/blob/master/React/getting-start.md)

#### [Introduction to React Book by Cory Gackenheimer](https://github.com/vanbumi/CodeJournal/blob/master/React/intro-to-react-book.md)

## Awesome Tut!

#### [React.js Introduction For People Who Know Just Enough jQuery To Get By](http://reactfordesigners.com/labs/reactjs-introduction-for-people-who-know-just-enough-jquery-to-get-by/)

Last read: 		Writing the Event Handler

Editor: 	http://jsbin.com/ 

## How to write Default Props

getDefaultProps is function

	getDefaultProps: function() {
		return {
			name: 'defaultname'
		}
	},

## How to write Props Type

Props Type is an object

Sample:

	propTypes: {
	   name: React.PropTypes.string
	},

You can add property Required which add this  .isRequired onto this line:

 	React.PropTypes.string.isRequired

## Sample React

[5 Practical Examples](http://tutorialzine.com/2014/07/5-practical-examples-for-learning-facebooks-react-framework/)

[Sample React 	](https://github.com/facebook/react/wiki/Examples)

[React Demos](https://github.com/ruanyf/react-demos)

## React Bootstrap

[ReactBootstrap](https://react-bootstrap.github.io/) 	

## Like Button

[Like Button](https://facebook.github.io/react/docs/interactivity-and-dynamic-uis.html)

## Guides React

[Learn from the web](https://facebook.github.io/react/docs/why-react.html)

[React Form](http://facebook.github.io/react/docs/forms.html)

## Learn Flux

[facebook.github.io/flux](http://facebook.github.io/flux/)

## React Rails

[React Guides for Rails Developer](https://www.airpair.com/reactjs/posts/reactjs-a-guide-for-rails-developers)

#### Rails Form into React Form, Learn this:

[Stack Overflow](http://stackoverflow.com/questions/31628436/react-on-rails-integration)

[RailsConf ReactJs on Rails](https://www.youtube.com/watch?v=kTSsZrub5iE)

## Create Slug with React

#### Slug Regex

	slugify(text){
	   return text.replace(/[^-a-zA-Z0-9\s+]+/ig, '').replace(/\s+/gi, "-").toLowerCase();
	  }

#### Origininal Form React

	var Input = React.createClass({
        getInitialState: function() {
          return {value: 'Hello!'};
        },
        handleChange: function(event) {
          this.setState({value: event.target.value});
        },
        render: function () {
          var value = this.state.value;
          return (
            <div>
              <input type="text" value={value} onChange={this.handleChange} />
              <p>{value}</p>
            </div>
          );
        }
      });

      ReactDOM.render(<Input/>, document.body);

#### Form Slug

	<div id="slug"></div>

	<script type="text/babel">
	    var Input = React.createClass({
	      getInitialState: function() {
	        return {value: 'Hello!'};
	      },
	      handleChange: function(event) {
	        this.setState({value: event.target.value});
	      },
	      render: function() {
	        var value = this.state.value;
	        return (
	          <div>
	            <input type="text" value={value} onChange={this.handleChange} />
	            <p>{value.replace(/\W+/g, "-").toLowerCase()}</p>
	          </div>
	        );
	      }
	    });

	  // ReactDOM.render(<Input />, document.body);
	     ReactDOM.render(
	         <Input />,
	         document.getElementById('slug')
	     );

	</script>
