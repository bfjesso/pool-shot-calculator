# Pool Shot Calculator
This is a game Mod for Real Pool 3D: https://store.steampowered.com/app/670290/Real_Pool_3D__Poolians/

# Usage
While the game is running, run shotcalc.exe. To avoid crashing, you should wait until you are in a match.
The terminal will print the controls.

# How it Works
To calculate shots, the direction between the target ball and pocket is calculated by subtracting the pocket's coordinates from the target ball's coordinates. Next, the ghost ball, or the position the cue ball needs to hit the target ball at is calculated by multiplying the previous direction by the cue ball's radius. Then, the target direction is calculated by subtracting the cue ball's coordinates from the ghost ball's coordinates. Finally, the target angle is calculated using inverse tangent, which is then converted to degrees by multiplying by 180 and dividing by PI.

Bank shots are calculated by reflecting the pocket's location accross the bank wall. An explanation for can be found here: https://www.billiardsthegame.com/finding-the-bank-angle-317

The injector works by allocating memory in the game process for the path to the shotcalc.dll. Then, a remote thread is created and starts on LoadLibraryA with the path location as a parameter. 
