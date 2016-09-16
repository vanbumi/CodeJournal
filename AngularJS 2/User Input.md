## Button & Input

	@Component({
	  selector: 'my-app',
	  template: `
	    <div>
	      <h2>Hello {{name}}</h2>
	      <button (click)='onClick()'>Click Me</button>
	      <input type='text' placeholder='input something' #box (keyup)='onKeyup(box.value)'>
	      {{ userWrited }} or {{box.value}}
	    </div>
	    
	  `,
	})
	export class App {
	  
	  public userWrited:string;
	  
	  constructor() {
	    this.name = 'Angular2 (Release Candidate!)'
	  }
	  
	  onClick(){
	    alert('You are clicked it!!')
	  }
	  
	  onKeyup(value:string){
	    // alert(value);
	    this.userWrited = value;
	  }
	  
	}
