# React Hooks

## Custom Hooks useFetch

### Normal Sintax

	import React, { useEffect, useState } from 'react';
	
	function Joke() {
	  const [joke, setJoke] = useState({});
	
	  useEffect(() => {
	    fetch('https://official-joke-api.appspot.com/jokes/random')
	      .then(response => response.json())
	      .then(json => {
	        //console.log('joke json', json);
	        setJoke(json);
	      });
	  }, []);
	
	  const { setup, punchline } = joke;
	
	  return (
	    <div>
	      <h3>Today Joke</h3>
	      <p>{setup}</p>
	      <p><em>{punchline}</em></p>
	    </div>
	  )
	}
	
### Custom Hooks

	import React, { useEffect, useState } from 'react';

	const useFetch = (url, initialValue) => {
		const [result, setResult] = useState(initialValue);
		
		useEffect(() => {
		 fetch(url)
		 	.then(responsee => response.json())
		 	.then(json => setResult(json))
		},[]);
		
		return result;
	}
	
	function Joke() {
		const { setup, punchline } = useFetch('https://official-joke-api.appspot.com/jokes/random', {});
		
		return (
		    <div>
		      <h3>Today Joke</h3>
		      <p>{setup}</p>
		      <p><em>{punchline}</em></p>
		    </div>
		  )
	}










	