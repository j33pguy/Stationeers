# Psuedo Code for Furnace Vending Machine Logic

## Setup
     - Look at the button state
       - if button is pushed advance the 'stack' by one (push) +1 sp
     - look for furnace to open mold
       - if mold open, decrement stack by one 

## Add an Alloy
    - push, add +1 to sp move the hash to the register

## Remove an Alloy
    - pop, remove -1 to sp and move the hash to register