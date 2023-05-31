Process: 
1. Patron presses the open door button on outside control panel
2. The Elevator door opens
3. Patron selects floor on inside control panel 
4. The Elevator door shuts
5. The elevator moves up or down depending on the floor selection in relation to the current floor
6. When the current floor matches the floor the patron selected the elevator stops
7. The Elevator door opens 

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
  INITIALIZE
    Current Floor = 1
  
  Patron.pressDoorButton('open')
  
  OutsideControlPanel.doorButtonPressed('open')
  
  ElevatorDoor.openClose('open')
  
  Patron.floorSelection(5)
  
  InsideControlPanel.selectionMade(5)
  
  ElevatorDoor.openClose('close')
  
  DO LiftingSystem.moveup() WHILE currentFloor < floorSelected
  DO Lifting System.movedown() WHILE currentFloor > floorSelected
  
  Elevator.doorOpenClose('open')

END
-----------------------------------------------------------------
Objects and Functions

INIT function
CREATE Elevator 
CREATE Patron
CREATE Outside Control Panel
CREATE Inside Control Panel 
CREATE Lifting System
CREATE Current Floor

Patron
  pressDoorButton
  floorSelection
 
Outside Control Panel 
  doorbuttonPressed
 
Elevator Door
  openClose
 
Inside Control Panel 
  selectionMade
 
Lifting System
  moveUp
  moveDown
  
  
