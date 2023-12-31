# Node Graphs

Rocketship allows the parameters and logical flow of a **Binding** to be controlled using a **Node Graph**.

**Nodes**:
- Threshold
	- Passes along value changes so long as the value is greater than or equal to the threshold
	- Inputs:
		- Value (number)
		- Threshold (number)
	- Outputs:
		- Value (number)
- Sample
	- Trigger tells you 'when', Emitter tells you 'what'
	- Inputs:
		- Trigger (null)
		- Emitter (data)
	- Outputs:
		- Value of the connected Emitter, when the Trigger is fired
- Gate
	- Value is passed on so long as the gate is open
	- Inputs:
		- Open (boolean)
		- Value
	- Outputs:
		- Value
- Trigger
	- Allows you to create named Triggers
	- Inputs:
		- Trigger (null)
	- Outputs:
		- Trigger (null)
- Value
	- Allows you to create named, keyframeable, shared Values
	- Inputs:
		- Value
	- Outputs:
		- Value