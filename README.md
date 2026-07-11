# InstaPlugins
A new Roblox Framework.

# What is InstaPlugins
InstaPlugins is a Luau Plugin that makes Scalable and Efficient the creation of Plugins, it is inspired from ReactJs. It is easy to Import, Config and Init.
InstaPlugins helps you make Plugins Fast:
- Shortcuts: !setup, !CreateDock/Gui are Snippets.
- Everything is in the Plugin Script (the Central Script), so you can have a Working Gui close-open syststem with few lines of code!
- root:SaveData('*true') saves everything for you, such as ConfigData and ButtonData.
- Using root:CreateButton() instead of plugin:CreateButton() you can access the Button's Id, IconImg, etc...
- The Structure is easy to learn
- New Types that helps you manage Data faster

# Usage:

## How to set it up
When you run InstaPlugins in Roblox Studio you need to choose a Name for the Plugin and choose a place where to import the Framework (i suggest ServerScriptService), you can also toggle turn on/off the Shortcuts, which lets you can write !setup or similiar keywords in LuaSourceContainers.

## How to start using it
Once you configured it, you can see that the folder you created for your Plugin will have a ModuleScript, a Script and a Folder (Components), you will be using most of the times the Script and the Folder, to Connect the Instances you make into the Scipt, as i already said, it is inspired from ReactJs. You can create Module scripts in the Components Folder which returns a function with atleast 2 arguments: Component (Instance or pluginButtonData) and Data (a Table or Dictionary). **Now this Structure lets you can manage multiple similiar Buttons or Instances at the same time with just sending those 2 arguments, and calling the same function, and having more Clear code**, this is one of a cool features my plugin gives to you.

## Data Saving
my plugin dont lose important data, when you create a Toolbar or you create a pluginButton your data will be saved, a feature that can be lost if not stored in variables, my plugin does it automatically, and if you want your plugin to be fast you can use the root:SaveData('*false') which will not save anymore ConfigData and ButtonData (we will get into it later).
Now, as i said, my plugin saves data automatically, **but how to acess it**? when you create a Button for your Toolbar, you can acess the data of it, a feature that the plugin keyword dont provide, after you created the Button using root:CreateButton you can acess from it the Button's Id, Tooltip, IconImg, Description, Toolbar and even the Button itself using Button.self.

## Useful Commands
  1) the `root:Init({Component: pluginButtonData, ModuleScript: ModuleScript, Data: {}?, elaborateData: boolean?})` lets you can Initialize a module script, you need pass a Component and a ModuleScript to this function, and if you want, Data and elaborateData, and the Main script will call the function you returned from that Module Script passing the data (Data and elaborateData) as Arguments.
**elaborateData**: Converts a Dictionary to a Table, you can see that when you import the Main Folder, there is a ModuleScript (Component) inside Components where you see that i am getting Data[1] and not Data['OnClick'] which is what i sent from the Plugin Script, **this might be dangerous if not handled correctly**.
  2) `root:Config(Folder:Folder)` is a function that returns the Components Folder and the Name of the Folder, but at the same time saves the Main Folder and the Components Folder and the Main Folder Name in root, you can acess them using `root.MainFolder root.Components root.Name`
  3) `root:Get(Name:string, place:'Components'|'MainFolder'|Instance?` returns the first Instance found with name Name and in place or by default in Components.

# DataTypes
when you call the `root:SaveData()` function you can give a table or '*true' or '*false', if you dont want any type of Data to be saved then just use '*false' or else '*true', but if instead you want only give true to some DataTypes and false to others, then you can pass a Dictionary where you can write these Data Names:
- ConfigData: Doesn't save anymore these types of data: `root.Name root.MainFolder root.Components`, but they are still createable using `root.something` or `root['something']`.
- ButtonData: Skips the ability to read the `Button.Toolbar` propriety, but you will still be able to read the Button's Id, Tooltip, IconImg, Description and Button.self.

Remember: My plugin is open-source, so it means you can save/delete the data how you want, so you can even create root.Hello etc.

# Gui Managing
you can see when you open the Script that there is a Do-End with inside some code, it is managing the open-close frame visibility, but before it, there is a new function: root:CreateGui() which deletes all copies of that gui in CoreGui and asks for a gui and creates a copy of that gui in the Coregui; You can also see that we aren't using a normal root:Get() but a special type of it, where it asks for a new type: Children, Children is a type where you insert a Parent and the Children you want to search for, and root:Get() will return the Children found in that Parent.

# Special Commands
As i already said before, you will Unlock some Shortcuts when you Install the Plugin, here is what they do:
- !setup: use it in ModuleScripts in Components, to create Components Faster!
- !CreateGui: Generates the basic structure of a Gui, but remember to have a ScreenGui and also to have a Button that calls togglePluginGui!
- !CreateDock: Creates a Dock which will show only if you call the togglePluginGui function when a button is clicked or just use `Dock.Enabled = true`

Remember to have 1 togglePluginGui function, if you want use the Dock and the Gui at the same time then name them differently, like toggleDock and toggleGui!

# Future Updates
- GUI managing: You will be soon able to create DockWidgets faster.
- You will be able to insert data inside `root.Data[...]` using `root:AddData()` or by doing it manually using `root.Data`
