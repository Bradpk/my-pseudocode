Rules:
1. Write one statement per line
2. Capitalize initial keywords (READ, WRITE, IF, WHILE, UNTIL).
3. Indent to show hierarchy.
4. End multi line structure.
5. Keep statements language agnostic.

Objects & Data Structures

Elevator: 
   Outside Control Panel:
        - A single onPress button 
        - A display panel, button lights up when pressed 
     
   Inside Control Panel 
        - An array of buttons corisponding to different floors
        - Each button requires an onPress button
        - A display panel, buttons light up when pressed
        
   Lifting System
        - Pulley that lifts or lowers the elevator based off selection made by the control panels
        
   Elevator Door
        - Opens and Closes door
    
Patron:
    - Presses the button on the outside control panel 
    - Selects a floor on the inside control panel
    
---------------------------------------------------------------
BEGIN

  INITIALIZE()
  
  1. Patron presses the open door button on outside control panel
  INPUT Patron.pressDoorButton('pushed')
  
  2. Control panel registers door button has been pushed and moves to the floor level of the patron
  READ OutsideControlPanel.doorButtonPressed('pressed)
  
  3. The Elevator door opens
   ElevatorDoor.openClose('open')
  
  4. Patron selects floor on inside control panel 
  INPUT Patron.floorSelection(5)
  
  5. The inside control panel registers a selection has been made and the selected button lights up
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
Objects and Functions

INITIALIZE function
CREATE Elevator 
CREATE Patron
CREATE Outside Control Panel
CREATE Inside Control Panel 
CREATE Lifting System
CREATE Current Floor

Patron
  INIT:
  pressDoorButton
  floorSelection
 
Outside Control Panel 
  INIT:
  doorbuttonPressed
 
Elevator Door
  INIT:
  openClose
 
Inside Control Panel 
  INIT:
  selectionMade
 
Lifting System
  INIT:
  moveUp
  moveDown
  stop
  
  
