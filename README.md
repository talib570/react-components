# react-components
simple example of react components

	class Button extends React.Component {  
		handleClick = () => {
		this.props.onClickFunction(this.props.incValue);
	  };

		render() {
		return (
		<button onClick={this.handleClick}>
		+{this.props.incValue}
	      </button>
	    );
	  };
	}

	const Result = (props) => {
		return (
		<div>{props.counter}</div>
	  );
	};

	class App extends React.Component {
	  state = { counter: 0 };

	  incrementCounter = (incValue) => {
		this.setState((prevState) => ({
		counter: prevState.counter + incValue
	    }));
	  };

		render() {
		return (
		<div>
		<Button incValue={1}   onClickFunction={this.incrementCounter} />
		<Button incValue={5}   onClickFunction={this.incrementCounter} />
		<Button incValue={10}  onClickFunction={this.incrementCounter} />
		<Button incValue={100} onClickFunction={this.incrementCounter} />
		<Result counter={this.state.counter} />
	      </div>
	    );
	  }
	}

	ReactDOM.render(<App />, mountNode);
