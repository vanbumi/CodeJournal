# React Learning Sources

#### [Getting Start](https://github.com/vanbumi/CodeJournal/blob/master/React/getting-start.md)

#### [Introduction to React Book by Cory Gackenheimer](https://github.com/vanbumi/CodeJournal/blob/master/React/intro-to-react-book.md)

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