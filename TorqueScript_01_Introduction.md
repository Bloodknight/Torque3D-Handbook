# TorqueScript - Introduction
## What is TorqueScript
TorqueScript (TS) is a proprietary scripting language developed specifically for Torque technology. The language itself is derived from the scripting used for Tribes 2, which was the base tech Torque evolved from. Scripts are written and stored in .cs files, which are compiled and executed by a binary compiled via the C++ engine (.exe for Windows or .app OS X).<br>
The CS extension stands for "C Script," meaning the language resembles C programming. Though there is a connection, TorqueScript is a much higher level language and is easier to learn than standard C or C++. 
## Basic Usage
Like most other scripting languages, such as Python or Java Script, TorqueScript is a high-level programming language interpreted by Torque 3D at run time. Unlike C++, you can write your code in script and run it without recompiling your game.<br>
<br>
All of your interfaces can be built using the GUI Editor, which saves the data out to TorqueScript. The same goes for data saved by the World Editor or Material Editor. Most of the editors themselves are C++ components exposed and constructed via TorqueScript.<br>
<br>
More importantly, nearly all of your game play programming will be written in TorqueScript: inventory systems, win/lose scenarios, AI, weapon functionality, collision response, and game flow. All of these can be written in TorqueScript. The language will allow you to rapidly prototype your game without having to be a programming expert or perform lengthy engine recompilation. 

## Scripting vs Engine Programming
As mentioned above, TorqueScript is comprised of the core C++ objects needed to make your game. For example, you will use the PlayerData structure to create player objects for your game. This structure was written in C++:<br>
<br>
##### C++ PlayerData Code<br>
```cs 
struct PlayerData: public ShapeBaseData {
   typedef ShapeBaseData Parent;

   bool renderFirstPerson; // Render the player shape in first person

   mass = 9.0f;         // from ShapeBase
   drag = 0.3f;         // from ShapeBase
   density = 1.1f;      // from ShapeBase
}
```
Instead of having to go into C++ and create new PlayerData objects or edit certain fields (such as mass), PlayerData was exposed to TorqueScript:
<br>
##### Example TorqueScript PlayerData Code<br>
```cs
datablock PlayerData(DefaultPlayerData)
{
   renderFirstPerson = true;
   className = Armor;
   shapeFile = "art/shapes/actors/gideon/base.dts";
   mass = 100;
   drag = 1.3;
   maxdrag = 0.4;

   // Allowable Inventory Items
   maxInv[Pistol] = 1;
   maxInv[PistolAmmo] = 50;
};
```
If you want to change the name of the object, the mass, the inventory, or anything else, just open the script, make the change, and save the file. When you run your game, the changes immediately take affect. Of course, for this example you could have used the Datablock Editor, but you should get the point. TorqueScript is the first place you should go to write your game play code. 
## Script Editors
TorqueScript files are essentially text files. This means you have several editors to choose from. Some users prefer to use the stock OS text editors: Notepad on Windows or Text Edit on OS X. Others will use their programming IDEs (Interactive Development Environments), such as Visual Studio for Windows or Xcode on OS X. Third party applications are the most popular choice:

### Recommended:
**Torsion** - [Github]() - [Download]() <br>
Torsion is undeniably the best TorqueScript IDE it is currently a wondows project, it is fully open source. It was developed by Torque veterans Sickhead Games. If you are developing on Windows, this is the first thing you should purchase after Torque 3D. No other editor offers this level of quality and functionality:<br> <br>
* Integrated "One Click" script debugging<br>
* Full control over script execution via step and break commands
* Advanced editor features like code folding, line wrapping, auto-indent, column marker, automatic bracket matching, and visible display of tabs and spaces<br>
* Goto line and text searching<br>
* ScriptSense updated dynamically as you type<br>
* Customizable syntax highlighting for TorqueScript<br>
* Unlimited undo/redo buffer<br>
* Code browser window for exploring both engine exports and script symbols in your project<br>

#### Alternatives:
**Visual Studio Code** - [Github]() - [Download]() <br>
A cross platform and free editor from microsoft, many plugins makes this a very flexible editor and more.<br>

**Notepad++** - [Github]() - [Download]() <br>
This is a free (as in "free speech" and also as in "free beer") source code editor and Notepad replacement that supports several languages.

### Relatively.... Recent Changes
#### Foreach Statements
Two new statements simplify the iteration over sets of objects and string vectors.
To loop over each object in a SimSet, use the foreach statement:
```
foreach( %obj in %set )
   /* do something with %obj */;
```
To loop over each element in a string vector, use the foreach$ statement:
```
foreach$( %str in "a b c" )
   /* do something with %str */;
```

foreach Statement foreach$ Statement

Redefinition Behavior  TODO <br>
Singletons TODO <br>
Lookup Operator TODO <br>
Floating-Point Notation TODO <br>
Datablock Syntax Extensions TODO <br>
