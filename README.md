# simple-state
A state manager which is easy to use and dispose the variable at your ease. A simple Observable at best.
It based on callback approach, where we can provide subscriber for the state variable. A lightweight library with no additional burden on your network.

## Creating a 'state'
<code>
  var timeState = new StateManager();
</code>
While creating a simple state we can pass a preset value for the variable. 
## Accessing current value
<code>
  var timeState = new StateManager('New Value');
  timeState.value() // returns 'New Value'
</code>
In order to access the current value of state we can use <code>timeState.value()</code>.
## Changing values
In order to change value, we can use the <code>next</code> method available in the State variable.
<code>
    timeState.next('Changed value');
</code>
## Subscribing changes
We can provide a subscriber function callback with arguements as Old Value, New Value. The subscriber function gets called when there is a change in value of the 'State'.
<code>
    timeState.subscribe(function(oldState, newState){
      console.log("Old Value >> ", oldState, " New Value >> ", newState);
    });
</code>
## Unsubscribing subscriber function
'Subscribe' method will return an object with 'dispose' method available. We can use the dispose method to remove the subscriber function.
<code>
  var temp =  timeState.subscribe(function(oldState, newState){
      console.log("Old Value >> ", oldState, " New Value >> ", newState);
    });
  temp.dispose(); // removes the subscriber method
</code>

This is just the initial build, please be happy to contribute.
