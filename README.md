# simple-state
A state manager which is easy to use and dispose the variable at your ease. A simple Observable at best.
It based on callback approach, where we can provide subscriber for the state variable. A lightweight library with no additional burden on your network.<br>
## Creating a 'state'
<code>
  var timeState = new StateManager();
</code>
While creating a simple state we can pass a preset value for the variable. <br>
-----------------------
Accessing current value
-----------------------
<br>
<code>
  var timeState = new StateManager('New Value');
  timeState.value() // returns 'New Value'
</code>
<br>
In order to access the current value of state we can use <code>timeState.value()</code>.
<br>
---------------
Changing values 
---------------
<br>
In order to change value, we can use the <code>next</code> method available in the State variable.
<br>
<code>
    timeState.next('Changed value');
</code>
<br>
-------------------
Subscribing changes
-------------------
<br>
We can provide a subscriber function callback with arguements as Old Value, New Value. The subscriber function gets called when there is a change in value of the 'State'.
<br>
<code>
    timeState.subscribe(function(oldState, newState){
      console.log("Old Value >> ", oldState, " New Value >> ", newState);
    });
</code>
<br>
---------------------------------
Unsubscribing subscriber function
---------------------------------
<br>
'Subscribe' method will return an object with 'dispose' method available. We can use the dispose method to remove the subscriber function.
<br>
<code>
  var temp =  timeState.subscribe(function(oldState, newState){
      console.log("Old Value >> ", oldState, " New Value >> ", newState);
    });
  temp.dispose(); // removes the subscriber method
</code>
<br>
This is just the initial build, please be happy to contribute.
