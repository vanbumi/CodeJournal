# Video React To Do App

[Links](https://www.youtube.com/watch?v=S1oBU7DWt2s&index=5&list=PL-m_C-Go-ZCPKioOKTOpQYEcm5yPHCAFD)

## Part 1

Create directory

	mkdir todo_react

Generate react app

	cd todo_react

	create-react-app .

Run server

	npm start

Look at link

	To get started, edit src/App.js and save to reload. 	

Open it with text editor

Change this 

	<p className="App-intro">
	  To get started, edit <code>src/App.js</code> and save to reload.
	</p>

To become	

	<p className="App-intro">
		Hello React!.
	</p>

Test at friendly error message in browser.

Move to file index.js as entry point of React App.

	ReactDOM.render(
  	<App />,
  	document.getElementById('root')
	);	

root is target on index.html, index.html is as Template

	ReactDOM.render(
	  <App />,
	  document.getElementById('root')
	);

Edit app.js

...

retun (

	<div className="app">
		<div className="app-header">
			<img src="{logo}" className="App-logo" alt="logo">
			<h2>React Todos</h2>
		</div>
		<div className="Todo-App">
			<form action="">
				<input type="text">
			</form>
			<div className="Todo-List">
				<ul>
					<li><input type="checkbox" /> Belajar React</li>
					<li><input type="checkbox" />Bikin Kopi</li>
					<li><input type="checkbox" />Lanjut belajar</li>
				</ul>
			</div>
		</div>

	</div>

)

Tambahkan CSS:

	.Todo App {
		padding-top:28px;
		display:inline-block;
		text-align:left;   
	}

	input {
		font-size: 28px;
	}

	ul {
		padding: 0px;
	}

	li {
		list-style-type: none;
	}

And see on browser :)



