# React Project Video

[react - Beginner](https://egghead.io/lessons/react-custom-proptype-validation)

Hasil dari rekam di simpan di external HD

## Belajar React JS

Install via npm

	npm i create-react-app -g

Create new app

	create-react-app react-app

	cd react-app

	npm start

Custome app.js

	import React from 'react';

	const App = () => <h1>Hello World</h1>

	export default App;

Custome index.js

	import React from 'react';
	import ReactDOM from 'react-dom';
	import App from './App';

	ReactDOM.render(
		<App />,
		document.getElementById("root");
	); 	

#### Membuat React Component

app.js file:

	import React from 'react';

	class App extends React.Component{
		render() {
			return <h1>Hello React Component</h1>
		}
	}

	export default App; 

Normal JS

	return React.createElement('h1', null, 'Hello React');	


