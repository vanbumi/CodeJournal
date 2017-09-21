# React Learning Sources

* [scotch.io](https://scotch.io/tag/react)
* [CODESANDBOX ONLINE REACT PLAYGROUND](https://codesandbox.io/)

### Getting Start

	<!DOCTYPE html>
	<html>
		<head>
			<script src="//fb.me/react-0.14.7.min.js"></script>
			<script src="//fb.me/react-dom-0.14.7.min.js"></script>
			<link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css" rel="stylesheet" type="text/css" />
			<meta charset="utf-8">
			
			<title>JS Bin</title>
		</head>

		<body>
		  <div id="container"></div>
		</body>
	</html>

### Practising test on console

	var TweetBox = React.createClass({
	  handleChange: function(e) {
	    console.log(e.target.value)
	  },
	  render: function() {
	    return (
	      <div className="well clearfix">
	        <textarea className="form-control" onChange={this.handleChange}></textarea><br />
	        <button className="btn btn-primary pull-right" disabled>Tweet</button>
	      </div>
	    );
	  }
	});

	ReactDOM.render(
	  <TweetBox />,
	  document.getElementById("container")
	);	

#### [Getting Start](https://github.com/vanbumi/CodeJournal/blob/master/React/getting-start.md)

#### [Introduction to React Book by Cory Gackenheimer](https://github.com/vanbumi/CodeJournal/blob/master/React/intro-to-react-book.md)

## Tutorial References

#### [React.js Introduction For People Who Know Just Enough jQuery To Get By](http://reactfordesigners.com/labs/reactjs-introduction-for-people-who-know-just-enough-jquery-to-get-by/)

Last read: 		Writing the Event Handler

Editor: 	http://jsbin.com/

#### [Build with React](http://buildwithreact.com/) 

## Awesome 

[React Templates](http://wix.github.io/react-templates/)

---

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

## React Tut

[The React Quick Start Guide: ES6 Edition](http://www.jackcallister.com/2015/08/30/the-react-quick-start-guide-es6-edition.html)

	Liked button!

## ReactJS Koans

[ReactJS Koans](https://github.com/arkency/reactjs_koans)

	Installation:

	$ git clone https://github.com/arkency/reactjs_koans.git
	$ cd reactjs_koans
	$ npm run setup		

You can run a webserver and see your changes live in your web browser:

	npm run start

	Visit http://localhost:8080/

## React Tut Collection!

[codementor.io/learn-reactjs](https://www.codementor.io/learn-reactjs)	

## Rails and React II: A real use case

[Rails and React II: A real use case](http://codeloveandboards.com/blog/2014/09/10/rails-and-react-ii-a-real-use-case/)

## Must Read!

[React.js - A guide for Rails developers](https://www.airpair.com/reactjs/posts/reactjs-a-guide-for-rails-developers)

* [Sample](https://github.com/fervisa/accounts-react-rails/tree/bf1d80cf3d23a9a5e4aa48c86368262b7a7bd809)

## Learn Flux

[facebook.github.io/flux](http://facebook.github.io/flux/)

## Tutorial Point

* [React - Tutorial Point](http://www.tutorialspoint.com/reactjs/))

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

* [React Rails Course](https://learnetto.com/tutorials/quick-introduction-to-key-react-concepts)
* [3 ways to use React with Ruby on Rails 5](https://learnetto.com/blog/3-ways-to-use-react-with-ruby-on-rails-5)
* [Uncontrolled Components](https://facebook.github.io/react/docs/uncontrolled-components.html)
		To write an uncontrolled component, instead of writing an event handler for every state update, you can use a ref to get form values from the DOM.
* [Form & Controlled Component](https://facebook.github.io/react/docs/forms.html).
* [Refs and the DOM](https://facebook.github.io/react/docs/refs-and-the-dom.html).
* [Buat Latihan - React.js - A guide for Rails developers](https://www.airpair.com/reactjs/posts/reactjs-a-guide-for-rails-developers)
* [React POST Request](https://www.npmjs.com/package/axios)


