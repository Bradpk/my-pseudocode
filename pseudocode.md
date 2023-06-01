# Building A Virtual Elevator 

## Rules:
1. Write one statement per line
2. Capitalize initial keywords (READ, WRITE, IF, WHILE, UNTIL etc).
3. Indent to show hierarchy.
4. End multi line structure.
5. Keep statements language agnostic.

## Process:
 
1. Patron pushes the open door button on door panel
2. Door panel registers door button has been pushed
3. Door panel lights up 
4. Lifting system moves the elevator compartment to the floor the patron is on
5. Elevator door opens 
6. Patron selects floor from an array of buttons on the control panel 
7. The control panel registers a selection has been made 
8. The selected floor button lights up 
9. Elevator door shuts
10. The elevator moves to the floor selected on the control panel 
11. When the current floor matches the floor the patron selected the elevator stops    
12. The elevator door opens 

## INITIALIZE: Variables

  ### Door Panel:
        - A single button (on/off) 
        - A display panel with a button that lights up when pressed 
        - Checks whether a selection has been made
        - Tracks floor location of itself
     
  ### Control Panel 
        - An array of buttons corisponding to different floors
        - A display panel with buttons that light up when pressed
        - Checks whether a selection has been made
        
  ### Elevator Compartment 
        - Pulley that lifts the elevator
        - Pulley that lowers the elevaotr 
        - Pulley that can stop the elevator
        - Tracks floor of itself
        
  ### Elevator Door
        - Open door
        - Close door
    
   ### Patron:
       - Selects the button on the door panel 
       - Selects a button on the control panel
       - Trakcs floor location of itself
    
---------------------------------------------------------------
## BEGIN


INITIALIZE()
Elevator Compartment Floor: 10 <br>
Patron Floor: 1 <br>
Door Panel Light: Off <br>
Door Panel Floor: 1 <br>
Door Panel Selection: False <br>
Elevator Door: Closed <br>
Control Panel Light: Off <br>
Control Panel Selection: False <br>
  
1. Patron pushes the door panel button <br>
&nbsp; SET Patron.doorButton = on
  
2. Door panel registers door button has been pushed <br>
&nbsp; IF Patron.doorButton = on <br>
&nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; DoorPanel.selectionMade = true <br>
&nbsp; &nbsp; ELSE DoorPanel.selectionMade = false <br>
&nbsp; &nbsp; &nbsp; END
  
3. Door panel button lights up <br>
&nbsp; IF DoorPanel.selectionMade = true <br>
&nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; DoorPanel.light = on <br>
&nbsp; &nbsp; ELSE DoorPanel.light = off <br>
&nbsp; &nbsp; &nbsp; END
  
4. Lifting system moves the elevator compartment to the floor the patron is on <br>
&nbsp; IF DoorPanel.selectionMade = true <br>
&nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; FOR ElevatorCompartment.floor[] > Patron.floor[] <br>
&nbsp; &nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; &nbsp; ElevatorCompartment = move down <br>
&nbsp; &nbsp; &nbsp; FOR ElevatorCompartment.floor[] > Patron.floor[] <br>
&nbsp; &nbsp; &nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; &nbsp; &nbsp; SET ElevatorCompartment = move up <br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; END
  
5. Elevator door opens <br>
&nbsp; IF ElevatorCompartment.floor[] = Patron.floor[] <br>
&nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; SET ElevatorDoor = open <br>
&nbsp; &nbsp; &nbsp; END
   
6. Patron selects floor from an array of buttons on the control panel <br>
&nbsp; SET Patron.controlPanel = [7] <br>
   
7. The control panel registers a selection has been made <br>
&nbsp; IF Patron.controlPanel = true <br>
&nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; ControlPanel.selectionMade = true <br>
&nbsp; &nbsp; &nbsp; ELSE ControlPanel.selectionMade = false <br>
&nbsp; &nbsp; &nbsp; &nbsp; END
   
8. The selected floor button lights up <br>
&nbsp; IF Patron.controlPanel = [7] AND ControlPanel.selectionMade = true <br>
&nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; ControlPanel.light[7] = on <br>
&nbsp; &nbsp; &nbsp; END
  
9. Elevator door shuts <br>
&nbsp; IF ControlPanel.selectionMade = true <br>
&nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; ElevatorDoor = close <br>
&nbsp; &nbsp; &nbsp; END
  
10. The elevator moves to the floor selected on the control panel <br>
&nbsp; FOR ElevatorCompartment.floor[] > Patron.controlPanel[7] <br>
&nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; ElevatorCompartment move down <br>
&nbsp; &nbsp; FOR ElevatorCompartment.floor[] < Patron.Controlpanel[7] <br>
&nbsp; &nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; &nbsp; SET ElevatorCompartment = move up <br>
&nbsp; &nbsp; &nbsp; &nbsp; END
   
11. When the current floor matches the floor the patron selected the elevator stops <br>
&nbsp; IF ElevatorCompartment.floor[] = Patron.Controlpanel[7] <br>
&nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; ElevatorCompartment = stop <br>
&nbsp; &nbsp; &nbsp; END
   
12. The elevator door opens <br>
&nbsp; IF ElevatorCompartment.floor[] = Patron.Controlpanel[7] AND ElevatorCompartment = stop <br>
&nbsp; &nbsp; THEN: <br>
&nbsp; &nbsp; SET ElevatorDoor = open <br>
&nbsp; &nbsp; &nbsp; END
   
   
## END
-----------------------------------------------------------------
