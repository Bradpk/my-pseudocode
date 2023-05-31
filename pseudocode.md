# Building A Virtual Elevator 

## Rules:
1. Write one statement per line
2. Capitalize initial keywords (READ, WRITE, IF, WHILE, UNTIL).
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

   Door Panel:
        - A single button (on/off) 
        - A display panel with a button that lights up when pressed 
        - Checks whether a selection has been made
        - Tracks Floor Location Of Itself
     
   Control Panel 
        - An array of buttons corisponding to different floors
        - A display panel with buttons that light up when pressed
        - Checks whether a selection has been made
        
   Elevator Compartment 
        - Pulley that lifts the elevator
        - Pulley that can lowers the elevaotr 
        - Pulley that can stop the elevator
        - Tracks Current Floor Of Itself
        
   Elevator Door
        - Open Door
        - Close Door
    
   Patron:
       - Selects the button on the door panel 
       - Selects a floor button on the control panel
       - Trakcs Floor Location Of Itself
    
---------------------------------------------------------------
## BEGIN

INITIALIZE()
Elevator Compartment Floor: 10
Patron Floor: 1
Door Panel Light: Off
Door Panel Floor: 1
Door Panel Selection: False
Elevator Door: Closed
Control Panel Light: Off
Control Panel Selection: False
  
1. Patron pushes the door panel button
 SET Patron.doorButton = on
  
2. Door panel registers door button has been pushed
 IF Patron.doorButton = on
  THEN:
  DoorPanel.selectionMade = true
  ELSE DoorPanel.selectionMade = false
  
3. Door panel button lights up 
 IF DoorPanel.selectionMade = true
  THEN:
  DoorPanel.light = on
  ELSE DoorPanel.light = off
  
4. Lifting system moves the elevator compartment to the floor the patron is on
 IF DoorPanel.selectionMade = 'true' 
  THEN:
  FOR ElevatorCompartment.floor[] > Patron.floor[] 
   THEN: 
   ElevatorCompartment = move down
    FOR ElevatorCompartment.floor[] > Patron.floor[] 
    THEN: 
    SET ElevatorCompartment = move up
  
5. Elevator door opens 
 IF ElevatorCompartment.floor[] = Patron.floor[] 
  THEN: 
  SET ElevatorDoor = open
   
6. Patron selects floor from an array of buttons on the control panel 
 SET Patron.controlPanel = [7]
   
7. The control panel registers a selection has been made 
 IF Patron.controlPanel = true
 THEN:
 ControlPanel.selectionMade = true
 ELSE ControlPanel.selectionMade = false
   
8. The selected floor button lights up 
 IF Patron.controlPanel = [7] AND ControlPanel.selectionMade = true
  THEN:
  ControlPanel.light[7] = on
  
9. Elevator door shuts
 IF ControlPanel.selectionMade = true 
  THEN:
  ElevatorDoor = close
  
10. The elevator moves to the floor selected on the control panel
 FOR ElevatorCompartment.floor[] > Patron.controlPanel[7] 
  THEN: 
  ElevatorCompartment move down
   FOR ElevatorCompartment.floor[] < Patron.Controlpanel[7] 
    THEN: 
    SET ElevatorCompartment = move up
   
11. When the current floor matches the floor the patron selected the elevator stops   
 IF ElevatorCompartment.floor[] = Patron.Controlpanel[7] 
  THEN:
  ElevatorCompartment = stop
   
12. The elevator door opens 
 IF ElevatorCompartment.floor[] = Patron.Controlpanel[7] AND ElevatorCompartment = stop
  THEN:
  SET ElevatorDoor = open
   
   
## END
-----------------------------------------------------------------
