# React Project Video

[react - Beginner](https://egghead.io/lessons/react-custom-proptype-validation)

Hasil dari rekam di simpan di external HD

## Belajar React JS

### Episode 1 Setup environment

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

### Episode 2 Membuat React Component

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

### Episode 3

Render method hanya boleh untuk single node, bila lebih dari satu element maka harus wrap dengan tag.

	class App extends React.Component {
		render() {
			return ( 
			<div>
				<h1>Hello Dyo</h1>
				<p>Apakabar</p>	
			</div>
			) 
		}
	}

### Episode 4

Props

term Components pada React adalah semacam function, yang bisa terpisah, indepent dan reusable.

Kemudian di dalam component kita bisa memasukan input yang dinamis, yang bisa di rubah2, inilah props, props juga bisa mengatur dimana kita akan menampilkannya.

Kita bisa passing data ke dalam component dengan menggunakan props.

Pada index.js kita sisipkan props ke dalam element, seperti kita menuliskan atribut di dalam element.

index.js

	ReactDOM.render(
		<App cat={10} txt="Ini adalah props text" />
	)

app.js

	class App extends React.Component {
		render() {
			return <h1>{this.props.txt}</h1>
		}
	}

Atau gunakan variable let

	class App extends React.Component {
		render() {
			let txt = this.props.txt
			return <h1>{txt}</h1>
		}
	}

Kita coba test update index js menjadi:

	Ini adalah props text, kita belajar apa itu props.  

Pada app.js file : Kita juga memberikan/menentukan tipe dari props:

	App.propTypes = {
		txt: React.PropTypes.string,
		cat: React.PropTypes.number.isRequired
	}

Maka akan terjadi Error, karena cat tidak ter defined, untuk itu update index.html tambahkan cat.

Kita juga bisa menambahkan default props:

	App.defaultProps = {
		txt: "Ini adalah default dari text ok!"
	}

Jadi bila di index.html txt kita hapus maka yang akan menucul adalah defaultProps. 

	ReactDOM.render(
		<App cat={10} txt="Ini adalah props text" />
	)














