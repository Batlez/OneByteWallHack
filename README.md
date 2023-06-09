# OneByteWallHack
OneByteWallhack is a Python 3 script that achieves a wallhack in CS:GO by modifying a single byte of game memory.

This script aims to replicate the functionality of the **r_drawothermodels 2** command without directly modifying the associated cvar, making it supposedly VAC-safe.

## How Does It Work?
The program accomplishes its goal by patching the assembly code generated from compiling a specific line of the game's source code. The line in question can be found [here](https://github.com/ValveSoftware/source-sdk-2013/blob/0d8dceea4310fde5706b3ce1c70609d72a38efdf/mp/src/game/client/c_baseanimating.cpp#L3149):
```cpp
int extraFlags = 0;
if ( r_drawothermodels.GetInt() == 2 )
{	
    extraFlags |= STUDIO_WIREFRAME;	
}
```

To bypass the **r_drawothermodels** cvar check, the script modifies the code to ensure that the `if` statement constantly evaluates to **true** when the **r_drawothermodels** cvar is set to its default value of 1.

## What To Do To Make It Work?
**Important!:**
If you haven't done so already, make sure to download [Python 3.9 or a newer version](https://www.python.org/downloads/)

Additionally, you may need to navigate to ```"C:\Users\ username \AppData\Local\Programs\Python\Python39\Scripts"```, press Win+R, type ```"cmd"```, and execute the commands ```"pip install pymem"``` and ```"pip install pywin32"``` and ```"pip install regex"``` before restarting your computer.

**Usage:**
Before running the script, ensure that CS:GO is already running. It is also essential to run the script with administrator privileges.

**Credits:**
I added some of my code to it, but OneByteWallHack was initially created by [danielkrupinski](https://github.com/danielkrupinski/OneByteWallhack).
