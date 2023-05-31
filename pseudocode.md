Building A Virtual Elevator 

Rules:
1. Write one statement per line
2. Capitalize initial keywords (READ, WRITE, IF, WHILE, UNTIL).
3. Indent to show hierarchy.
4. End multi line structure.
5. Keep statements language agnostic.

Process:
 
  1. Patron presses the open door button on door panel
  
  2. Door panel registers door button has been pushed

  3. Door panel lights up 
  
  4. Lifting system moves the elevator to the floor of the patron 
  
  5. Elevator Door Opens 
  
  6. Patron selects floor from an array of buttons on control panel 
  
  7. The control panel registers a selection has been made 

  8. Selected Floor Button Lights Up 
  
  9. The Elevator door shuts
  
  10. The elevator moves to the floor selected on the control panel
      
  11. When the current floor matches the floor the patron selected the elevator stops    
  
  12. The elevator door opens 

INITIALIZE: Variables

   Door Panel:
        - A single button (on or off) 
        - A display panel, button lights up when pressed 
     
   Control Panel 
        - An array of buttons corisponding to different floors
        - A display panel, buttons light up when pressed
        
   Lifting System
        - Pulley that lift the elevator
        - Pulley that can lower the elevaotr 
        - Pulley that can stop the elevator
        
   Elevator Door
        - Open Door
        - Close Door
    
   Patron:
       - Selects the button on the door panel 
       - Selects a floor button on the control panel
    
---------------------------------------------------------------
BEGIN

  INITIALIZE()
  
  1. Patron presses the open door button on outside control panel
  - Set door button to pushed
  READ Patron.doorButton('true')
  
  IF Patron.doorButton = 'true' THEN DoorPanel.selectionMade = 'true' AND doorpanel.light = 'true'
  
  If doorpanel.selectionMade = 'true' THEN Lifting System = current floor AND door opens 
  Else door opens 
  
  READ Patron.controlpanel[5] 
  
  If co
  
  
  2. Control panel registers door button has been pushed and moves to the elevator to the floor level of the patron and opens the door
  IF door button is "true" THEN lifting system is set to current floor AND elevator door is set to "true" 
  READ OutsideControlPanel.doorButtonPressed('pressed)
  
  Lifting system moves to the current floor of the patron 
  
  Elevator Door Opens 
  
  4. Patron selects floor on inside control panel 
  INPUT Patron.floorSelection(5)
  
  5. The inside control panel registers a selection has been made and the selected floor button lights up.
  READ InsideControlPanel.selectionMade(5)
  
  6. The Elevator door shuts
  ElevatorDoor.openClose('close')
  
  7. The elevator moves up if the floor selection is higher than the current floor
  IF (currentFloor < floorSelected)
      THEN LiftingSystem.moveup()
      
  8. The elevator moves down if the floor selection is lower than the current floor    
  ELSE If (currentFloor > floorSelected)
      THEN Lifting System.movedown() 
      
  9. When the current floor matches the floor the patron selected the elevator stops    
  ELSE Lifting System.stop() 
  
  10. The elevator door opens once the selected floor matches the current floor and the elevator has come to a halt
  Elevator.doorOpenClose('open')

END
-----------------------------------------------------------------

Patron
  INIT:
  doorButton
  floorSelection
 
Outside Control Panel 
  INIT:
  doorbuttonPressed
 
Elevator Door
  INIT:
  doorSensor
 
Inside Control Panel 
  INIT:
  selectionMade
 
Lifting System
  INIT:
  moveUp
  moveDown
  stop
  
  
