# React Form

## Example 1 

```react
class NameForm extends React.Component {
    constructor(props) {
        super(props);
        this.state = {
            name: '',
            lastName: 'Bumi'           
        };
    }

    nameHandleChange(event) {
        this.setState({name: event.target.value});
    }
    
    lastHandleChange(event) {
        this.setState({lastName: event.target.value});
    }

    handleSubmit(event) {
        alert('A name was submitted: ' + this.state.name + ' ' + this.state.lastName);
        event.preventDefault();
    }

    render() {
        return (
        <form onSubmit={this.handleSubmit}>
            <label>
                Name:
                <input type="text" value={this.state.name} onChange={this.nameHandleChange.bind(this)} />
                <br />
                Last Name:
                <input type="text" value={this.state.lastName} onChange={this.lastHandleChange.bind(this)} />
            </label>
            <input type="submit" value="Submit" />
        </form>
        );
    }
}

ReactDOM.render(
    <NameForm />,
    document.getElementById('root')
);
```

## Example 2

    class NewItem extends React.Component {
        constructor(props) {
            super(props);
    
            this.state = {
                name: '',
                description: ''
            }
        }
        
        NameHandleChange(event) { 
            this.setState({name: event.target.value });     
        }
    
        DescHandleChange(event) { 
            this.setState({description: event.target.value });     
        }
    
        handleSubmit(event) {
            const name = this.state.name;
            const description = this.state.description; 
    
            alert('name: ' + name + ' description: ' + description);
            event.preventDefault();
        }
    
        render() {
            return (
                <div>
                    <input 
                        onChange={this.NameHandleChange.bind(this)} type="text" value={this.state.name} placeholder='Enter the name of the item' 
                    /> 
                    <input 
                        onChange={this.DescHandleChange.bind(this)} type="text" value={this.state.description} placeholder='Enter a description' 
                    /> 
                    <button 
                        onClick={this.handleSubmit.bind(this)}
                    >
                        Submit
                    </button>
                </div>
            )
        }
    }

## Example 3        

c