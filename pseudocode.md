Variables: Patron, Elevator, Control Panel, Floor Buttons, Open/Door Button

Objects: 

Functions: 

Arrays: 

Loops:

If/Else: 

What needs to be done: (Functions) 
Outside button to open door to enter elevator. (if)
Elevator moves up and down. 
Buttons move to floor associated with button number on click.
Doors open and shut. (if)
Time elapses for patron to enter or leave elevator.
Needs to track current floor number to know whether the button input in lower or higher than current floor.
Move up if button number is higher than current floor, or goes down if button number is lower than current floor (if else statement).
Keeps going up or down until floor number is reached (loop).

Patron: 
  variables:

  functions:
    floorSelection
    doorButton
    
    
Elevator:
  variables:
    currentFloor
    floorSelected
  
  function:
    movesUp
    movesDown
    wait
    doorOpenClose
  
  
Inside Control Panel: 
  variables:
    floorSelector
    floorArray[]
  
  function:
    slectionMade
  
  
Outside Control Panel:
  variables:
  
  function:
    openClose


Process: 

Patron opens door
Patron selects floor on control panel 
door shuts
elevator moves up or down depending on the floor selection in relation to the current floor
when elevator floor matches the floor the patron selected elevator stops and door opens

Rules
1. Write one statement per line
2. Capitalize initial keywords (READ, WRITE, IF, WHILE, UNTIL).
3. Indent to show hierarchy.
4. End multi line structure.
5. Keep statements language agnostic.



BEGIN
  INITIALIZE  
  
  Patron.doorButton('open')
  
  OutsideControlPanel.openClose('open')
  
  Elevator.doorOpenClose('open')
  
  Patron.floorSelection(5)
  
  InsideControlPanel.selectionMade(5)
  
  Elevator.doorOpenClose('close')
  
  DO Elevator.moveup() WHILE currentFloor < floorSelected
  DO Elevator.movedown() WHILE currentFloor > floorSelected
  
  Elevator.doorOpenClose('open')

END
